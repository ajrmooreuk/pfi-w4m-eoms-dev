# EOMS Document Register

## Phase 1 — Order Entry Foundation

---

**Last Updated:** 19 February 2026
**Version:** 4.0
**Status:** For Sign-Off

---

## Document Set Overview

```
EOMS_CLIENT_READINESS_VSOM.md       READY  - Executive summary, VSOM, scope gaps
        ↓
EOMS_STATEMENT_OF_WORK_v0.1.md      AGREE  - Scope, deliverables, acceptance criteria
        ↓
EOMS_TERMS_SHEET_v0.1.md            AGREE  - Payment schedule, IP, commercial terms
        ↓
EOMS_PROPOSAL_v3.1.md               WHY    - Business case, value proposition
        ↓
EOMS_PRD_UNIFIED_v2.1.md            WHAT   - Product requirements, epics, PBS
        ↓
EOMS_HLD_v2.1.md                    HOW    - Technical architecture, design decisions
        ↓
EOMS_IMPLEMENTATION_PLAN_v2.1.md    WHEN   - WBS, milestones, dependencies
        ↓
EOMS_VSOM_OKR_VP_ROADMAP.md         PLAN   - VSOM, OKRs, KPIs, VP, Epics, Gantt
```

---

## Client Sign-Up Package (Read in This Order)

| # | Document | Version | Status | Purpose | Audience |
|---|----------|---------|--------|---------|----------|
| 1 | [EOMS_CLIENT_READINESS_VSOM.md](EOMS_CLIENT_READINESS_VSOM.md) | 1.0 | Final Draft | Plain-English executive summary, VSOM, scope gaps | GM, COO |
| 2 | [EOMS_STATEMENT_OF_WORK_v0.1.md](EOMS_STATEMENT_OF_WORK_v0.1.md) | 0.1 | Draft | Scope, deliverables, acceptance criteria, WBS | GM, COO, CFO |
| 3 | [EOMS_TERMS_SHEET_v0.1.md](EOMS_TERMS_SHEET_v0.1.md) | 0.1 | Draft | Payment milestones, IP ownership, commercial terms | GM, COO, CFO |

---

## Core Documents (Supporting Detail)

| Document | Version | Status | Purpose |
|----------|---------|--------|---------|
| [EOMS_PROPOSAL_v3.1.md](EOMS_PROPOSAL_v3.0.md) | 3.1 | For Sign-Off | Business case — order entry foundation |
| [EOMS_PRD_UNIFIED_v2.1.md](EOMS_PRD_UNIFIED_v2.0.md) | 2.1 | For Implementation | Product requirements (3 epics) |
| [EOMS_HLD_v2.1.md](EOMS_HLD_v2.0.md) | 2.1 | For Implementation | Architecture — Next.js + Supabase |
| [EOMS_IMPLEMENTATION_PLAN_v2.1.md](EOMS_IMPLEMENTATION_PLAN_v2.0.md) | 2.1 | For Implementation | WBS, milestones, critical path |
| [EOMS_VSOM_OKR_VP_ROADMAP.md](EOMS_VSOM_OKR_VP_ROADMAP.md) | 1.0 | Draft | VSOM, OKRs, KPIs, Value Proposition, Epics roadmap, Gantt |

---

## Governance Documents

| Document | Version | Status | Purpose |
|----------|---------|--------|---------|
| [EOMS_CHANGE_CONTROL.md](EOMS_CHANGE_CONTROL.md) | 1.0 | Active | Change register (56 items, incl. re-scoping CC-049–CC-056) |
| [EOMS_DOCUMENT_TRACEABILITY.md](EOMS_DOCUMENT_TRACEABILITY.md) | 2.0 | Active | Cross-document alignment |
| EOMS_DOCUMENT_REGISTER.md | 4.0 | Active | This document |

---

## Superseded Documents

| Document | Version | Superseded By | Notes |
|----------|---------|---------------|-------|
| EOMS_PROPOSAL_v3.0.md | 3.0 | v3.1 | Pre-lean scope (full Figma, 3 RBAC, separate PMF) |
| EOMS_PRD_UNIFIED_v2.0.md | 2.0 | v2.1 | Pre-lean scope |
| EOMS_HLD_v2.0.md | 2.0 | v2.1 | Pre-lean scope |
| EOMS_IMPLEMENTATION_PLAN_v2.0.md | 2.0 | v2.1 | Pre-lean scope (6 WBS phases) |
| EOMS_PROPOSAL_v2.1.md | 2.1 | v3.0 | Included AI agents, FX, dashboards — broader scope |
| EOMS_PRD_UNIFIED_v1.7.md | 1.7 | v2.0 | 5 epics, AI layer, 8-state workflow |
| EOMS_HLD.md | 1.0 | v2.0 | Claude SDK, PF-Core, AI architecture |
| EOMS_IMPLEMENTATION_PLAN.md | 1.0 | v2.0 | AI integration phase, 6 milestones |

---

## Quick Reference

### What to Read First

1. **Client Readiness VSOM** — Plain-English overview, VSOM, scope gaps (start here)
2. **SOW v0.1** — Scope, deliverables, acceptance criteria
3. **Proposal v3.1** — Understand the WHY (business case, value proposition)
4. **PRD v2.1** — Epics (Order, Product, Order Export to Finance), PBS, requirements
5. **HLD v2.1** — Technical architecture, data model, design decisions

### Key Sections by Role

| Role | Documents | Time |
|------|-----------|------|
| **GM (Budget Approver)** | Client Readiness VSOM (Sections 1–4), then SOW Section 8 | 15 min |
| **COO (Product Owner)** | Client Readiness VSOM, SOW (full), Terms Sheet | 30 min |
| **CFO (Financial Review)** | Proposal Appendix D (ROI), Terms Sheet Section 3 | 15 min |
| **Technical** | HLD Sections 3–6, Implementation Plan | 20 min |
| **Operations** | PRD Section 4 (Epics & User Stories) | 10 min |
| **Project Board** | VSOM/OKR/VP Roadmap (full), GitHub Issues #17–#24 | 25 min |

### Sign-Off Sequence

```
1. Client reviews Client Readiness VSOM     → Confirms understanding
2. Parties discuss SOW                      → Agree scope & deliverables
3. Parties negotiate Terms Sheet            → Agree price & terms
4. SOW + Terms Sheet signed                 → Project authorised
5. Kickoff meeting                          → Development begins
```

---

## Document Version History

| Version | Date | Key Changes |
|---------|------|-------------|
| **Lean Scope (Feb 2026)** |||
| Proposal v3.1 | 19-Feb-2026 | Lean scope: no Figma, 2 RBAC roles, mobile optional, PMF folded into UAT |
| PRD v2.1 | 19-Feb-2026 | Lean scope: mobile SHOULD, simplified detail (wizard re-use), 2 roles |
| HLD v2.1 | 19-Feb-2026 | Lean scope: Tailwind config only, 2 RBAC roles, design decisions DD-008/DD-009 |
| Impl Plan v2.1 | 19-Feb-2026 | Lean scope: 5 WBS phases, compressed design, PMF folded into testing |
| **Phase 1 Re-Scoping (Feb 2026)** |||
| Proposal v3.0 | 19-Feb-2026 | Re-scoped: order entry foundation, removed AI/FX/dashboards |
| PRD v2.0 | 19-Feb-2026 | 3 epics, simplified PBS, Draft→Complete→Exported lifecycle |
| HLD v2.0 | 19-Feb-2026 | Simplified architecture, no AI layer, order export added |
| Impl Plan v2.0 | 19-Feb-2026 | Compressed WBS, 5 milestones (G0-G4) |
| **Client Sign-Up Package (Feb 2026)** |||
| Doc Register v3.0 | 09-Feb-2026 | Added VSOM/OKR/VP/Roadmap document, GitHub Epic issues #17–#24 |
| Doc Register v2.0 | 09-Feb-2026 | Added Client Sign-Up Package (VSOM, SOW, Terms Sheet) |
| **Original Scope (Jan 2026)** |||
| PRD v1.7 | 26-Jan-2026 | PRD Review & Enhancement: TOC, RRR framework, NFRs |
| PRD v1.6 | 26-Jan-2026 | PRD Scope Clean-up: move detail to HLD/Impl Plan |
| PRD v1.5 | 26-Jan-2026 | Epics before PBS, HLD reference, Ontology framework |
| PRD v1.4 | 26-Jan-2026 | Mermaid diagrams, VSOM, compliance generalisation |
| PRD v1.3 | 26-Jan-2026 | Benefit alignment, agile hierarchy |
| Proposal v2.1 | 26-Jan-2026 | AI-assisted costing model |
| HLD v1.0 | 26-Jan-2026 | Initial architecture document |
| Impl Plan v1.0 | 26-Jan-2026 | Initial WBS and schedule |
| SOW v0.1 | 09-Feb-2026 | Initial Statement of Work draft |
| Terms Sheet v0.1 | 09-Feb-2026 | Initial commercial terms draft |
| Client Readiness v1.0 | 09-Feb-2026 | Executive summary, VSOM, scope gap analysis |
| VSOM/OKR/VP/Roadmap v1.0 | 09-Feb-2026 | Strategic alignment, OKRs, KPIs, VP, 8-Epic delivery roadmap with Gantt |

---

## Phase 1 Scope Summary

**IN — Order Entry Foundation:**
- Order entry wizard (multi-step)
- Product search (7,816+ codes, market eligibility)
- Customer/buyer/consignee lookup
- Supplier/establishment selection
- Shipping details (container type, incoterms, ports)
- Order lifecycle: Draft → Complete → Exported
- Finance-ready order export (CSV/JSON)
- Basic auth (Supabase) with 2 RBAC roles (Trader, Admin)

**OUT — Deferred to Future Phases:**
- AI validation agents
- FX contract integration
- Dashboards & analytics
- Approval workflows
- Pattern recognition / smart reordering

---

## Standards & References

| Standard | Application |
|----------|-------------|
| MCSB v1 | Security baseline |
| shadcn/ui | Component library |
| Supabase RLS | Data access patterns |
| VSOM-ONT v3.0.0 | Vision-Strategy-Objectives-Metrics framework |
| OKR-ONT v2.0.0 | Objectives & Key Results framework |
| VP-ONT v1.2.3 | Value Proposition framework |
| PPM-ONT v4.0.0 | Portfolio/Programme/Project management |
| EFS-ONT v2.0.0 | Epics-Features-Stories agile framework |

---

## Contact

| Role | Responsibility |
|------|----------------|
| GM (Fin) | Budget Approver, Sign-Off |
| COO (F. Blacket) | Product Owner, Approvals |
| CFO (Anthony) | Finance, Commercial Terms |
| Technical Adviser (wings4mind.ai) | Architecture, Development Guidance |

---

*EOMS Phase 1 — Endeavour Order Management System*
*19 February 2026*
