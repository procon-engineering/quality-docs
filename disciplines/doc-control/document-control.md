# Document Control Rules — Company-Wide

Apply to all document checking across all projects and disciplines.

## Version Number Check (DMS vs Document) — ALL PROJECTS

**Rule:** When reviewing any document, always cross-check the version number recorded in the DMS against the version number stated inside the document itself (in the title block or revision history table).

- **Version** = internal/contractor version (increments for every change, including minor ones). May be labelled "Contractor Version", "Version", "Internal Version", or similar — terminology varies by customer.
- **Revision** = external release number. These are NOT the same field. Do not confuse them.

**Severity:**
- **Minor** — Version number not found in the document (field missing or not identifiable)
- **Major** — Version number is present in the document but does not match the DMS

**Process:** Tom will provide the DMS version number in the dispatch file. Clara checks it against what is stated inside the document.

*Source: Magnus feedback 2026-03-11*

## Document Status vs Reason for Issue

**Rule:** These are separate fields in the customer document management process. Do not conflate them.

- **Document Status** (As-built, For Use, Draft, etc.) — the lifecycle stage of the document
- **Reason for Issue** (Review, Information, Approval, Construction) — the purpose of this specific revision release

These categories relate to customer-specific document control workflows. Different customers may use different terminology. Always understand the customer's document control process before reviewing revision tracking.

*Source: Magnus feedback 2026-03-10*

## Revision vs Version — Internal Tracking

**Rule:** Internal document versions increment for every minor change (drafts, internal loops, small corrections). Revisions are the external release tracker only. Version numbers are NOT required to be sequential relative to revisions — gaps between version numbers associated with consecutive revisions are expected and by design. Do NOT flag version number gaps as findings.

- **Version** = internal tracker (can jump, e.g. v8 → v12 between two consecutive revisions)
- **Revision** = external release number (sequential: 01, 02, 03…)

*Source: Magnus feedback 2026-03-10*

## Self-Approval, Role Overlap, Checker/Approver — NOT Tom's Scope

**Rule:** Self-approval (checker = approver, or preparer = approver) and role inversions are normal in a small engineering team. They are acceptable for re-checks and waived revisions. This is handled manually by Procon management.

- **Tom:** Do NOT raise findings on self-approval, role overlap, or role inversion. Flag at most as **Info** if something looks structurally unusual.
- **Clara:** May note if check type is undeclared, but do not raise on the personnel overlap itself.

Primary checkers at Procon: Andreas Eltervåg (AELT), John Lihasi (JLIH), Mads Matthai (MKMA). Primary approver: Magnus Halvorsen (MKHA). For full-checks these roles should be independent, but re-checks and waivers allow overlap. This is not a document review concern.

*Source: Magnus feedback 2026-03-11*

## Contractor Version Gaps — NOT A FINDING

**Rule:** Gaps in contractor version numbers are entirely normal. Versions increment for every internal change including minor ones; the revision history table does not need to list every internal version. Do not flag version number gaps.

*Source: Magnus feedback 2026-03-11 (confirmed earlier 2026-03-10)*

## Document Status vs Reason for Issue — IGNORE FOR NOW

**Rule:** Do not flag inconsistencies between the Document Status field and the Reason for Issue field. A standard scheme for these combinations has not yet been defined at Procon. This will be addressed when a standard is established.

*Source: Magnus feedback 2026-03-11*

## Check Types — Full-Check, Re-Check, Waived

**Rule:** Documents go through different check types depending on the scope of changes. Not all revisions require a fully independent checker and approver.

| Check type | When used | Checker/Approver requirement |
|------------|-----------|------------------------------|
| **Full-check** | First issue, major changes, new sections | Independent checker AND independent approver (different people, different from preparer) |
| **Re-check** | Targeted corrections, updates to specific sections | Checker and approver may be the same person |
| **Waived** | Very minor edits (typo fixes, reference updates) | Checker and/or approver may be absent |

**How to check:** The declared check type should be stated in the revision history or accompanying documentation. If not stated, it cannot be confirmed — flag as Minor and request clarification on what check type was declared.

**Severity for undeclared check type:** Minor — "Check type not stated; cannot confirm whether waiver applies."

*Source: Magnus feedback 2026-03-11*

## Checker/Approver Waiver for Minor Revisions

**Rule:** Documents require a Checker and Approver in the revision history. However, this can be waived if the changes from the previous revision are minor. To assess whether a waiver is justified, review the description of changes for the revision in question. If changes are minor (e.g., reference updates, scope label corrections), a missing checker/approver is acceptable. If changes are substantial (new sections, updated calculations, design changes), the absence of a checker/approver is a Major finding.

**When flagging:** Use the "Description of Revisions" table to assess change scope before raising the severity.

*Source: Magnus feedback 2026-03-10*

## Reference Table Completeness

**Rule:** All entries in a document's reference table must have traceable document numbers. Entries with missing document IDs should be flagged as findings.

*Source: ENG-00006 review — Ref [28] and [29] had no document IDs*

## Platform/Section Coverage

**Rule:** If a document's scope includes multiple physical areas, components, or subsystems, ALL of them must be explicitly addressed. If a subsystem has nothing in scope, state this explicitly (e.g., "No LV equipment is installed on the Intermediate Platform"). Missing sections = documentation gap.

*Source: ENG-00006 review — Intermediate Platform not addressed in Section 4.1, confirmed by Magnus*

## Equipment Detail Level

**Rule:** Pay attention to junction boxes, socket outlets, and similar equipment. Extract specific configurations (voltage ratings, outlet types, protection devices, quantities) into equipment lists. These details are critical for cross-checking against schematics, cable lists, and procurement documentation.

*Source: Magnus feedback 2026-03-10*
