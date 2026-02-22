# EOMS Phase 1 — Kickstart Meeting

**Endeavour Order Management System | Project Kickstart**

---

| Detail | |
|--------|---|
| **Date** | w/c 24 February 2026 (TBC) |
| **Duration** | 60 minutes |
| **Location** | Teams / In-person (TBC) |
| **Called By** | wings4mind.ai (Advisory) |
| **Attendees** | James (CEO), Anthony (CFO/Acting COO), wings4mind.ai |
| **Pre-Read** | Scope on a Page (approved 22 Feb), Proposal v3.1 |

---

## Purpose

Formally kick off EOMS Phase 1 following scope approval on 22 February 2026. Align on immediate actions, data dependencies, and the 8-week delivery timeline to go-live on 18 April 2026.

---

## Agenda

### 1. Scope Confirmation (5 min)

- Recap approved reduced scope — 3 epics, 2 roles, 3-state lifecycle
- Confirm what is **in**: Order entry wizard, product search, customer lookup, order export to finance
- Confirm what is **out** (Phase 2+): AI agents, FX integration, dashboards, approval workflows
- Any final questions on scope boundaries

### 2. Value Proposition Recap (5 min)

| Metric | Current | Phase 1 Target |
|--------|---------|----------------|
| Order entry time | 45–60 min | < 20 min |
| Error rate | 5–8% | < 3% |
| Finance export | None | CSV/JSON |
| Audit trail | None | Full history |

- This is about **proving efficiency first** — intelligence and automation come later

### 3. Timeline & Milestones (10 min)

| Week | Dates | Deliverable | Client Action Needed |
|------|-------|-------------|---------------------|
| **1–2** | 23 Feb – 7 Mar | Environment, database, auth, data import | **Product + customer data extracts** |
| **3–4** | 10–21 Mar | Order wizard, product search, order list | Review demo mid-build |
| **5** | 24–28 Mar | Order export to finance | **Confirm export format with finance** |
| **6–7** | 31 Mar – 11 Apr | UAT with traders, bug fixes | **3–5 traders for UAT sessions** |
| **8** | 14–18 Apr | Go-live, handover | Go/No-Go decision |

**Key dates to lock in:**
- [ ] Mid-build demo (w/c 17 March)
- [ ] UAT sessions (w/c 31 March + 7 April)
- [ ] Go/No-Go decision (w/c 14 April)
- [ ] Go-live target: **18 April 2026**

### 4. Data Dependencies — Action Required (15 min)

These are the **critical path items** that the client must deliver for development to proceed:

| # | Data Required | Owner | Needed By | Format |
|---|---------------|-------|-----------|--------|
| D1 | **Product code list** (7,816+ codes) | Operations | **28 Feb** | Excel/CSV — code, description, brand, feed type, product state, market eligibility, AHECC, shelf life |
| D2 | **Customer list** (buyers + consignees) | Finance / Operations | **28 Feb** | Excel/CSV — name, type, contact, address, payment terms |
| D3 | **Supplier / establishment list** | Operations | **28 Feb** | Excel/CSV — supplier name, establishment number, program |
| D4 | **Port list** (load + destination) | Operations | **28 Feb** | Excel/CSV — port name, country, code |
| D5 | **Finance export format** requirements | Finance | **14 Mar** | Specification of what fields finance needs in the export file |
| D6 | **Sample order** (completed spreadsheet) | Traders | **28 Feb** | 2–3 real completed order spreadsheets as test data reference |

**Discussion points:**
- Who owns each extract?
- Are there any data sensitivity/privacy concerns?
- Can we get sample data by end of next week to unblock development?

### 5. Roles & Responsibilities (5 min)

| Role | Person | Responsibility |
|------|--------|----------------|
| **Project Sponsor** | Anthony (CFO/COO) | Scope decisions, UAT sign-off, go/no-go recommendation |
| **Executive Sponsor** | James (CEO) | Final go/no-go authority |
| **Technical Advisory** | wings4mind.ai | Design, build, test, deploy, handover |
| **UAT Participants** | 3–5 Traders (TBN) | Test the system, provide feedback |
| **Data Owners** | Operations / Finance | Provide product, customer, supplier data extracts |

**Action:** Anthony to nominate 3–5 traders for UAT by **7 March**.

### 6. Infrastructure & Accounts (5 min)

| Item | Status | Action |
|------|--------|--------|
| Supabase account (Sydney) | To set up | wings4mind.ai — Week 1 |
| Vercel account | To set up | wings4mind.ai — Week 1 |
| Domain & SSL | TBC | Client to confirm preferred domain |
| GitHub repo (`pfi-w4m-eoms-dev`) | Live | Development repo ready |

**Decision needed:**
- [ ] Preferred domain for EOMS (e.g. `eoms.endeavourmeats.com.au` or similar)
- [ ] Supabase account ownership — Endeavour or wings4mind.ai managed?

### 7. Communication Cadence (5 min)

**Proposed:**

| Cadence | What | Who | Format |
|---------|------|-----|--------|
| **Weekly** | Progress update + blockers | Advisory → Anthony | Email / Teams message |
| **Fortnightly** | Demo / walkthrough | Advisory + Anthony + traders | Teams call (30 min) |
| **Ad hoc** | Urgent decisions or blockers | Advisory ↔ Anthony | Teams / phone |
| **Gate reviews** | G2 (UAT sign-off), G3 (Go/No-Go) | All stakeholders | Formal meeting |

- [ ] Confirm preferred day for weekly updates
- [ ] Confirm preferred day for fortnightly demos

### 8. Risks & Assumptions (5 min)

| Risk | Mitigation |
|------|------------|
| Product/customer data delayed | Start dev with sample data; import is iterative |
| Traders unavailable for UAT | Lock in names and dates early (Week 1) |
| Scope creep requests during build | All changes via change control — future phases defined |
| Finance export format unclear | Design flexible CSV/JSON; iterate with finance in Week 5 |

**Key assumption:** Existing product code spreadsheet (7,816 codes) is the source of truth. Any data cleansing is client-side before import.

### 9. AOB & Next Steps (5 min)

---

## Actions Summary

| # | Action | Owner | Due |
|---|--------|-------|-----|
| A1 | Provide product code extract (7,816+ codes) | Operations | 28 Feb |
| A2 | Provide customer/buyer/consignee list | Finance / Ops | 28 Feb |
| A3 | Provide supplier/establishment list | Operations | 28 Feb |
| A4 | Provide 2–3 sample completed order spreadsheets | Traders | 28 Feb |
| A5 | Nominate 3–5 traders for UAT | Anthony | 7 Mar |
| A6 | Confirm finance export format requirements | Finance | 14 Mar |
| A7 | Confirm preferred domain for EOMS | Anthony | 7 Mar |
| A8 | Set up Supabase + Vercel environments | wings4mind.ai | 7 Mar |
| A9 | Confirm communication cadence (weekly update day, demo day) | Anthony | Kickstart |
| A10 | Lock in mid-build demo date (w/c 17 Mar) | All | Kickstart |

---

## Meeting Notes

*(To be completed during the meeting)*

**Attendees:**

**Key Decisions:**

**Additional Actions:**

**Next Meeting:**

---

*Prepared by wings4mind.ai | 22 February 2026*
