# PFI-EOMS-BRIEF: Application Framework & Design System Integration

**Product Code:** PFI-EOMS
**Document Type:** BRIEF — Strategy Briefing
**Version:** v1.0.0
**Date:** 2026-03-10
**Status:** Draft
**Epic Ref:** Epic 8 (to be created)
**Author:** Design Director + Claude Code
**PFI Instance:** pfi-w4m-eoms (`ajrmooreuk/pfi-w4m-eoms-dev`)

---

## 1. Purpose

This briefing establishes **Epic 8: Application Framework & Design System Integration** for EOMS, bringing Endeavour Meats into the PFC Application Skeleton + DS-ONT pattern already proven in VHF and the Ontology Adviser. This replaces the current ad-hoc Tailwind-config-only brand approach with a governed, token-mapped, zone-driven architecture that enables progressive brand refinement while building.

### 1.1 Why Now

The Endeavour brand is early-stage (EOMS_DESIGN_SYSTEM v0.2 DRAFT). Rather than freeze a half-formed brand into hardcoded Tailwind, we adopt the DS-ONT token cascade so:

- Brand values live in **one JSONLD instance file** — change tokens, see results immediately
- The **Application Skeleton** defines zones/navigation declaratively — no rewiring components when layout evolves
- **Admin/Design widgets** (token inspector, zone inspector) let the Design Director validate and refine the brand live in the running app
- All EOMS components inherit tokens via CSS custom properties — the same pattern as VHF, BAIV, and the Ontology Adviser

### 1.2 PFC Pattern Reference

| Pattern | PFC Source | VHF Implementation | EOMS Target |
|---|---|---|---|
| DS-ONT v3.0.0 | `PE-Series/DS-ONT/Entry-ONT-DS-001.json` | `vhf-viridian-ds-instance-v1.0.0.jsonld` | `eoms-endeavour-ds-instance-v1.0.0.jsonld` |
| App Skeleton | `pfc-app-skeleton-v1.0.0.jsonld` | `vhf-app-skeleton-v1.0.0.jsonld` | `eoms-app-skeleton-v1.0.0.jsonld` |
| Token Bridge | `ds-css-bridge.ts` / `token-bridge.js` | `token-bridge.js` → `:root` CSS vars | shadcn CSS vars via `ds-css-bridge` pattern |
| Zone Framework | DS-ONT AppZone entity | 8 VHF zones (Fixed, Sliding, Overlay) | 8 EOMS zones (order mgmt focused) |
| Admin Overlay | DS-ONT ZoneComponent | Z7 (Admin) + Z8 (Skeleton Inspector) | Z-EOMS-007 (Admin) + Z-EOMS-008 (Inspector) |
| EMC Cascade | 4-tier: PFC → PFI → Product → App | PFI-VHF tier overrides PFC base | PFI-EOMS tier overrides PFC base |

---

## 2. Architecture

### 2.1 Token Cascade (DS-ONT 3-Tier)

```
┌─────────────────────────────────────────────────────────────────┐
│  PRIMITIVE TOKENS (Layer 1)                                      │
│  Raw brand values from EOMS_DESIGN_SYSTEM v0.2                   │
│  color.primary: #19253B · color.secondary: #BC4620               │
│  font.heading: Baskervville · font.body: Lato                    │
│  spacing.xs–xlrg · radius.xs–full                                │
├─────────────────────────────────────────────────────────────────┤
│  SEMANTIC TOKENS (Layer 2)                                       │
│  Intent-based references to primitives                           │
│  primary.surface.default → #19253B                               │
│  secondary.surface.default → #BC4620                             │
│  error.surface.default → #EEC800                                 │
│  neutral.text.body → #3A5A68                                     │
├─────────────────────────────────────────────────────────────────┤
│  COMPONENT TOKENS (Layer 3 — future DS-ONT v4.0.0)              │
│  button.primary.background → primary.surface.default             │
│  card.surface → neutral.surface.subtle                           │
│  table.header → primary.surface.darker                           │
└─────────────────────────────────────────────────────────────────┘
```

### 2.2 EMC Cascade for EOMS

```
PFC Base Skeleton (immutable)
  ↓ inherits
PFI-EOMS Override (eoms-app-skeleton-v1.0.0.jsonld)
  ↓ adds zones, nav items, actions, brand token overrides
App-level config (runtime)
  ↓ theme mode, user preferences
Rendered UI
```

### 2.3 Zone Framework — EOMS 8-Zone Layout

| Zone ID | Name | Type | Position | Default Visible | Purpose |
|---|---|---|---|---|---|
| Z-EOMS-001 | Dashboard | Fixed | center | Yes | Order summary, KPI tiles, recent activity |
| Z-EOMS-002 | Order Wizard | Fixed | center | No | 4-step guided order creation flow |
| Z-EOMS-003 | Order Detail | Sliding | right | No | Full order view, line items, audit trail |
| Z-EOMS-004 | Product Catalogue | Sliding | right | No | 7,816+ product search, market eligibility |
| Z-EOMS-005 | Approval Queue | Sliding | left | No | Pending orders awaiting manager approval |
| Z-EOMS-006 | FX Management | Sliding | left | No | Currency rates, margin calculator |
| Z-EOMS-007 | Admin Overlay | Floating | right | No | Design Director: token inspector, CSS Live |
| Z-EOMS-008 | Skeleton Inspector | Floating | right | No | Zone browser, component placement, overrides |

### 2.4 Navigation (L4-EOMS Layer)

| Nav Item | Action | Icon | Type |
|---|---|---|---|
| Dashboard | showDashboard | layout-dashboard | Button |
| New Order | showOrderWizard | plus-circle | Button |
| Products | showProductCatalogue | package | Button |
| Approvals | showApprovalQueue | check-square | Button |
| FX Rates | showFXManagement | dollar-sign | Button |
| Admin | toggleAdminOverlay | settings | Toggle |

### 2.5 Token Bridge → shadcn Integration

The EOMS stack is **Next.js 14 + shadcn/ui + Tailwind**. Token mapping:

```
DS-ONT JSONLD Instance
  ↓ fetch at app init
ds-css-bridge pattern
  ↓ resolve primitive → semantic → brand override
CSS Custom Properties on :root
  ↓ shadcn consumes via --primary, --secondary, etc.
  ↓ Tailwind consumes via theme.extend.colors
shadcn Components render with brand tokens
```

**shadcn Slot Mapping:**

| DS-ONT Semantic Token | shadcn CSS Variable | Endeavour Value |
|---|---|---|
| `primary.surface.default` | `--primary` | `#19253B` (Deep Navy) |
| `primary.surface.lighter` | `--primary-foreground` | `#FFFFFF` |
| `secondary.surface.default` | `--secondary` | `#BC4620` (Burnt Sienna) |
| `accent.surface.default` | `--accent` | `#6B9EFE` (Sky Blue) |
| `neutral.surface.subtle` | `--muted` | `#F8FAFC` |
| `neutral.text.body` | `--foreground` | `#3A5A68` |
| `neutral.surface.default` | `--card` | `#FFFFFF` |
| `neutral.border.default` | `--border` | `#C6E8F5` |
| `error.surface.default` | `--destructive` | `#EEC800` |

---

## 3. Epic 8: Feature Breakdown

### F8.1: EOMS DS-ONT Instance

**Deliverable:** `instance-data/tokens/EOMS-DESIGN-SYSTEM-ONT/eoms-endeavour-ds-instance-v1.0.0.jsonld`

| Story | Scope |
|---|---|
| S8.1.1 | Create DS-ONT instance with Endeavour primitive tokens (colours, typography, spacing, radius) |
| S8.1.2 | Add semantic tokens (primary, secondary, accent, error, warning, success, neutral) with surface/border/text variants |
| S8.1.3 | Add BrandVariant entity for Endeavour Meats with Figma source reference |
| S8.1.4 | Add ThemeMode entity (light mode default, dark mode future) |
| S8.1.5 | Validate instance against DS-ONT v3.0.0 schema |

### F8.2: EOMS Application Skeleton

**Deliverable:** `application/eoms-app-skeleton-v1.0.0.jsonld`

| Story | Scope |
|---|---|
| S8.2.1 | Define 8 EOMS zones (Dashboard, Order Wizard, Order Detail, Product Catalogue, Approval Queue, FX Management, Admin, Inspector) |
| S8.2.2 | Define L4-EOMS navigation layer with 6 nav items |
| S8.2.3 | Define 8 action entities (one per zone toggle + order CRUD actions) |
| S8.2.4 | Add ZoneComponent with Endeavour brand token overrides for context bar |
| S8.2.5 | Validate skeleton cascade: PFC base → PFI-EOMS override |

### F8.3: Token Bridge Integration

**Deliverable:** Token bridge module wired into Next.js app init

| Story | Scope |
|---|---|
| S8.3.1 | Create `lib/ds-css-bridge.ts` — fetch DS-ONT JSONLD, resolve token cascade, apply to `:root` |
| S8.3.2 | Map DS-ONT semantic tokens → shadcn CSS variable slots |
| S8.3.3 | Map DS-ONT semantic tokens → Tailwind theme.extend via CSS vars |
| S8.3.4 | Skeleton token overrides merge (skeleton wins over DS-ONT instance) |
| S8.3.5 | WCAG AA contrast check on text/background pairs at bridge init |

### F8.4: Admin Overlay — Design Director Tools

**Deliverable:** Admin overlay zone (Z-EOMS-007) with token and zone inspection

| Story | Scope |
|---|---|
| S8.4.1 | CSS Live tab — list all `--ds-*` custom properties with source badges (DS-ONT / Skeleton Override / Tailwind Default) |
| S8.4.2 | DS-ONT Source tab — tokens from JSONLD instance with divergence flags where CSS var differs |
| S8.4.3 | Zone Inspector tab — zone list with visibility state, placed components, token override count |
| S8.4.4 | Token edit sandbox — Design Director can temporarily override a token value and see live preview (not persisted) |
| S8.4.5 | Export current token state as updated DS-ONT JSONLD patch (for commit back to repo) |

### F8.5: Progressive Brand Refinement Workflow

**Deliverable:** Documented workflow for brand iteration via DS-ONT

| Story | Scope |
|---|---|
| S8.5.1 | Document brand refinement loop: Figma reference → DS-ONT JSONLD update → token bridge → live preview → commit |
| S8.5.2 | Create EOMS Figma ↔ DS-ONT token mapping table (for future Figma Make integration) |
| S8.5.3 | Add brand verification matrix (Endeavour primary/secondary/accent verified against WCAG AA) |
| S8.5.4 | Integration test: skeleton load → token bridge → all zones render with correct brand tokens |

---

## 4. Acceptance Criteria (Epic Level)

| # | Criterion | Verification |
|---|---|---|
| AC-1 | EOMS DS-ONT instance validates against DS-ONT v3.0.0 schema | Schema validation pass |
| AC-2 | EOMS app skeleton inherits PFC base and adds 8 EOMS zones | Skeleton loader parses without error |
| AC-3 | Token bridge maps DS-ONT tokens → shadcn CSS vars at app init | All `--ds-*` vars present in computed style |
| AC-4 | Endeavour brand colours render correctly across all shadcn components | Visual regression check |
| AC-5 | Admin overlay displays token source, zone state, and divergence flags | Manual QA |
| AC-6 | WCAG AA contrast passes for all text/background pairs | `checkContrastCompliance()` returns empty array |
| AC-7 | Brand can be updated by editing JSONLD only — no CSS/Tailwind changes needed | Token change → reload → new colours render |

---

## 5. Dependencies

| Dependency | Status | Impact if Blocked |
|---|---|---|
| DS-ONT v3.0.0 (Azlan-EA-AAA) | Available | None — ontology schema ready |
| PFC App Skeleton v1.0.0 | Available | None — base skeleton ready |
| `ds-css-bridge.ts` pattern (Epic 65) | Available | Port pattern to Next.js context |
| Next.js 14 + shadcn/ui (EOMS stack) | Confirmed | None — already in HLD v2.1 |
| Endeavour brand assets (EOMS-DS-001 v0.2) | Available | Tokens may evolve — that's the point |

---

## 6. Execution Order

Epic 8 should execute **before or in parallel with** Epic 1 (Order Management):

```
Week 1:  F8.1 (DS-ONT instance) + F8.2 (Skeleton JSONLD) — data artefacts only
Week 2:  F8.3 (Token bridge) — wired into Next.js app shell
Week 2:  F8.4 (Admin overlay) — inspection tools
Week 3+: F8.5 (Brand refinement) — ongoing as Epics 1-6 build features into zones
```

This means from Week 2 onwards, every component built in Epics 1-6 automatically inherits the Endeavour brand via token bridge + zone placement — no separate "apply styling" pass required.

---

## 7. Risk Register

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Brand evolves significantly after tokens locked | High | Low | DS-ONT is designed for this — update JSONLD, reload |
| Endeavour semantic colours have WCAG issues | Medium | Medium | Contrast check at bridge init; flag failures early |
| shadcn component overrides conflict with token vars | Low | Medium | shadcn uses CSS vars natively — alignment is natural |
| Admin overlay adds complexity to Phase 1 scope | Medium | Low | Admin zone is toggleable, ships behind feature flag |

---

## 8. Artefact Inventory

| Artefact | Path | Type |
|---|---|---|
| This briefing | `PBS/STRATEGY/PFI-EOMS-BRIEF-Application-Framework-Design-System-Integration-v1.0.0.md` | Strategy |
| DS-ONT Instance | `instance-data/tokens/EOMS-DESIGN-SYSTEM-ONT/eoms-endeavour-ds-instance-v1.0.0.jsonld` | Instance Data |
| App Skeleton | `instance-data/skeleton/eoms-app-skeleton-v1.0.0.jsonld` | Instance Data |
| PFI Config (existing) | `instance-data/config/pfi-config.json` | Config |

---

*Generated: 2026-03-10 · EOMS Application Framework · `pfi-w4m-eoms-dev`*
