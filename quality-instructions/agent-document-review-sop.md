# Agent-Assisted Document Review SOP

**Document ID:** 020506-20  
**Version:** 1.0  
**Date:** 2026-03-27  
**Author:** Angela (QMS)  
**Approved by:** Pending — Magnus Halvorsen  
**Status:** Under Review  
**ISO 9001:2015 Clause:** 8.3.4, 8.5.1, 7.5.1  

---

## Purpose

This SOP defines the process by which agent lead engineers assist with technical document review in Procon engineering projects. It covers how review tasks are initiated, executed, recorded, and closed out through the monday.com Check & Approve (C&A) system.

---

## Scope

Applies to all agent lead engineers (Tom, Bart, Kai, Duncan, Rosa, Angus, Cedar, Emmy, Genny, Elise, Morgan, Isla, and future hires) performing document review passes on their assigned projects.

Does not apply to design development activities, which are the responsibility of the human engineering team.

---

## Responsibilities

| Role | Responsibility |
|------|---------------|
| Magnus / Project Manager | Assigns documents to agent for review; sets scope and standards |
| Lead Engineer Agent | Executes review pass per WI (see below); logs findings; posts check report |
| Checker (human) | Reviews agent findings; approves or rejects check report |
| Angela | Monitors review quality; receives QMS findings from leads |
| Forge | Maintains check-trigger.js, check-resolve.js, and DMS tooling |

---

## Workflow

### Stage 1 — Review Initiation

Documents are assigned to an agent lead engineer via one of these routes:

1. **monday.com C&A board** — A new item appears in the agent's queue on the Check & Approve board (project-specific board, e.g. NSC B C&A). The `check-trigger.js` automation detects the assignment and routes the task to the agent's inbox.

2. **Direct inbox delivery** — Magnus or a project supervisor delivers a review brief directly to `workspace-<agentId>/inbox/`.

The brief contains:
- Document title and revision
- DMS board item ID
- Review scope (standards, prior findings, reference documents)
- Deadline

---

### Stage 2 — Review Execution

The lead engineer performs the review following:

**`WI: Agent LE — Document Review Pass Execution`** (020506-29)

At minimum, the review covers:
- Compliance with applicable standards (IEC, ISO, project-specific)
- Internal consistency (cross-referencing within the document)
- Cross-document consistency (against other project deliverables)
- Completeness of required content per document type
- Traceability to requirements

All findings are logged to the project database (`project.db`) using the Engineering Findings Table standard (`findings-table-standard-2026-03-12.md`).

---

### Stage 3 — Check Report Posting

On completion, the lead engineer posts a structured check report to the C&A board item via the `check-resolve.js` automation, or directly via API update. The report includes:

- Summary: pass / pass with comments / fail
- Number of findings logged
- Key findings summary (if any)
- Standards referenced
- Agent sign-off

The DMS board item status is updated to **Checked** once the report is posted.

---

### Stage 4 — Human Checker Review

A human checker (as defined per project DMS assignment policy — see `dms-author-checker-approver-policy.md`) reviews the agent's findings and check report.

The checker may:
- **Accept** — findings are incorporated; document proceeds
- **Return with comments** — agent revises and re-checks
- **Reject** — findings are disputed; escalate to Lead Engineer or Magnus

---

### Stage 5 — Closure

Once the human checker accepts, the DMS item is moved to **Approved** status. The lead engineer's findings remain in `project.db` as the traceability record.

If findings triggered QMS observations or NCRs, these are tracked separately in the QMS register (Angela's responsibility).

---

## Quality Standards

### Findings Logging

All findings must meet the Engineering Findings Table standard. Minimum fields:
- Finding ID (sequential per project)
- Document reference (title, revision, section)
- Finding description (precise, no ambiguity)
- Standard or requirement referenced
- Severity (Comment / Minor / Major / Critical)
- Status (Open / Resolved / Disputed / Closed)

### Review Traceability

Every document review pass must produce a traceable record: findings in `project.db` + a check report posted to the C&A board. Reviews with no logged findings must explicitly note "No findings identified" in the check report — not simply left blank.

### Scope Discipline

Agents review **within their assigned scope only**. Lead engineers do not:
- Modify design intent
- Make engineering decisions
- Communicate findings externally
- Approve documents

---

## Known Constraints

- `board_relation` columns on the C&A board are **not API-writable**. Project routing uses the numeric project ID column (`numeric_mm1vgcya`) as the machine-readable field. (See QMS-035 — C&A board project routing gap.)
- DMS board status codes and label indices vary by project. Always read label mappings dynamically; do not hardcode status indices. (See QMS-029.)

---

## Related Documents

- `020506-29` — WI: Agent LE — Document Review Pass Execution
- `knowledge-base/quality-instructions/findings-table-standard-2026-03-12.md`
- `knowledge-base/quality-instructions/lead-engineer-scope.md`
- `knowledge-base/quality-instructions/dms-author-checker-approver-policy.md`

---

*This document is subject to periodic review. Changes require Angela assessment and Magnus approval.*
