# Engineering Project File Storage

**Document ID:** 020506-46  
**Version:** 1.0 — Draft for approval  
**Date:** 2026-03-27  
**Author:** Angela (Quality Manager)  
**Owner:** Magnus Halvorsen (Engineering Director)  
**Status:** Draft — awaiting Engineering Director approval  
**ISO 9001:2015:** Clauses 7.5 (Documented Information), 8.5.1 (Control of Production and Service Provision)  
**Applies to:** All engineering projects on the shared Google Drive — human team members and AI agents  
**EQM Level:** L3 Work Instruction | Stream: Common

---

## 1. Purpose

This instruction defines the standard folder structure, file placement rules, document naming convention, and version management procedure for all engineering projects on the Procon/Hyndla shared Google Drive.

Consistent file storage ensures traceability, supports automated routing, and enables efficient retrieval by both human engineers and AI agents.

---

## 2. Scope

Applies to:
- All engineering projects hosted on the shared Google Drive
- All team members (human engineers and AI agents) creating, uploading, or managing project files
- Incoming files routed via the automated import watcher

---

## 3. Standard Project Folder Structure

Every engineering project shall maintain the following top-level folder structure. These folders are the minimum required; additional subfolders may be added for specific project scopes (e.g. `Electrical/`, `Mechanical/`).

### 3.1 Engineering/

Contains **Procon/Hyndla-authored documents only**. Client and vendor documents must not be placed in this folder.

> **Exception:** Comment Sheets are collaborative documents passed between Hyndla and the client. They are the only external-origin files permitted in `Engineering/`.

| Subfolder | Contents |
|---|---|
| `Comment Sheets/` | Review comment sheets on project documents |
| `Drawings/` | Hyndla-produced engineering drawings (DWG, DXF, PDF exports) |
| `Reports/` | Design reports, calculation notes, design basis documents, studies, analyses |
| `Spreadsheets/` | Cable lists, equipment lists, load lists, input lists, and other engineering spreadsheets |
| `3D Models/` | STEP, STP, Navisworks (NWD/NWC), and other 3D model files |
| `BOMs/` | Bills of materials |
| `Automation/` | PLC programmes, SCADA documents, I/O lists, control system documentation |
| `Datasheets/` | Hyndla-produced datasheets |
| `Working Files/` | Work-in-progress files, drafts, and internal working documents |

**How to identify a Hyndla document:** If the document number contains `HYND`, `HYN`, `PROCON`, or `HYNDLA`, it is a Hyndla document. All other documents are client or vendor origin and belong in `Import/`.

### 3.2 Import/

The receiving folder for all incoming documents from clients, vendors, and external parties.

- All externally received files land here first
- Files are automatically screened for security before processing
- **Client and vendor documents remain in `Import/`** — they are never moved to `Engineering/`
- Hyndla-authored documents (identified by `HYND`/`PROCON` in the document number) are automatically routed to the correct `Engineering/` subfolder
- Subfolders within `Import/` may be created per client or delivery batch

**Do not manually move files out of `Import/` into `Engineering/`.** The import watcher handles routing for incoming files. Manual uploads of Hyndla documents go directly to the correct `Engineering/` subfolder.

### 3.3 Project Management/

| Location | Contents |
|---|---|
| `TQs/` | Technical Queries — outgoing (TQ-HYND-*) and incoming (TQ-VES-*, TQ-RWE-*, etc.). TQ responses from Hyndla are uploaded here. |
| `Planning/` | Gantt charts, schedules, milestone trackers, timelines |
| Root | Presentations (KOM slides, progress reports), distribution lists, transmittals, meeting minutes |

### 3.4 Commercial/

| Location | Contents |
|---|---|
| `Invoices/` | Project invoices |
| `Contract Documents/` | Contracts, NDAs, purchase orders, agreements, terms and conditions |
| `Proposals/` | Quotations, tenders, offers |
| `OLD/` | Superseded commercial documents |
| Root | Vendor setup forms, scope of work documents, general commercial correspondence |

### 3.5 HSEQ/

Health, Safety, Environment, and Quality documentation for the project:
- Risk assessments, HAZOP/HAZID records
- Safety plans and environmental documentation
- Cyber security evaluations
- Quality-related project documents

### 3.6 Logistics/

Logistics and shipping documentation, packing lists, delivery records.

### 3.7 Export/ *(where applicable)*

Outgoing deliverables and export packages issued to the client.

---

## 4. Document Naming Convention

All Hyndla/Procon-authored documents shall use the standard document numbering format:

```
NSC-HYND-{PROJECT}-{DISCIPLINE}-ENG-{NUMBER}_{REVISION}
```

| Element | Description | Example |
|---|---|---|
| `NSC` | Project prefix (North Sea Connect or applicable prefix) | `NSC` |
| `HYND` | Hyndla/Procon identifier — marks this as our document | `HYND` |
| `{PROJECT}` | Project code | `NSCB` |
| `{DISCIPLINE}` | Engineering discipline code | `FOU` (Foundations), `LV` (Low Voltage) |
| `ENG` | Document type — Engineering | `ENG` |
| `{NUMBER}` | Sequential 5-digit document number | `00025` |
| `_{REVISION}` | Underscore-separated revision number (2-digit) | `_04` |

**Example:** `NSC-HYND-NSCB-FOU-ENG-00025_04.xlsx`

This naming convention ensures correct identification as a Hyndla document for automated routing. Documents not following this convention may not route correctly via the import watcher.

---

## 5. Version Management

When uploading a new revision of a document to a folder that already contains a previous revision:

1. The **previous revision** is moved to an `old/` subfolder within the same directory
2. If no `old/` subfolder exists, it is created automatically
3. The **new revision** takes its place in the main folder

This applies to all project folders, not only `Commercial/`.

**For automated uploads:** The import watcher handles version management automatically when an incoming file replaces an existing document.

**For manual uploads:** Engineers uploading directly to `Engineering/` subfolders are responsible for following the same process. The system may assist, but manual verification is required.

---

## 6. Responsibilities

| Role | Responsibility |
|---|---|
| **All team members** | Upload Hyndla documents to the correct `Engineering/` subfolder; use the standard naming convention; do not place client/vendor files in `Engineering/` |
| **Lead Engineer** | Verify that documents on their projects are correctly stored and named before submission for check |
| **Agents (automated)** | Follow the same routing rules; the import watcher enforces rules for incoming files; agent-created files must also follow the naming convention |
| **Quality Manager** | Maintain this instruction; audit compliance during internal audits |

---

## 7. Non-Compliance

Failure to follow this instruction may result in:
- Documents being unroutable by the automated import system
- Incorrect version management (overwriting without archiving to `old/`)
- Client or vendor documents appearing in `Engineering/`, causing audit traceability failures

Non-compliance identified during audit shall be logged as an Observation or NCR per the QMS findings submission process (see: `lead-engineer-qms-reporting.md`).

---

## 8. Related Documents

| Document | Reference |
|---|---|
| Engineering Communication WI | EQM L3 — Common |
| QMS Findings Submission | `lead-engineer-qms-reporting.md` |
| Findings Table Standard | `findings-table-standard-2026-03-12.md` |
| Document Management SOP | EQM L2 — Common *(in progress)* |

---

*Angela — Quality Manager | Draft v1.0 | 2026-03-27*  
*Awaiting Engineering Director approval before adoption*
