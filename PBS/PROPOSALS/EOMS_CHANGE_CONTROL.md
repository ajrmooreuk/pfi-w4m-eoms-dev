# EOMS CHANGE CONTROL REGISTER
## PRD & Proposal Alignment

---

| Document Control | |
|-----------------|---|
| **Document Number** | EOMS-CC-001 |
| **Version** | 1.0 |
| **Status** | EXECUTED |
| **Date** | 26 January 2026 |
| **Purpose** | Track proposed changes to PRD for alignment with Proposal v2.1 |

---

## 1. CHANGE CONTROL SUMMARY

This document tracks proposed changes to align EOMS_PRD_UNIFIED_v1.1.md with EOMS_PROPOSAL_v2.1.md before execution.

**Target Document:** EOMS_PRD_UNIFIED_v1.1.md → **EOMS_PRD_UNIFIED_v1.5.md** ✓
**Reference Document:** EOMS_PROPOSAL_v2.1.md

---

## 2. PROPOSED CHANGES REGISTER

| CC# | Document | Section | Change Type | Current State | Proposed Change | Priority | Status |
|-----|----------|---------|-------------|---------------|-----------------|----------|--------|
| **PRD CHANGES** |||||||
| CC-001 | PRD | 1.1 | ADD | No revenue context | Add $600M current, $1.2Bn target context | Medium | **COMPLETED** |
| CC-002 | PRD | 1.1 | ADD | No risk scale | Add $200K-$300K per container risk context | Medium | **COMPLETED** |
| CC-003 | PRD | 1.3 | MOVE | Investment table in body | Move investment details to new Appendix | High | **COMPLETED** |
| CC-004 | PRD | 2.1 | MOVE | Business case in body | Move detailed ROI to Appendix, keep summary | High | **COMPLETED** |
| CC-005 | PRD | 2.2 | UPDATE | Benefit figures differ | Align 3-year benefit figures | Medium | **COMPLETED** |
| CC-006 | PRD | PBS 4.1.3 | UPDATE | "Halal Compliance Check" | Change to "Compliance Policy Check" | High | **COMPLETED** |
| CC-007 | PRD | PBS 4.0 | ADD | No pattern recognition | Add PBS 4.6 "Pattern Recognition Agent" | Medium | **COMPLETED** |
| CC-008 | PRD | 1.3 | UPDATE | "x days within 3 months" | Update to "8-12 weeks elapsed" | Low | **COMPLETED** |
| CC-009 | PRD | NEW | ADD | No Epics/Features/Stories | Add Section: Epics, Features & User Stories | High | **COMPLETED** |
| CC-010 | PRD | Appendix | ADD | No cost appendix | Create Appendix: Investment & ROI | High | **COMPLETED** |
| **PROPOSAL CHANGES** |||||||
| CC-011 | Proposal | 1 Exec | UPDATE | $92K 3-year investment | Update to ~$70K (AI-assisted) | High | **COMPLETED** |
| CC-012 | Proposal | 1 Exec | UPDATE | ~40x ROI | Update to ~52x ROI | High | **COMPLETED** |
| CC-013 | Proposal | 1 Exec | UPDATE | ~25 days payback | Update to ~9 days payback | High | **COMPLETED** |
| CC-014 | Proposal | 4.4 | UPDATE | Traditional options focus | Focus on AI-assisted, traditional as reference | High | **COMPLETED** |
| CC-015 | Proposal | App D | UPDATE | Traditional costing | Update to AI-assisted costing | High | **COMPLETED** |
| **PRD v1.3 CHANGES** |||||||
| CC-016 | PRD | Multiple | UPDATE | Halal-specific references | Generalise to EOMS Compliance Audit | High | **COMPLETED** |
| CC-017 | PRD | 3.4 | ADD | No VSOM framework | Add Vision, Strategy, Objectives & Metrics | High | **COMPLETED** |
| CC-018 | PRD | 3.5 | ADD | No value proposition | Add structured value proposition statement | Medium | **COMPLETED** |
| CC-019 | PRD | 3.6 | ADD | No internal PMF | Add Internal Product-Market Fit measurement | High | **COMPLETED** |
| **PRD v1.4 CHANGES** |||||||
| CC-020 | PRD | Multiple | ADD | ASCII/text diagrams | Add Mermaid visual diagrams throughout PRD | Medium | **COMPLETED** |
| **PRD v1.5 CHANGES** |||||||
| CC-021 | PRD | 3.6 | UPDATE | PMF ASCII diagram | Convert PMF Validation Cycle to Mermaid diagram | Low | **COMPLETED** |
| CC-022 | PRD | Part 2 | REORDER | PBS precedes Epics | Move Epics/Features/Stories BEFORE PBS section | High | **COMPLETED** |
| CC-023 | PRD | Architecture | ADD | No system architecture diagram | Add Mermaid architecture/C4 diagram | Medium | **SUPERSEDED by CC-030** |
| CC-024 | PRD | Appendix | ADD | No ontology framework | Add Ontology Library with OAA (Ontology Architect Agent) | High | **COMPLETED** |
| CC-025 | PRD | Appendix | ADD | No artifact register | Add Unified Register of Artifacts Ontology | High | **COMPLETED** |
| CC-026 | PRD | Design | UPDATE | Hardcoded design values | Reference Design System Ontology (Endeavour-DS) | High | **COMPLETED** |
| CC-027 | PRD | Multiple | REMOVE | Specific timeline references | Remove days/weeks, reference Implementation Plan & WBS | Medium | PARTIAL |
| CC-028 | PRD | UI/UX | CONSOLIDATE | Detailed design specs | Consolidate to external Design System document | Medium | PARTIAL |
| CC-029 | PRD | Implementation | EXTRACT | Implementation details in PRD | Create separate Implementation Plan & References document | High | **COMPLETED** |
| CC-030 | NEW | Architecture | CREATE | No HLD document | Create separate EOMS_HLD.md (High-Level Design) | High | **COMPLETED** |
| CC-031 | HLD | Section 4.1 | FIX | Mermaid render failure | Fix API path syntax in Architecture Overview diagram | Low | **COMPLETED** |
| CC-032 | NEW | std-docs | CREATE | No document register | Create EOMS_DOCUMENT_CONTROL_REGISTER.md | Medium | **COMPLETED** |
| CC-033 | NEW | std-docs | ADD | No inventory prompt | Add file-inventory-prompt.md from PF-Core-BAIV | Low | **COMPLETED** |
| CC-034 | NEW | std-docs | CREATE | No unified register | Create Unified Register process doc and JSON ontology | High | **COMPLETED** |
| CC-035 | NEW | PROPOSALS | CREATE | No team-shareable register | Create minimal EOMS_DOCUMENT_REGISTER.md for team sharing | Low | **COMPLETED** |
| CC-036 | NEW | std-docs | CREATE | No workflow documentation | Create EOMS_CC_GITHUB_WORKFLOW.md for CC→Issues→Kanban integration | Medium | **COMPLETED** |
| CC-037 | std-docs | EOMS-STD-005 | UPDATE | No change request gate | Add Definition of Ready: Value/Done/Works checklist | Medium | **COMPLETED** |
| CC-038 | std-docs | EOMS-STD-005 | FIX | Mermaid syntax error | Fix stateDiagram-v2 note text colon parsing in Section 5 | Low | **COMPLETED** |
| **PRD v1.6 SCOPE CLEANUP** |||||||
| CC-039 | PRD | Appendix C | SIMPLIFY | Detailed Investment appendix | Reference Proposal, remove detail | Medium | **COMPLETED** |
| CC-040 | PRD | Section 7 | CONSOLIDATE | Detailed Tech Architecture | Summary + HLD cross-reference | Medium | **COMPLETED** |
| CC-041 | PRD | Section 8 + Appendix D | MOVE | Detailed Ontology schemas | Move to HLD Appendices C & D | High | **COMPLETED** |
| CC-042 | PRD | Sections 9-11 | MOVE | Detailed Design System/Figma | Move to HLD Appendix E + Impl Plan Appendix C | High | **COMPLETED** |
| CC-043 | PRD | Sections 12-13 | MOVE | Detailed Dev Guide/WBS | Move to Implementation Plan Appendices A & B | High | **COMPLETED** |
| **PRD v1.7 REVIEW & ENHANCEMENT** |||||||
| CC-044 | PRD | TOC | UPDATE | TOC reflects old structure | Update TOC with cross-refs, NFR section, RRR subsections | Medium | **COMPLETED** |
| CC-045 | PRD | Section 16 | ADD | Basic RACI only | Add RRR Framework (Roles/Responsibilities/RBAC), authority levels, cascading hierarchy | High | **COMPLETED** |
| CC-046 | PRD | Section 6 | ADD | No NFRs | Add Non-Functional Requirements (Performance, Security, Availability, Scalability, Compliance, Usability) | High | **COMPLETED** |
| CC-047 | PRD | Section 2 | VERIFY | Business Case figures | Cross-check Business Case with Proposal - VERIFIED consistent | Low | **COMPLETED** |
| CC-048 | PRD | Multiple | ADD | Missing section context | Add introductory paragraphs to sections, fix section numbering (14.x, 15.x, 16.x) | Medium | **COMPLETED** |

---

## 3. DETAILED CHANGE DESCRIPTIONS

### CC-001: Add Revenue Context
**Location:** Section 1.1 Business Problem
**Rationale:** Proposal v2.1 includes strategic context of $600M current revenue and $1.2Bn target
**Impact:** Low - Adds context, no functional change

### CC-002: Add Risk Scale Context
**Location:** Section 1.1 Business Problem
**Rationale:** Proposal emphasises $200K-$300K per container to quantify error impact
**Impact:** Low - Adds context, no functional change

### CC-003: Move Investment to Appendix
**Location:** Section 1.3 → New Appendix A
**Rationale:** PRD is a product statement, not a business case. Investment details belong in appendix.
**Impact:** Medium - Restructure, keep summary reference in body

### CC-004: Move ROI Details to Appendix
**Location:** Section 2.1/2.2 → Appendix A
**Rationale:** Detailed ROI calculations should be appendix material
**Impact:** Medium - Restructure, keep summary in body

### CC-005: Align Benefit Figures
**Location:** Section 2.2 Key Benefit Categories
**Current:**
| Category | Annual Benefit | 3-Year Total |
|----------|---------------:|-------------:|
| Error Reduction | $301,000 | $903,000 |
| Labour Efficiency | $153,000 | $459,000 |
| Capacity Enablement | $600,000 | $1,800,000 |
| Onboarding Acceleration | $37,100 | $111,300 |
| Customer Retention | $200,000 | $600,000 |
| Margin Protection | $220,500 | $661,500 |

**Proposal v2.1 (3-Year):**
| Category | 3-Year Value |
|----------|-------------:|
| Error Reduction | $1,947,000 |
| Labour Efficiency | $1,833,000 |
| Capacity Enablement | $500,000 |
| Faster Onboarding | $225,000 |
| Customer Retention | $562,500 |
| Margin Protection | $1,056,000 |

**Action:** Verify source and align figures

### CC-006: Update Compliance Check Naming
**Location:** PBS 4.1.3
**Current:** "PBS 4.1.3 Halal Compliance Check"
**Proposed:** "PBS 4.1.3 Compliance Policy Check"
**Rationale:** Generic compliance policy is more flexible than Halal-specific
**Impact:** Medium - Requires review of compliance requirements

### CC-007: Add Pattern Recognition Agent
**Location:** PBS 4.0 AI Agent Layer
**Proposed Addition:**
```
+-- PBS 4.6 Pattern Recognition Agent
    +-- PBS 4.6.1 Customer Reordering Patterns
    +-- PBS 4.6.2 Product Combination Analysis
    +-- PBS 4.6.3 Smart Data Entry Acceleration
```
**Rationale:** Proposal v2.1 includes "Customer-Aware Reordering" capability
**Impact:** Medium - New functionality scope

### CC-008: Update Timeline Reference
**Location:** Section 1.3 Investment table
**Current:** "x days within 3 months"
**Proposed:** "8-12 weeks elapsed"
**Rationale:** Align with Proposal timeline
**Impact:** Low - Editorial

### CC-009: Add Epics, Features & User Stories Section
**Location:** New Section (suggest Part 2, Section 4.2)
**Rationale:** PRD lacks agile hierarchy that forms basis for implementation plan
**Proposed Structure:**
```
## 4.2 Epics, Features & User Stories

### Epic 1: Order Management
- Feature 1.1: Order Creation Wizard
  - US-1.1.1: As a trader, I can create a new order...
  - US-1.1.2: As a trader, I can search products...
- Feature 1.2: Order Line Items
  - US-1.2.1: As a trader, I can add products to order...

### Epic 2: Product Catalogue
- Feature 2.1: Product Search
  - US-2.1.1: As a trader, I can search 7,816 products...

### Epic 3: AI Validation
- Feature 3.1: Automated Validation
  - US-3.1.1: As a trader, I receive AI validation feedback...

[etc.]
```
**Impact:** High - Significant new content, improves implementation clarity

### CC-010: Create Investment & ROI Appendix
**Location:** New Appendix A
**Content:** Move all investment/ROI details from body to appendix
**Costing Model:** AI-assisted development (~$20K AUD / £10K GBP)
**Impact:** High - Restructure

### CC-021: Convert PMF Validation Cycle to Mermaid (PROPOSED)
**Location:** Section 3.6 Internal Product-Market Fit
**Current:** ASCII box diagram showing Build-Measure-Learn cycle
**Proposed:** Convert to Mermaid flowchart with:
- Circular Build → Measure → Learn cycle
- Feedback channels subgraph
- Change verification process subgraph
**Rationale:** Consistency with other Mermaid diagrams in PRD v1.4
**Impact:** Low - Visual enhancement only

### CC-022: Reorder Epics/Features/Stories Before PBS (FOR REVIEW)
**Location:** Part 2 - Product Requirements
**Current Structure:**
```
Part 2: Product Requirements
├── 4.1 PBS (Product Breakdown Structure)
├── 4.2 Epics, Features & User Stories
├── 4.3 Functional Requirements
└── ...
```
**Proposed Structure:**
```
Part 2: Product Requirements
├── 4.1 Epics, Features & User Stories (WHAT we want - user perspective)
├── 4.2 PBS (Product Breakdown Structure) (HOW we structure components)
├── 4.3 Functional Requirements
└── ...
```
**Rationale:**
- Logical flow: Define goals (Epics) → Break down structure (PBS)
- User-centric requirements should drive technical breakdown
- Aligns with agile practice: Stories → Technical Design
**Impact:** High - Document restructure, section renumbering required
**Discussion Points:**
- Does current PBS reference Epics that don't exist yet in reading order?
- Should PBS items map explicitly to Features/Stories?
- Impact on existing cross-references

### CC-023: Add System Architecture Diagram (PROPOSED)
**Location:** Technical Architecture section (Part 2)
**Current:** Text description of architecture layers
**Proposed:** Add Mermaid architecture diagram showing:
- User Interface Layer (React/Next.js)
- Application Layer (API routes, business logic)
- AI Agent Layer (Claude integration, validation, skills)
- Data Layer (Supabase, product catalogue)
- External Integrations (O365 SSO, export services)
**Diagram Type Options:**
- `flowchart` - Layer hierarchy with connections
- `C4Context` - System context diagram (users, systems, boundaries)
- `C4Container` - Container-level detail (apps, databases, APIs)
**Rationale:** Visual representation aids developer onboarding and stakeholder communication
**Impact:** Medium - New content, improves technical clarity

### CC-024: Add Ontology Library with OAA (PROPOSED)
**Location:** New Appendix - Ontology Framework
**Proposed:** Establish Ontology Library managed by OAA (Ontology Architect Agent)
**Purpose:** Ensure competency and design consistency across all system ontologies
**OAA Responsibilities:**
- Ontology design review and validation
- Semantic consistency across domains
- Version control and evolution management
- Integration patterns between ontologies
**Impact:** High - Foundational framework for AI-driven system design

### CC-025: Unified Register of Artifacts Ontology (PROPOSED)
**Location:** Appendix - Ontology Library
**Proposed Ontologies:**
| Ontology | Purpose |
|----------|---------|
| **Value Engineering** | Benefits, ROI, cost models, value streams |
| **ORG Context** | Organisation structure, AI context, capabilities |
| **Market/Process** | Business processes, market dynamics, products |
| **RRR (Roles/RACI/RBAC)** | Role definitions, responsibilities, access control |
| **Security/Compliance** | MCSB compliance, OWASP AI Top 10 risks |
**Rationale:** Single source of truth for all system artifacts and governance
**Impact:** High - Enterprise architecture foundation

### CC-026: Design System Ontology Reference (PROPOSED)
**Location:** Design/UI sections throughout PRD
**Current:** Hardcoded design values, detailed component specs
**Proposed:**
- Reference external Design System Ontology (Endeavour-DS)
- Limit PRD to HLD reference only
- Best practices statement for branded SHADCN-compliant design system
**Endeavour-DS Structure:**
```
Endeavour-DS/
├── Primitives (colours, spacing, typography)
├── Semantic Tokens (intent-based: primary, secondary, error)
└── Component Tokens (button, input, card specifications)
```
**Benefits:**
- Single source of truth for all Endeavour applications
- Consistent branding across apps and marketing materials
- Decoupled from PRD for independent evolution
**Impact:** High - Removes detail, adds maintainability

### CC-027: Remove Specific Timeline References (PROPOSED)
**Location:** Multiple sections in PRD body
**Current:** References to specific days, weeks (e.g., "Weeks 3-6", "8-12 weeks")
**Proposed:** Replace with:
- "See Implementation Plan and Schedule"
- "Per WBS timeline"
- "As per project schedule"
**Rationale:**
- Timelines change; PRD should be stable
- Implementation Plan is the authoritative schedule source
- GitHub Kanban board will be generated from WBS
**Impact:** Medium - Editorial, improves document longevity

### CC-028: Consolidate Design/UI/UX Details (PROPOSED)
**Location:** UI/UX specifications throughout PRD
**Current:** Detailed design specs, component lists, styling details
**Proposed:**
- Move detailed specs to external Design System document
- PRD retains only functional requirements
- Reference standard skills for implementation
**Consolidation Target:** External documents:
- Endeavour-DS (Design System Ontology)
- Implementation Playbook (detailed specs)
- Standard Skills library
**Rationale:** PRD scope is product definition, not implementation detail
**Impact:** Medium - Reduces PRD size, improves focus

### CC-029: Extract Implementation Plan & References (PROPOSED)
**Location:** Implementation/timeline sections in PRD
**Proposed:** Create separate document: `EOMS_IMPLEMENTATION_PLAN.md`
**Document Structure:**
```
EOMS_IMPLEMENTATION_PLAN.md
├── 1. WBS (Work Breakdown Structure)
├── 2. Schedule & Milestones
├── 3. GitHub Kanban Board Setup
├── 4. Resource Assignments
├── 5. Dependencies & Critical Path
└── 6. References & External Documents
```
**PRD Retains:**
- High-level scope statement
- Reference to Implementation Plan document
- Success criteria and acceptance gates
**Rationale:**
- Separation of concerns (What vs How vs When)
- Implementation details change frequently
- Enables independent schedule updates
- GitHub Kanban generated from WBS in this document
**Impact:** High - Document restructure, improves maintainability

### CC-031: Fix HLD Section 4.1 Mermaid Syntax
**Location:** EOMS_HLD.md Section 4.1 Architecture Overview
**Issue:** Mermaid diagram fails to render in GitHub/VS Code
**Root Cause:** API paths `/api/orders` interpreted as parallelogram shape syntax
**Fix:** Quote all API path labels: `API1["/api/orders"]`
**Impact:** Low - Bug fix, no functional change

### CC-032: Create Document Control Register
**Location:** std-docs/EOMS_DOCUMENT_CONTROL_REGISTER.md
**Purpose:** Unified register for all EOMS design and build artifacts
**Content:**
- Document inventory with versions and status
- Document hierarchy visualisation
- Version control policy
- Approval matrix
- Change Control integration
- File inventory integration for JSON ontology migration
**Impact:** Medium - Governance improvement

### CC-033: Add File Inventory Prompt
**Location:** std-docs/file-inventory-prompt.md
**Source:** TeamBAIV/PF-Core-BAIV/PBS/DOCS/file-inventory-prompt.md
**Purpose:** Standard prompt for generating file inventories without reading content
**Future Use:** Feed into JSON ontologies for automated document tracking
**Impact:** Low - Standard tooling addition

### CC-038: Fix Mermaid stateDiagram-v2 Syntax
**Location:** std-docs/EOMS_CC_GITHUB_WORKFLOW.md Section 5 (Item Lifecycle)
**Issue:** Mermaid diagram fails to render - parse error on line 12
**Root Cause:** Colons in note text interpreted as Mermaid syntax separator
**Current:** `note right of In_Progress: Kanban: In Progress`
**Fixed:** `note right of In_Progress: Kanban - In Progress`
**Impact:** Low - Bug fix, no functional change

### CC-049: Phase 1 Re-Scoping — Order Entry Foundation
**Location:** All documents
**Date:** 19 February 2026
**Rationale:** Client feedback from James (CEO) and Anthony (CFO/acting COO) — Phase 1 scope is broader than what they want at this stage. They want to prove workflow efficiency first with a simple, focused order entry system before layering intelligence and automation. Both are new to digital transformation and want a contained, low-risk first step.
**Scope Change:**
- **IN:** Order entry wizard, product search (7,816+ codes), customer/buyer/consignee lookup, supplier/establishment selection, shipping details, Draft→Complete→Exported lifecycle, finance-ready export, basic auth, order list view
- **OUT (deferred):** AI agents, FX integration, margin thresholds, approval workflows, dashboards, analytics, compliance automation, pattern recognition, PF-Core framework
**Impact:** Critical — affects all 4 core documents. New versions created for each.
**Narrative:** "Phase 1 builds the data foundation and workflow engine. Prove the efficiency gain first, then add intelligence."

### CC-050: Proposal v2.1 → v3.0
**Location:** EOMS_PROPOSAL_v3.0.md
**Date:** 19 February 2026
**Key Changes:** Reframed from "AI-augmented order management" to "order entry foundation replacing spreadsheets". All AI/FX/dashboard language removed. Benefits recalculated: labour efficiency (55-65% time reduction) and error reduction (<3% error rate) as primary categories. Margin Protection deferred. Operating costs ~$50/month (no Claude API). Explicit "Deferred to Future Phases" table added.
**Impact:** Critical — sign-off document for this-week decision

### CC-051: PRD v1.7 → v2.0
**Location:** EOMS_PRD_UNIFIED_v2.0.md
**Date:** 19 February 2026
**Key Changes:** Reduced from 5 epics to 3 (Order Management, Product Catalogue, Order Export to Finance). PBS simplified — removed PBS 4.0 (AI Layer) entirely. Order lifecycle simplified from 8-state to 3-state (Draft→Complete→Exported). MoSCoW re-prioritised with explicit WON'T list. Data model adds EXPORT_LOG, removes FX_CONTRACT. RBAC simplified to 3 roles.
**Impact:** Critical — scope definition

### CC-052: HLD v1.0 → v2.0
**Location:** EOMS_HLD_v2.0.md
**Date:** 19 February 2026
**Key Changes:** Removed Section 6 (AI Agent Architecture) entirely. Claude SDK and PF-Core removed from technology stack. Architecture simplified to Users→Frontend→API→Supabase. Order schema simplified (removed fx/compliance JSONB, status enum now draft/complete/exported). Order export format specification added to Integration Architecture. Appendix D (Ontology Library) removed. Design decisions DD-006 and DD-007 added.
**Impact:** Critical — technical architecture

### CC-053: Implementation Plan v1.0 → v2.0
**Location:** EOMS_IMPLEMENTATION_PLAN_v2.0.md
**Date:** 19 February 2026
**Key Changes:** WBS 4.0 (AI Integration) removed entirely. Dashboard module (WBS 3.3.2), FX API (WBS 3.4.3), approval module removed. Order export tasks added (WBS 3.3.7, 3.4.4). Milestones reduced from G0-G5 to G0-G4 (removed G3 AI Integration). Anthropic API dependency removed. Order export format spec from Endeavour IT added as new dependency.
**Impact:** Critical — delivery plan

### CC-054: Order Export to Finance Promoted to Core
**Location:** All documents
**Date:** 19 February 2026
**Rationale:** Client identified clean finance-ready export as critical Phase 1 deliverable — the order data needs to flow back into their existing finance system.
**Change:** Order export (CSV/JSON) moved from future phase to Phase 1 core. New Epic 3 (Order Export to Finance) in PRD, new FR-EXP-001, new WBS tasks, new HLD integration architecture section.
**Impact:** High — new core requirement

### CC-055: Benefit Recalculation
**Location:** Proposal v3.0
**Date:** 19 February 2026
**Previous:** 6 benefit categories with AI-driven claims (87% time reduction, <1% error rate)
**Current:** 2 primary categories — Labour Efficiency (55-65% time reduction) and Error Reduction (<3% error rate). Conservative assumptions without AI-driven benefits. Margin Protection and Capacity Enablement explicitly deferred to future phases.
**Impact:** High — investment justification

### CC-056: Formal Deferral Register
**Location:** All documents
**Date:** 19 February 2026
**Items Deferred:** AI validation agents (Order Validation, Pricing, Compliance, Pattern Recognition, Margin, Market Eligibility), FX contract integration & currency conversion, margin threshold recognition, approval workflows & authority matrix, dashboards (Trader, Executive, Finance), analytics/KPIs/trend charts, advanced compliance automation, pattern recognition/smart reordering, PF-Core agent framework/OAA
**Rationale:** Client wants to prove workflow efficiency first. Foundation is deliberately designed so deferred items can be layered on in future phases with minimal rework.
**Impact:** High — formal scope boundary

### CC-039: Simplify Investment Appendix
**Location:** PRD Appendix C
**Change:** Removed detailed investment/ROI tables, replaced with summary + Proposal reference
**Rationale:** Investment details already exist in EOMS_PROPOSAL_v2.1.md - avoid duplication
**Impact:** Medium - Reduces PRD size, improves single source of truth

### CC-040: Consolidate Technical Architecture
**Location:** PRD Section 7
**Change:** Replaced detailed architecture with summary + HLD cross-reference
**Rationale:** HLD contains comprehensive architecture - PRD needs only summary
**Impact:** Medium - Improves document separation of concerns

### CC-041: Move Ontology Schemas to HLD
**Location:** PRD Section 8 (JSON schemas) + Appendix D (Ontology Library Framework)
**Target:** EOMS_HLD.md Appendices C & D
**Change:** Moved detailed JSON schema definitions and OAA framework to HLD
**Rationale:** Technical specifications belong in HLD, not PRD
**Impact:** High - Major content restructure

### CC-042: Move Design System/Figma to HLD
**Location:** PRD Sections 9-11 (Design System, MVP Prototype, Figma Implementation)
**Target:** EOMS_HLD.md Appendix E + EOMS_IMPLEMENTATION_PLAN.md Appendix C
**Change:** Moved colour tokens, typography, Figma implementation steps
**Rationale:** Design specifications belong in HLD; implementation steps belong in Impl Plan
**Impact:** High - Major content restructure

### CC-043: Move Dev Guide/WBS to Implementation Plan
**Location:** PRD Sections 12-13 (Development Guide, WBS detailed breakdown)
**Target:** EOMS_IMPLEMENTATION_PLAN.md Appendices A & B
**Change:** Moved bash commands, code snippets, detailed WBS tree
**Rationale:** Implementation details belong in Implementation Plan, not PRD
**Impact:** High - Major content restructure, PRD now focuses on WHAT not HOW/WHEN

### CC-034: Create Unified Register Process & JSON
**Location:** std-docs/EOMS_UNIFIED_REGISTER_PROCESS.md, std-docs/eoms_unified_register.json
**Based On:** PF-Core-BAIV Registry 4.0.0 pattern (simplified)
**Purpose:** Connect Change Control → Document Register → Unified Register
**Deliverables:**
- Process document defining CC→DCR→Register flow
- Simplified JSON schema for EOMS artifacts
- Initial registry with all 10 current EOMS artifacts
- Integration prompt for register updates
**Future State:** Foundation for self-documenting platform with OAA agent
**Impact:** High - Establishes artifact governance framework

| **PHASE 1 RE-SCOPING (February 2026)** |||||||
| CC-049 | ALL | ALL | RESCOPE | AI-augmented order management | **Order entry foundation** — remove all AI agents, FX integration, dashboards, analytics, approval workflows per client feedback. James (CEO) & Anthony (CFO/acting COO) want contained, low-risk first step proving workflow efficiency before layering intelligence. | Critical | **COMPLETED** |
| CC-050 | Proposal | v2.1 → v3.0 | REWRITE | AI-augmented scope, $22K investment, 41x ROI, 5 epics, 6 AI agents | Re-scoped to order entry foundation. Removed AI/FX/dashboard language. Benefits focused on labour efficiency + error reduction only. Operating costs ~$50/month (no Claude API). Narrative: "prove workflow efficiency first, add intelligence later" | Critical | **COMPLETED** |
| CC-051 | PRD | v1.7 → v2.0 | REWRITE | 5 epics, 60+ PBS nodes, 8-state workflow, AI layer | 3 epics (Order Management, Product Catalogue, Order Export to Finance). PBS simplified — removed PBS 4.0 (AI Layer). Order lifecycle: Draft→Complete→Exported. Removed FR-ORD-003 (FX), FR-APR-* (approvals), FR-DSH-* (dashboards). Added FR-EXP-001 (Order Export to Finance). 3 RBAC roles (Trader/Operations/Admin) | Critical | **COMPLETED** |
| CC-052 | HLD | v1.0 → v2.0 | REWRITE | Claude SDK, PF-Core, AI Agent Architecture (Section 6), FX in data model, 12 ontologies | Removed AI Agent Architecture section entirely. Removed Claude SDK/PF-Core from stack. Simplified Order schema (removed fx/compliance JSONB). Added order export spec. Removed Appendix D (Ontology Library). Operating costs $50/month | Critical | **COMPLETED** |
| CC-053 | Impl Plan | v1.0 → v2.0 | REWRITE | WBS 4.0 AI Integration, dashboard module, FX API, G0-G5 milestones | Removed WBS 4.0 entirely. Added order export WBS tasks. Milestones G0-G4 (removed G3 AI Integration Complete). Critical path: Environment→Database→Data Import→Order Module→Order Export→UAT→Production | Critical | **COMPLETED** |
| CC-054 | ALL | Integration | PROMOTE | Order export in future phase | **Finance-ready order export (CSV/JSON) promoted from future to Phase 1 core** — new Epic 3, new FR-EXP-001, WBS 3.3.7/3.4.4, HLD integration architecture section. Client identified clean finance-ready export as critical Phase 1 deliverable | High | **COMPLETED** |
| CC-055 | ALL | Benefits | RECALCULATE | 6 benefit categories, AI-driven claims | 2 primary categories: Labour Efficiency (55-65% time reduction) and Error Reduction (<3% error rate). Margin Protection, Capacity Enablement deferred. Conservative assumptions — no AI-driven benefits claimed | High | **COMPLETED** |
| CC-056 | ALL | Deferred | DOCUMENT | Items in Phase 1 scope | Formally deferred to future phases: AI validation agents (6), FX contract integration, margin threshold recognition, approval workflows/authority matrix, dashboards (Trader/Executive/Finance), analytics/KPIs/trends, advanced compliance automation, pattern recognition/smart reordering, PF-Core agent framework | High | **COMPLETED** |

---

## 4. STRUCTURAL GAPS IDENTIFIED

### 4.1 Missing Agile Hierarchy

**Current PRD Structure:**
- PBS (Product Breakdown Structure) ✓
- WBS (Work Breakdown Structure) ✓
- Functional Requirements ✓

**Missing:**
- Epics (high-level capability groupings)
- Features (deliverable functionality)
- User Stories (user-centric requirements)

**Recommendation:** Add Section 4.2 with Epic → Feature → Story hierarchy that maps to PBS

### 4.2 Cascading Implementation Basis

**Proposed Cascade:**
```
Proposal v2.1 (Business Case)
    ↓
PRD v1.2 (Product Definition)
    ↓ contains
    Epics → Features → User Stories
        ↓ maps to
        PBS (Product Breakdown)
            ↓ informs
            WBS (Work Breakdown)
                ↓ drives
                Implementation Plan
```

---

## 5. INVESTMENT MODEL DECISION

### APPROVED: AI-Assisted Development Model

**Decision:** Standardise BOTH documents on AI-assisted development model.

| Phase | Development | Operating | Timeline |
|-------|-------------|-----------|----------|
| Phase 1 MVP | **~$20,000** (£10K GBP) | ~$1,500/yr | 8-12 weeks |
| Extended phases | ~$45,000 | ~$3,500/yr | 12-18 months |
| **3-Year Total** | **~$65,000** | **~$5,000** | - |

**Key Metrics (AI-Assisted Model):**
| Metric | Value |
|--------|-------|
| 3-Year Total Investment | ~$70,000 |
| 3-Year Benefit (60%) | $3,674,100 |
| Net Value Created | $3,604,100 |
| ROI | **~52x** |
| Payback Period | **~9 days** |

### Traditional Development Model (Reference Only)

| Option | Approach | Investment |
|--------|----------|----------:|
| A | Internal + Advisory | $28,000 - $32,000 |
| B | Contractor | $45,000 - $55,000 |
| C | Agency (Turnkey) | $60,000 - $75,000 |

*Traditional model retained in Appendix for reference/comparison only.*

### Changes Required to Align

| Document | Current Model | Action |
|----------|---------------|--------|
| PRD v1.1 | AI-assisted ✓ | No change needed |
| Proposal v2.1 | Traditional ($92K) | **UPDATE to AI-assisted ($70K)** |

---

## 6. APPROVAL WORKFLOW

| Step | Action | Approver | Status |
|------|--------|----------|--------|
| 1 | Review Change Control Register | Document Owner | **COMPLETE** |
| 2 | Approve/Reject individual changes | Document Owner | **COMPLETE** |
| 3 | Resolve benefit figure discrepancy | Finance/COO | **COMPLETE** |
| 4 | Execute approved changes | Author | **COMPLETE** |
| 5 | PRD version increment (v1.1 → v1.2) | Author | **COMPLETE** |
| 6 | Final review | COO | PENDING |

---

## 7. SIGN-OFF

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Document Owner | | | |
| COO | | | |
| Adviser | | | |

---

**--- END OF CHANGE CONTROL REGISTER ---**

*Version 1.0 | For Review*
*26 January 2026*
