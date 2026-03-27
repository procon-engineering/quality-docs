# WI: Agent LE — Document Review Pass Execution

**Document ID:** 020506-29  
**Version:** 1.0  
**Date:** 2026-03-27  
**Author:** Angela (QMS)  
**Approved by:** Pending — Magnus Halvorsen  
**Status:** Under Review  
**ISO 9001:2015 Clause:** 8.5.1, 7.5.1  
**Parent SOP:** 020506-20 — Agent-Assisted Document Review SOP  

---

## Purpose

Step-by-step work instruction for a lead engineer agent executing a single document review pass. This WI is invoked once per review task.

---

## Inputs

| Input | Source |
|-------|--------|
| Document brief | Inbox file or C&A board item |
| Document under review | DMS board item or file path provided in brief |
| Applicable standards | Brief, plus `iso-standards.md` and project knowledge base |
| Prior findings (if re-review) | `project.db` — previous findings for this document |
| Reference documents | As listed in brief (prior revision, related drawings, standards) |

---

## Procedure

### Step 1 — Read the Brief

Open the inbox file or C&A item. Confirm:
- Document title and revision number
- Scope: what to check, what to exclude
- Standards to apply
- Any specific concerns flagged by the requester
- Deadline

If scope is unclear or standards are not specified, **do not begin review** — query the requester first.

---

### Step 2 — Read the Document

Read the full document. Note:
- Document type (report, drawing, cable list, equipment list, etc.)
- Revision history (what changed vs. prior revision, if applicable)
- Stated scope and applicability

For large documents, confirm the complete file has been loaded before proceeding.

---

### Step 3 — Apply the Review Framework

For each section of the document, apply the following checks:

#### 3a — Standards Compliance
- Does the document comply with applicable IEC/ISO standards?
- Are standard-mandated elements present (e.g. title block, revision history, approval status)?
- Are calculations, ratings, or specifications consistent with standard requirements?

Reference `iso-standards.md` for active standards. Reference project knowledge base for project-specific requirements.

#### 3b — Internal Consistency
- Are all cross-references within the document correct (table numbers, figure references, section references)?
- Do values cited in one section match values in another?
- Are all abbreviations defined?
- Are units consistent throughout?

#### 3c — Cross-Document Consistency
- Do values align with connected documents (e.g. cable list against SLD, equipment list against layout)?
- Does the document reflect the latest revision of its reference documents?
- Are there conflicts with other project deliverables?

Query the project database or other project documents as needed to perform cross-checks.

#### 3d — Completeness
- Is required content present for this document type?
- Are all mandatory fields / sections populated?
- Are approval signatures or status blocks complete?

#### 3e — Deviations from Reference Project
If a reference project (e.g. JBO, prior Procon project) has been cited in the brief:
- Identify where this project deviates from the reference
- Assess whether deviations are justified and documented
- Flag unjustified deviations as findings

---

### Step 4 — Log Findings

For every issue identified, create a finding in `project.db` with the following minimum fields:

| Field | Requirement |
|-------|-------------|
| Finding ID | Sequential, project-scoped (e.g. F-001, F-002) |
| Document | Title + revision |
| Section / Clause | Specific location in document |
| Description | Precise, unambiguous statement of the issue |
| Standard / Requirement | What requirement is not met (if applicable) |
| Severity | Comment / Minor / Major / Critical |
| Status | Open |

**Severity guidance:**
- **Comment** — Suggested improvement; no requirement violated
- **Minor** — Requirement partially met or minor error; does not affect safety or compliance
- **Major** — Requirement not met; affects compliance, safety, or fitness for purpose
- **Critical** — Fundamental deficiency; document cannot be used as-is

Do not aggregate multiple issues into a single finding. One issue = one finding.

If no findings are identified, explicitly record this: "No findings identified — document reviewed against [standards list]."

---

### Step 5 — Assess QMS Relevance

Review the findings list. If any finding indicates:
- A systemic process gap (same issue appearing across multiple documents)
- A missing or outdated procedure
- A deviation from the QMS or documented process

...submit a QMS observation via the inbox protocol. See `lead-engineer-qms-reporting.md`.

---

### Step 6 — Post the Check Report

Post a check report to the C&A board item (or return it to the requester's inbox if no C&A item exists). The report must include:

```
DOCUMENT REVIEW CHECK REPORT

Agent: [name]
Date: [date]
Document: [title, revision]
Standards applied: [list]

Result: PASS / PASS WITH COMMENTS / FAIL

Findings logged: [count]
  - Major: [count]
  - Minor: [count]
  - Comments: [count]

Key findings:
[brief summary of most significant findings, or "None — see project.db for full record"]

Traceability: All findings logged in project.db.
```

Update the DMS board item status to **Checked** once the report is posted.

---

### Step 7 — Notify the Requester

Ping the requester (lead engineer supervisor, project manager, or Magnus) in their Discord channel. Keep to one line — the full report is in the C&A board / inbox.

---

## Outputs

| Output | Destination |
|--------|-------------|
| Findings | `project.db` |
| Check report | C&A board item update or inbox |
| DMS status update | DMS board — Checked |
| QMS submission (if applicable) | `workspace-qms/inbox/` |

---

## Related Documents

- `020506-20` — Agent-Assisted Document Review SOP
- `knowledge-base/quality-instructions/findings-table-standard-2026-03-12.md`
- `knowledge-base/quality-instructions/lead-engineer-qms-reporting.md`
- `knowledge-base/quality-instructions/iso-standards.md`

---

*This document is subject to periodic review. Changes require Angela assessment and Magnus approval.*
