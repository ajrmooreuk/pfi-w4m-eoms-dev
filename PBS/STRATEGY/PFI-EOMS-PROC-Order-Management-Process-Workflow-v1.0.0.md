# PFI-EOMS-PROC: Order Management Process Workflow

**Product Code:** PFI-EOMS
**Document Type:** PROC — Process Definition & Workflow Specification
**Version:** v1.0.0
**Date:** 2026-03-10
**Status:** Draft
**PE-ONT Instance:** `pe-eoms-process-instance-v1.0.0.jsonld`
**SOP Graph Mapping:** `eoms-test-data-graph-mapping-v1.0.0.json`

---

## 1. Purpose

This document defines the EOMS order management processes, user roles, and workflow journeys. It maps directly to the PE-ONT process instance and SOP-ONT graph entities. Every process step is a testable unit for TDD — the PE process instance provides `testContract` specifications that the builder uses to generate test stubs.

---

## 2. User Roles

| Role | Access Level | Primary Actions | RBAC Guard |
|------|-------------|-----------------|------------|
| **Trader** | Standard | Create orders, add line items, search products, complete orders, export | `role = 'trader'` |
| **Admin** | Elevated | All Trader actions + user management, system config, view all orders | `role = 'admin'` |
| **Finance** (future) | Read + Export | View orders, download exports, FX data | Deferred to Phase 3 |
| **Operations** (future) | Read + Logistics | Shipping status, container tracking | Deferred to Phase 2 |

---

## 3. Core Order Lifecycle

The EOMS order lifecycle follows the SOP-ONT entity chain. Each state transition maps to a specific SOP entity.

```mermaid
stateDiagram-v2
    [*] --> Draft: Trader creates order
    Draft --> Draft: Edit order / Add lines
    Draft --> Complete: Trader marks complete
    Complete --> Complete: View / Review
    Complete --> Exported: Trader exports to finance
    Exported --> [*]: Order archived

    Draft --> Cancelled: Trader cancels
    Cancelled --> [*]

    state Draft {
        [*] --> CustomerEnquiry: Select buyer
        CustomerEnquiry --> SalesQuotation: Add line items
        SalesQuotation --> OrderCapture: Confirm order details
    }

    state Complete {
        [*] --> OrderValidation: System validates
        OrderValidation --> CreditCheck: Auto credit check
        CreditCheck --> ReadyForExport: Check passed
    }

    note right of Draft
        SOP Entities: CustomerEnquiry,
        SalesQuotation, QuotationLine,
        OrderCapture, CustomerAccount
    end note

    note right of Complete
        SOP Entities: OrderValidation,
        CreditCheck
        Bridge: validatedOrderToFulfilment → OFM
    end note
```

---

## 4. Order Creation Process (F1.1)

The order creation wizard is the primary workflow. It maps to the SOP enquiry→quotation→capture chain.

```mermaid
flowchart TD
    A[🏠 Dashboard] -->|"New Order"| B[Step 1: Select Customer]
    B -->|"Search / Create"| C{Existing Customer?}
    C -->|Yes| D[Select from list]
    C -->|No| E[Create new customer]
    D --> F[Step 2: Shipping Details]
    E --> F

    F -->|"Port, Transport, Incoterms"| G[Step 3: Add Products]
    G -->|"Search catalogue"| H[Select Product]
    H -->|"Qty, Price, UOM"| I[Add Line Item]
    I -->|"More products?"| G
    I -->|"Done"| J[Step 4: Review Order]

    J -->|"Edit"| B
    J -->|"Save Draft"| K[📋 Draft Order]
    J -->|"Complete"| L[✅ Complete Order]

    K -->|"Resume later"| B

    style A fill:#19253B,color:#fff
    style L fill:#4caf50,color:#fff
    style K fill:#ff9800,color:#fff

    subgraph SOP_Mapping [SOP-ONT Entity Mapping]
        direction LR
        S1[sop:CustomerEnquiry] --> S2[sop:SalesQuotation]
        S2 --> S3[sop:QuotationLine]
        S3 --> S4[sop:OrderCapture]
    end
```

---

## 5. Trader User Journey

Complete journey from login to order export.

```mermaid
journey
    title Trader: Daily Order Management
    section Login
      Open EOMS: 5: Trader
      Authenticate (email/password): 4: Trader
    section Dashboard
      View active orders: 5: Trader
      Check pending actions: 4: Trader
    section Create Order
      Click "New Order": 5: Trader
      Select buyer: 4: Trader
      Set shipping details: 3: Trader
      Search products: 4: Trader
      Add line items (x5): 3: Trader
      Review order totals: 4: Trader
      Save as draft: 5: Trader
    section Complete Order
      Open draft order: 5: Trader
      Review all details: 4: Trader
      Mark as complete: 5: Trader
      System validates: 5: System
      Credit check passes: 5: System
    section Export
      Select completed orders: 4: Trader
      Export to CSV/JSON: 5: Trader
      Confirm exported: 5: Trader
```

---

## 6. Admin User Journey

Admin has elevated access for user management and system oversight.

```mermaid
journey
    title Admin: System Administration
    section Login
      Open EOMS: 5: Admin
      Authenticate (admin role): 4: Admin
    section Overview
      View all trader orders: 5: Admin
      Filter by status/trader/date: 4: Admin
      Review order volumes: 4: Admin
    section User Management
      Create trader account: 4: Admin
      Set role permissions: 4: Admin
      Reset passwords: 3: Admin
    section Data Management
      View product catalogue: 5: Admin
      Update product eligibility: 4: Admin
      Review audit trail: 4: Admin
    section Design System (Epic 8)
      Open admin overlay: 4: Admin
      Inspect CSS tokens: 3: Admin
      View zone inspector: 3: Admin
```

---

## 7. End-to-End Process Flow

Full process from customer enquiry through to finance export, showing all SOP→OFM→LSC bridges.

```mermaid
flowchart LR
    subgraph SOP["SOP-ONT — Sales Order Processing"]
        direction TB
        CE[Customer Enquiry] --> SQ[Sales Quotation]
        SQ --> QL[Quotation Lines]
        QL --> OC[Order Capture]
        OC --> OV[Order Validation]
        OV --> CC[Credit Check]
    end

    subgraph FDN["Foundation — Customer Context"]
        direction TB
        CA[Customer Account] --> ORG[Organization]
        CA --> MS[Market Segment]
        CA --> CL[Competitive Landscape]
        QL2[Quotation Line] --> PR[Product Catalogue]
    end

    subgraph OFM["OFM-ONT — Order Fulfilment (future)"]
        direction TB
        SO[Sales Order] --> SLA[Service Level Agreement]
        SO --> DIS[Dispatch]
    end

    subgraph LSC["LSC-ONT — Logistics (future)"]
        direction TB
        SC[Supply Chain Corridor] --> SH[Shipment]
    end

    CC -->|"validatedOrderToFulfilment"| SO
    CA -.->|"accountMapsToOrg"| ORG
    CA -.->|"accountInSegment"| MS
    QL -.->|"quotationLineRefsProduct"| PR
    SQ -.->|"quotationRequiresLogistics"| SC
    SO -.->|"fulfilledByShipment"| SH

    style SOP fill:#19253B,color:#fff
    style FDN fill:#6B9EFE,color:#19253B
    style OFM fill:#BC4620,color:#fff
    style LSC fill:#00BCD4,color:#19253B
```

---

## 8. Data Flow: CSV Test Data → SOP Graph → Database

Shows how the 7,635 test order lines flow through the SOP graph into database tables.

```mermaid
flowchart TD
    subgraph CSV["Test Data CSV (7,635 rows × 19 columns)"]
        C1["ID, Order-Anon"]
        C2["Buyer Name Alias"]
        C3["Loading Port, Discharge Port, Country"]
        C4["Code, Description, Qty, UOM, Price, Value"]
        C5["Transport Mode, Currency"]
    end

    subgraph SOP_Graph["SOP-ONT Graph Entities"]
        E1["sop:SalesOrderProcess"]
        E2["sop:CustomerAccount"]
        E3["lsc:SupplyChain"]
        E4["sop:QuotationLine + org-ctx:Product"]
        E5["sop:SalesChannel + sop:PricingAgreement"]
    end

    subgraph DB["Supabase PostgreSQL Tables"]
        T1["orders (order_number, status, dates)"]
        T2["customers (buyer_alias, tier, segment)"]
        T3["orders (loading_port, discharge_port, country)"]
        T4["order_lines (product_code, qty, price, value)"]
        T5["orders (transport_mode, currency)"]
        T6["products (code, description, eligibility)"]
    end

    C1 --> E1 --> T1
    C2 --> E2 --> T2
    C3 --> E3 --> T3
    C4 --> E4 --> T4
    C4 -.-> T6
    C5 --> E5 --> T5

    style CSV fill:#ff9800,color:#19253B
    style SOP_Graph fill:#19253B,color:#fff
    style DB fill:#4caf50,color:#fff
```

---

## 9. Quality Gates (PE-ONT Process Gates)

Each gate maps to a PE-ONT ProcessGate entity with threshold and criteria.

```mermaid
flowchart LR
    E0[Epic 0\nFoundation] -->|"G1: Kickoff\nScope approved\nAccounts provisioned"| E1[Epic 1\nOrder Mgmt]
    E1 --> E2[Epic 2\nProducts]
    E2 --> E3[Epic 3\nExport]
    E3 -->|"G2: Core Complete\nOrder wizard works\nProduct search works\nExport generates files"| E6[Epic 6\nUAT]
    E6 -->|"G3: UAT Complete\n>90% task success\nTrader sign-off"| G4{G4: PMF}
    G4 -->|"≥80% prefer EOMS\nover Excel"| E7[Epic 7\nDeploy]
    E7 -->|"G5: Go-Live\nProduction deployed\nTeam trained\nMonitoring active"| GL[🚀 Go-Live\n18 Apr 2026]

    E8[Epic 8\nApp Framework] -.->|"tokens + zones\nfeed all UI"| E1
    E8 -.-> E2
    E8 -.-> E3

    style E0 fill:#4caf50,color:#fff
    style E1 fill:#2196f3,color:#fff
    style E2 fill:#2196f3,color:#fff
    style E3 fill:#ff9800,color:#fff
    style E6 fill:#00bcd4,color:#fff
    style E7 fill:#e91e63,color:#fff
    style E8 fill:#19253B,color:#fff
    style GL fill:#00E5CE,color:#19253B
```

---

## 10. TDD Test Generation Workflow

The PE process instance drives test-driven design. The builder reads testContracts and generates test stubs before implementation.

```mermaid
sequenceDiagram
    participant PE as PE-ONT Instance
    participant Builder as Builder Agent
    participant Tests as Test Suite
    participant Code as Application Code
    participant Gate as Process Gate

    PE->>Builder: Read Activity.stories[].testContract
    Builder->>Tests: Generate test stubs (FAILING)
    Note over Tests: Tests define expected behaviour
    Builder->>Code: Implement feature to pass tests
    Code->>Tests: Run test suite
    alt All tests pass
        Tests->>Builder: GREEN
        Builder->>PE: Mark Activity status = completed
    else Tests fail
        Tests->>Builder: RED — fix implementation
        Builder->>Code: Iterate
    end
    PE->>Gate: Check all Activities in Phase
    alt All Activities complete
        Gate->>PE: Gate PASS — progress to next phase
    else Activities incomplete
        Gate->>PE: Gate BLOCKED
    end
```

---

## 11. Zone Architecture (Application Skeleton)

How the 8 EOMS zones map to the order management process.

```mermaid
flowchart TB
    subgraph App["EOMS Application (Endeavour brand)"]
        subgraph Nav["L4-EOMS Navigation (6 items)"]
            N1[Dashboard] --> Z1
            N2[New Order] --> Z2
            N3[Products] --> Z4
            N4[Approvals] --> Z5
            N5[FX Rates] --> Z6
            N6[Settings] --> Z7
        end

        subgraph Zones["Zone Layout"]
            Z1[Z-EOMS-001\nDashboard\nFixed Center]
            Z2[Z-EOMS-002\nOrder Wizard\nFixed Center]
            Z3[Z-EOMS-003\nOrder Detail\nSliding Right]
            Z4[Z-EOMS-004\nProduct Catalogue\nSliding Right]
            Z5[Z-EOMS-005\nApproval Queue\nDeferred]
            Z6[Z-EOMS-006\nFX Management\nDeferred]
            Z7[Z-EOMS-007\nAdmin Overlay\nFloating Right]
            Z8[Z-EOMS-008\nSkeleton Inspector\nFloating Right]
        end
    end

    Z1 -.->|"F1.3: Order list"| SOP1[sop:SalesOrderProcess]
    Z2 -.->|"F1.1: Order wizard"| SOP2[sop:OrderCapture]
    Z3 -.->|"F1.3: Order detail"| SOP3[sop:OrderValidation]
    Z4 -.->|"F2.1: Product search"| OC[org-ctx:Product]

    style Z1 fill:#19253B,color:#fff
    style Z2 fill:#19253B,color:#fff
    style Z3 fill:#19253B,color:#fff
    style Z4 fill:#19253B,color:#fff
    style Z5 fill:#9e9e9e,color:#fff
    style Z6 fill:#9e9e9e,color:#fff
    style Z7 fill:#BC4620,color:#fff
    style Z8 fill:#BC4620,color:#fff
```

---

## 12. Cross-Ontology Bridge Summary

| Bridge | From | To | Direction | Phase |
|--------|------|----|-----------|-------|
| `validatedOrderToFulfilment` | `sop:OrderValidation` | `ofm:SalesOrder` | SOP → OFM | Future (OFM instances) |
| `orderSelectsSLA` | `sop:OrderCapture` | `ofm:ServiceLevelAgreement` | SOP → OFM | Future |
| `quotationRequiresLogistics` | `sop:QuotationLine` | `lsc:SupplyChain` | SOP → LSC | Future (LSC instances) |
| `accountMapsToOrg` | `sop:CustomerAccount` | `org:Organization` | SOP → ORG | Phase 1 (customers table) |
| `accountInSegment` | `sop:CustomerAccount` | `org-ctx:MarketSegment` | SOP → ORG-CTX | Phase 1 (destination_country) |
| `quotationLineRefsProduct` | `sop:QuotationLine` | `org-ctx:Product` | SOP → ORG-CTX | Phase 1 (products table) |

---

## 13. Trackable Items

| # | Item | Owner | Priority | Status | PE-ONT Ref |
|---|------|-------|----------|--------|------------|
| TI-001 | Map test customer data to SOP graph — validate DB table design | Platform | P1 | Done | `eoms-test-data-graph-mapping-v1.0.0.json` |
| TI-002 | Create PE-ONT process instance for EOMS (TDD backbone) | Platform | P1 | Done | `pe-eoms-process-instance-v1.0.0.jsonld` |
| TI-003 | Generate Supabase migration DDL from graph mapping | Dev | P1 | Pending | Table schemas in mapping doc |
| TI-004 | Create OFM instance data when SOP→OFM handoff exercised | Platform | P2 | Future | EMC instanceDataRefs[OFM] |
| TI-005 | Create LSC instance data when product catalogue defines sourcing | Platform | P2 | Future | EMC instanceDataRefs[LSC] |
| TI-006 | Resolve product catalogue stock sourcing (external LSC vs own inventory) | Product | P2 | Future | EMC composedGraphSpec.note |
| TI-007 | Generate test stubs from PE-ONT testContracts for F1.x stories | Dev | P1 | Pending | PE Activity.stories[].testContract |

---

## Appendix A: SOP Entity → DB Table Quick Reference

| SOP-ONT Entity | DB Table | Key Columns |
|---------------|----------|-------------|
| `sop:SalesOrderProcess` | `orders` | order_number, status, dates |
| `sop:CustomerAccount` | `customers` | buyer_alias, tier, segment |
| `sop:QuotationLine` | `order_lines` | product_code, qty, price, value |
| `sop:SalesChannel` | `orders` | transport_mode |
| `sop:PricingAgreement` | `orders` | currency |
| `sop:OrderValidation` | `orders` | validation_status |
| `sop:CreditCheck` | `orders` | credit_check_status |
| `org:Organization` | `organizations` | name, abn |
| `org-ctx:Product` | `products` | product_code, description, eligibility |
| `org-ctx:MarketSegment` | `orders` | destination_country |
| `lsc:SupplyChain` | `orders` | loading_port, discharge_port |
| `lsc:Shipment` | `orders` | vessel_name, voyage_number |

---

*PFI-EOMS Phase 1 — Order Management Process Workflow v1.0.0*
*PE-ONT Process Instance: `pe-eoms-process-instance-v1.0.0.jsonld`*
*10 March 2026*
