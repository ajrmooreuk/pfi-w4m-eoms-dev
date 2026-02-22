# EOMS TERMS SHEET
## Commercial Terms — Phase 1 MVP

---

| Document Control | |
|-----------------|---|
| **Document Number** | EOMS-TS-001 |
| **Version** | 0.1 — DRAFT |
| **Status** | For Agreement |
| **Date** | [DATE] |
| **Related SOW** | EOMS_STATEMENT_OF_WORK_v0.1.md |
| **Classification** | Commercial in Confidence |

---

## 1. PARTIES

| | |
|---|---|
| **Client** | [CLIENT LEGAL ENTITY NAME] (ABN: [CLIENT ABN]) |
| **Adviser** | [ADVISER LEGAL ENTITY NAME] (ABN: [ADVISER ABN]) |

---

## 2. PRICING MODEL

### 2.1 Phase 1 MVP — Fixed Price

| Item | Amount ([CURRENCY]) |
|------|---:|
| **Phase 1 MVP — Design, Build, Deploy** | [TOTAL PRICE — e.g., $22,000 AUD] |

**Billing currency:** [AUD / GBP — confirm]
**Exchange rate basis (if applicable):** [RATE OR METHOD — e.g., XE mid-rate on invoice date]

### 2.2 What the Fixed Price Covers

All work described in SOW Section 3.1 (Deliverables D1–D12), including:

- Requirements clarification and scope refinement
- Figma design system creation and mockups
- Full-stack development (frontend, backend, database, AI integration)
- UAT facilitation and bug fixing
- Documentation and handover
- [DURATION — e.g., 2 weeks] post-go-live stabilisation support

### 2.3 What the Fixed Price Does NOT Cover

| Item | Responsibility | Notes |
|------|---------------|-------|
| Infrastructure subscriptions (Supabase, Vercel, Anthropic API, domain) | Client | See SOW Section 8.3 for estimates |
| Client staff time for UAT, data provision, meetings | Client | Expected: [HOURS — e.g., 20–30 hours total] |
| Phase 2+ development | Separate SOW | To be quoted |
| Post-stabilisation support | By agreement | See Section 6 below |

---

## 3. PAYMENT SCHEDULE

### 3.1 Milestone-Based Payments

Payments are linked to delivery gates defined in the SOW. Each payment becomes due upon Client approval of the relevant gate.

| # | Milestone | Trigger | Amount | % |
|---|-----------|---------|-------:|---:|
| M1 | **Project Kickoff** | SOW signed, kickoff completed | [AMOUNT — e.g., $6,600] | [% — e.g., 30%] |
| M2 | **G2: MVP Feature Complete** | Core modules functional in staging | [AMOUNT — e.g., $8,800] | [% — e.g., 40%] |
| M3 | **G5: Go-Live** | Production deployed, handover complete | [AMOUNT — e.g., $6,600] | [% — e.g., 30%] |
| | **Total** | | **[TOTAL PRICE]** | **100%** |

### 3.2 Alternative Payment Structures (For Discussion)

**Option A — Three milestones (recommended)**
As above: 30% / 40% / 30%

**Option B — Monthly billing**

| Month | Amount | % |
|-------|-------:|---:|
| Month 1 (Weeks 1–4) | [AMOUNT] | 35% |
| Month 2 (Weeks 5–8) | [AMOUNT] | 40% |
| Month 3 (Weeks 9–12) | [AMOUNT] | 25% |

**Option C — Gate-by-gate (5 payments)**

| Gate | Amount | % |
|------|-------:|---:|
| G1: POC Demo | [AMOUNT] | 15% |
| G2: Feature Complete | [AMOUNT] | 30% |
| G3: AI Operational | [AMOUNT] | 20% |
| G4: UAT Sign-off | [AMOUNT] | 20% |
| G5: Go-Live | [AMOUNT] | 15% |

**Agreed structure:** [OPTION A / B / C — to be confirmed]

### 3.3 Payment Terms

| Term | Detail |
|------|--------|
| **Invoice timing** | Invoiced upon gate approval |
| **Payment due** | [DAYS — e.g., 14 / 30] days from invoice date |
| **Payment method** | [BANK TRANSFER / OTHER] |
| **Late payment** | [LATE PAYMENT TERMS — e.g., Interest at RBA cash rate + 2% per annum on overdue amounts] |
| **Disputed invoices** | Undisputed portions payable on time; disputed portions resolved within [DAYS] working days |

---

## 4. INTELLECTUAL PROPERTY

### 4.1 Ownership of Deliverables

| Asset | Ownership | Notes |
|-------|-----------|-------|
| **EOMS application code** | [CLIENT / ADVISER / JOINT — recommend: CLIENT] | All custom code written for this project |
| **Database schemas & data models** | [CLIENT] | Including ontology definitions |
| **Figma design system (Endeavour-DS)** | [CLIENT] | Design tokens, components, mockups |
| **Client data** | Client | Product catalogue, customer data, orders |
| **Documentation** | [CLIENT] | User guide, API docs, handover materials |

### 4.2 Pre-Existing IP

| Asset | Ownership | Licence |
|-------|-----------|---------|
| **Open-source libraries** (Next.js, shadcn/ui, Tailwind, Supabase SDK, etc.) | Respective owners | Per their open-source licences (MIT, Apache 2.0) |
| **Claude API / Anthropic SDK** | Anthropic | Per Anthropic Terms of Service |
| **Adviser's proprietary frameworks, methods, or templates** (if any) | Adviser | [LICENCE GRANT — e.g., Perpetual, non-exclusive licence to Client for use within EOMS] |
| **PF-Core Agent Framework** (if used) | [OWNER] | [LICENCE TERMS] |

### 4.3 IP Transfer Timing

- IP in deliverables transfers to Client upon **payment of the corresponding milestone**
- Upon final payment (M3/G5), Client holds full ownership of all custom deliverables
- Pre-existing IP licences are perpetual and survive termination

### 4.4 Source Code Access

| Provision | Detail |
|-----------|--------|
| **Repository** | Code maintained in [PLATFORM — e.g., GitHub] repository |
| **Client access** | [FULL ACCESS / READ-ONLY — recommend: FULL ACCESS from Day 1] |
| **Handover** | Full repository transferred to Client-owned account at G5 |
| **No lock-in** | Client is free to engage any party to maintain or extend the system after handover |

---

## 5. CONFIDENTIALITY

### 5.1 Confidential Information

Each party agrees to treat as confidential:

| Party | Confidential Information |
|-------|------------------------|
| **Client** | Business data, customer information, pricing, product codes, FX contracts, internal processes |
| **Adviser** | Proprietary methods, pricing structures, client lists |

### 5.2 Obligations

- Confidential information shall not be disclosed to third parties without written consent
- Information shall be used only for the purpose of this project
- Obligations survive for [PERIOD — e.g., 2 years] after termination
- Exceptions: publicly available information, independently developed, required by law

---

## 6. POST-GO-LIVE SUPPORT

### 6.1 Stabilisation Period (Included)

| Item | Detail |
|------|--------|
| **Duration** | [DURATION — e.g., 2 weeks] from go-live date |
| **Coverage** | P1 and P2 defect resolution |
| **Availability** | [HOURS — e.g., Business hours AEST, Monday–Friday] |
| **Cost** | Included in fixed price |

### 6.2 Ongoing Support (If Required — Separate Agreement)

| Option | Description | Rate |
|--------|-------------|------|
| **Ad-hoc support** | Billed per incident or per hour | [HOURLY RATE — e.g., $[RATE]/hour] |
| **Monthly retainer** | [HOURS — e.g., 10 hours/month] support allocation | [MONTHLY RATE — e.g., $[RATE]/month] |
| **Managed service** | Full application support and maintenance | [TO BE QUOTED] |

*Post-stabilisation support is optional and will be agreed separately if required.*

---

## 7. DATA HANDLING

| Item | Provision |
|------|-----------|
| **Data residency** | Australian data sovereignty — Supabase Sydney region |
| **Data ownership** | All Client data remains the property of the Client at all times |
| **Data access** | Adviser access limited to project duration + stabilisation period |
| **Data deletion** | Adviser will delete all Client data from non-production environments within [DAYS — e.g., 30] days of project completion |
| **Backups** | Supabase automated backups; Client responsible for backup policy post-handover |

---

## 8. FUTURE PHASES

### 8.1 Phase 2+ Indicative Scope

The following capabilities are anticipated for future phases (subject to separate SOW):

| Phase | Capability | Indicative Investment |
|-------|-----------|----------------------|
| Phase 2 | Domestic market, advanced analytics, Excel export | [TO BE QUOTED] |
| Phase 3 | ERP integration, batch processing, advanced AI | [TO BE QUOTED] |
| **3-Year Total (indicative)** | All phases | ~[TOTAL — e.g., $70,000 AUD] |

### 8.2 No Obligation

This Terms Sheet covers Phase 1 only. There is no obligation on either party to proceed with future phases.

---

## 9. GENERAL TERMS

| Term | Provision |
|------|-----------|
| **Governing law** | [JURISDICTION — e.g., Laws of Queensland, Australia / Laws of England and Wales] |
| **Dispute resolution** | [METHOD — e.g., Good faith negotiation → Mediation → Courts of [JURISDICTION]] |
| **Force majeure** | Neither party liable for delays caused by events beyond reasonable control |
| **Entire agreement** | This Terms Sheet, the SOW, and referenced supporting documents constitute the entire agreement |
| **Amendments** | Amendments must be in writing and signed by both parties |
| **Assignment** | Neither party may assign without written consent |
| **Severability** | If any provision is found invalid, the remainder continues in effect |
| **Notices** | Written notices to the authorised representatives listed in the SOW |

---

## 10. AGREEMENT

By signing below, the parties agree to the commercial terms described in this Terms Sheet, to be read in conjunction with the Statement of Work (EOMS-SOW-001).

### Client

| | |
|---|---|
| Signed | _________________________ |
| Name | [CLIENT AUTHORISED REP NAME] |
| Title | [CLIENT AUTHORISED REP TITLE] |
| Date | [DATE] |

### Adviser

| | |
|---|---|
| Signed | _________________________ |
| Name | [ADVISER AUTHORISED REP NAME] |
| Title | [ADVISER AUTHORISED REP TITLE] |
| Date | [DATE] |

---

**--- END OF TERMS SHEET ---**

*Version 0.1 — DRAFT | For Agreement*
*[DATE]*
