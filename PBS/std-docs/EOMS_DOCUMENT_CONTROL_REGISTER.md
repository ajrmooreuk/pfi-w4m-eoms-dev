# EOMS DOCUMENT CONTROL REGISTER
## Unified Register of Design & Build Artifacts

---

| Document Control | |
|-----------------|---|
| **Document Number** | EOMS-DCR-001 |
| **Version** | 1.0 |
| **Status** | Active |
| **Date** | 26 January 2026 |
| **Owner** | COO (F. Blacket) |

---

## 1. PURPOSE

This Document Control Register (DCR) provides a single source of truth for all EOMS project documentation. It:

- Tracks all design and build artifacts
- Records version history and approval status
- Ensures document traceability
- Supports governance and audit requirements

---

## 2. DOCUMENT INVENTORY

### 2.1 Core Project Documents

| Doc ID | Document Name | Version | Status | Location | Approver |
|--------|---------------|---------|--------|----------|----------|
| EOMS-PROP-001 | EOMS_PROPOSAL_v2.1.md | 2.1 | Approved | PROPOSALS/ | COO |
| EOMS-PRD-001 | EOMS_PRD_UNIFIED_v1.7.md | 1.7 | For Implementation | PROPOSALS/ | COO |
| EOMS-HLD-001 | EOMS_HLD.md | 1.1 | Draft | PROPOSALS/ | COO |
| EOMS-IMP-001 | EOMS_IMPLEMENTATION_PLAN.md | 1.1 | Draft | PROPOSALS/ | COO |
| EOMS-CC-001 | EOMS_CHANGE_CONTROL.md | 1.0 | Active | PROPOSALS/ | COO |
| EOMS-TM-001 | EOMS_DOCUMENT_TRACEABILITY.md | 1.0 | Draft | PROPOSALS/ | COO |

### 2.2 Standard Documents

| Doc ID | Document Name | Version | Status | Location | Purpose |
|--------|---------------|---------|--------|----------|---------|
| EOMS-STD-001 | file-inventory-prompt.md | 1.0 | Active | std-docs/ | File inventory generation |
| EOMS-STD-002 | EOMS_DOCUMENT_CONTROL_REGISTER.md | 1.0 | Active | std-docs/ | This document |
| EOMS-STD-003 | EOMS_UNIFIED_REGISTER_PROCESS.md | 1.0 | Active | std-docs/ | Unified Register process |
| EOMS-STD-004 | eoms_unified_register.json | 1.0 | Active | std-docs/ | Unified artifact registry |
| EOMS-STD-005 | EOMS_CC_GITHUB_WORKFLOW.md | 1.0 | Active | std-docs/ | CC/GitHub workflow integration |

### 2.3 Design System Documents

| Doc ID | Document Name | Version | Status | Location | Purpose |
|--------|---------------|---------|--------|----------|---------|
| EOMS-DS-001 | Endeavour-DS | - | Proposed | TBD | Design tokens |

### 2.4 Ontology Documents

| Doc ID | Document Name | Version | Status | Location | Purpose |
|--------|---------------|---------|--------|----------|---------|
| EOMS-ONT-001 | Ontology Library | - | Proposed | TBD | Domain ontologies |

---

## 3. DOCUMENT HIERARCHY

```
PROPOSALS/                          (Published Documents)
├── EOMS_PROPOSAL_v2.1.md          WHY   - Business case
├── EOMS_PRD_UNIFIED_v1.5.md       WHAT  - Requirements
├── EOMS_HLD.md                    HOW   - Architecture
├── EOMS_IMPLEMENTATION_PLAN.md   WHEN  - Schedule
├── EOMS_CHANGE_CONTROL.md        GOVERNANCE - Changes
├── EOMS_DOCUMENT_TRACEABILITY.md GOVERNANCE - Alignment
└── README.MD                      INDEX

std-docs/                          (Standard Documents)
├── file-inventory-prompt.md       STANDARD - Inventory prompt
├── EOMS_DOCUMENT_CONTROL_REGISTER.md  REGISTER - This doc
├── EOMS_UNIFIED_REGISTER_PROCESS.md   PROCESS - CC→DCR→Registry flow
└── eoms_unified_register.json     DATA - Artifact registry JSON

PBS/ARCHITECTURE/                  (Source Documents)
└── 01-TOR-Terms-of-Ref-brief/
    └── EOMS-prd/                  Source location
```

---

## 4. VERSION CONTROL POLICY

### 4.1 Version Numbering

| Format | Description | Example |
|--------|-------------|---------|
| **Major.Minor** | Standard version | v2.1 |
| **Major** | Breaking changes, major revisions | v1 → v2 |
| **Minor** | Additions, non-breaking changes | v2.0 → v2.1 |

### 4.2 Document States

| State | Definition |
|-------|------------|
| **Draft** | Work in progress, not for implementation |
| **For Review** | Ready for stakeholder review |
| **Approved** | Signed off, ready for use |
| **For Implementation** | Approved and active for development |
| **Superseded** | Replaced by newer version |
| **Active** | Living document (registers, logs) |

---

## 5. APPROVAL MATRIX

| Document Type | Author | Reviewer | Approver |
|---------------|--------|----------|----------|
| Proposal | Technical Adviser | COO | GM |
| PRD | Technical Adviser | COO | COO |
| HLD | Technical Adviser | COO | COO |
| Implementation Plan | Technical Adviser | COO | COO |
| Change Control | Technical Adviser | COO | COO |
| Standards | Technical Adviser | - | COO |

---

## 6. CHANGE CONTROL INTEGRATION

All document changes are tracked in **EOMS_CHANGE_CONTROL.md**:

| CC# | Document | Change Type | Status |
|-----|----------|-------------|--------|
| CC-001 to CC-021 | PRD | Various | COMPLETED |
| CC-022 | PRD | Reorder sections | COMPLETED |
| CC-023 to CC-029 | PRD | Various | COMPLETED |
| CC-030 | HLD | Create document | COMPLETED |
| CC-031 | HLD | Fix Mermaid syntax | COMPLETED |
| CC-032 | DCR | Create register | COMPLETED |
| CC-033 | std-docs | Add file-inventory-prompt | COMPLETED |
| CC-034 | std-docs | Add unified register process & JSON | COMPLETED |
| CC-035 | PROPOSALS | Create team-shareable document register | COMPLETED |
| CC-036 | std-docs | Add CC/GitHub workflow document | COMPLETED |
| CC-037 | std-docs | Add Definition of Ready checklist | COMPLETED |
| CC-038 | std-docs | Fix Mermaid syntax error | COMPLETED |
| CC-039 to CC-043 | PRD v1.6 | PRD Scope Clean-Up (5 items) | COMPLETED |
| CC-044 to CC-048 | PRD v1.7 | PRD Review & Enhancement (5 items) | COMPLETED |

---

## 7. FILE INVENTORY INTEGRATION

This register integrates with the file inventory system:

### 7.1 Inventory Generation

Use `std-docs/file-inventory-prompt.md` to generate file inventories that feed into this register.

### 7.2 JSON Ontology Migration

File inventories will be converted to JSON ontologies:

```json
{
  "register_type": "document_control",
  "version": "1.0",
  "documents": [
    {
      "id": "EOMS-PROP-001",
      "name": "EOMS_PROPOSAL_v2.1.md",
      "version": "2.1",
      "status": "approved",
      "path": "PROPOSALS/EOMS_PROPOSAL_v2.1.md"
    }
  ]
}
```

---

## 8. AUDIT TRAIL

| Date | Action | By | Notes |
|------|--------|-----|-------|
| 26-Jan-2026 | Register created | Technical Adviser | Initial version |
| 26-Jan-2026 | CC-031 to CC-033 added | Technical Adviser | HLD fix, DCR, std-docs |
| 26-Jan-2026 | CC-034: Unified Register | Technical Adviser | Process doc + JSON registry |

---

## 9. NEXT ACTIONS

- [x] Complete JSON ontology schema for document registry
- [ ] Generate full file inventory of repository
- [ ] Integrate with Ontology Library
- [ ] Create automated validation of document references
- [ ] Set up Git hooks for auto-registration (future)

---

**--- END OF DOCUMENT CONTROL REGISTER ---**

*Version 1.0 | Active*
*26 January 2026*
