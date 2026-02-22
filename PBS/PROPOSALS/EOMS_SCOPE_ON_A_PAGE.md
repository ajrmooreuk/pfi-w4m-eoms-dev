# EOMS Phase 1 — Scope on a Page

**Endeavour Order Management System | APPROVED 22 February 2026**

> **Status: APPROVED** — Gate G1 passed. Scope confirmed, development authorised to commence.

---

## The Brief

> Prove workflow efficiency first. Replace the spreadsheets with a simple, focused order entry system. Keep it contained and low-risk. Layer intelligence and automation later.

---

## What Changed (Reduced Scope — Approved)

| Change | Was | Now | Why | Approved |
|--------|-----|-----|-----|:--------:|
| **Scope narrowed to 3 epics** | 5 (Order, Product, AI, FX, Dashboards) | 3 (Order, Product, Order Export to Finance) | Focus on core workflow — prove the value before adding intelligence | ✅ |
| **AI / Agents removed** | Claude SDK, 4 AI agents, PF-Core | Removed entirely | Deferred to Phase 2 — not needed to prove efficiency gains | ✅ |
| **FX Integration removed** | Currency conversion, FX contracts | Removed entirely | Deferred — adds complexity without proving core workflow | ✅ |
| **Dashboards removed** | Trader, Executive, Finance dashboards | Removed entirely | Deferred — analytics comes after clean data is flowing | ✅ |
| **Approval workflow simplified** | 8-state lifecycle, authority matrix | 3-state (Draft → Complete → Exported) | Traders own the workflow — no approval bottleneck | ✅ |
| **Design phase cut** | Figma wireframes, mockups, prototypes | Tokens applied directly in code | Saves time and cost — existing brand system sufficient | ✅ |
| **Roles simplified** | 3 (Trader, Operations, Admin) | 2 (Trader, Admin) | Operations folded into Trader — simpler | ✅ |
| **Mobile de-risked** | MUST have | SHOULD have (desktop-first) | Traders use desktop; mobile if budget allows | ✅ |
| **PMF folded into UAT** | Separate research phase | Integrated into user testing | Feedback from real usage — no extra overhead | ✅ |
| **Order Export promoted** | Future phase | Phase 1 core (CSV/JSON) | Day-one requirement — data must flow to finance | ✅ |

---

## What Stays

- **Order entry wizard** — multi-step guided creation replacing spreadsheet process
- **Product search** — 7,816+ codes with market eligibility filtering (< 200ms)
- **Customer/buyer/consignee lookup** — database-driven, no more manual entry
- **Supplier/establishment selection** — validated against regulatory identifiers
- **Shipping details** — container type, incoterms, load/destination ports
- **Audit trail** — complete history of every order change
- **Basic auth** — Supabase with role-based access control

---

## How This Meets the Brief

| Client Requirement | How We Deliver |
|--------------------|----------------|
| **Prove workflow efficiency** | Order creation drops from 45–60 min to < 20 min |
| **Simple and focused** | 3 epics, 2 roles, 3-state lifecycle — nothing unnecessary |
| **Contained and low-risk** | ~$50 AUD/month infrastructure, no AI API costs, proven stack |
| **Low-risk first step** | No complex integrations — standalone system with clean file export |
| **Foundation for future** | Data model, auth, and architecture designed for AI/FX/dashboards to plug in later |

---

## Timeline

| Week | Dates | What |
|------|-------|------|
| **1–2** | 23 Feb – 7 Mar | Foundation: environment, database, auth, design tokens, data import |
| **3–4** | 10–21 Mar | Core build: order wizard, product search, order list (parallel) |
| **5** | 24–28 Mar | Order export to finance (CSV/JSON) |
| **6–7** | 31 Mar – 11 Apr | Testing, UAT with traders, PMF feedback, bug fixes |
| **8** | 14–18 Apr | Deployment, handover, go-live |

**Go-Live Target: 18 April 2026**

---

## The Narrative

Phase 1 builds the **data foundation and workflow engine** — a simple, effective order entry system that replaces spreadsheets, reduces errors, and saves the trade team hours per week. This foundation is deliberately designed so that AI validation, FX integration, dashboards, and analytics can be layered on in future phases with minimal rework.

**Prove the efficiency gain first, then add intelligence.**

---

## Approval Record

| Item | Detail |
|------|--------|
| **Gate** | G1: Phase 1 Approval |
| **Date** | 22 February 2026 |
| **Decision** | APPROVED — Proceed to development |
| **Approved By** | CEO / CFO |
| **Advisory** | wings4mind.ai |

---

*Prepared by wings4mind.ai | Supporting documents: [GitHub — EOMS-Ph1](https://github.com/ajrmooreuk/EOMS-Ph1/tree/main/PROPOSALS)*
