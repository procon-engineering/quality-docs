# Document Review — Findings Table Standard
**Applies to:** All Procon engineering document review programmes  
**Author:** Tom (Lead Engineer, Project 10260)  
**Date:** 2026-03-12  
**Status:** Draft — for Engineering Director approval before adoption

---

## Purpose

This document defines the standard column structure, severity levels, and category rules for the findings table used in Procon's engineering document review process. All findings recorded by Tom (NSC A), Bart (NSC B), Clara, and Alex must use these definitions consistently so findings can be consolidated, compared across projects, and reported to clients and the Engineering Director in a uniform format.

---

## Findings Table Columns

| Column | Type | Description |
|---|---|---|
| `id` | Integer, auto-increment | Unique finding ID within the project. Never reuse a number, even if a finding is closed. |
| `doc_id` | Text | The Procon document identifier (e.g. `ENG-00006`, `TQ-HYND-10005`). Matches the document register. |
| `pass` | Integer (1 or 2) | Review pass: **1** = structural/index pass, **2** = cross-document check pass. Most actionable findings come from Pass 2. |
| `severity` | Text | One of: `Major`, `Medium`, `Minor`, `Info`. See definitions below. |
| `category` | Text | One of the defined categories below. |
| `description` | Text | The finding text. See writing rules below. |
| `status` | Text | One of: `open`, `closed`, `not-a-finding`, `closed-deviation`. |
| `found_date` | Date (YYYY-MM-DD) | Date the finding was recorded. |
| `reviewer` | Text | Who raised the finding: `Tom`, `Bart`, `Clara`, `Alex`. |
| `resolution` | Text | Populated when status changes from `open`. Describes how the finding was resolved or why it was closed. |

---

## Severity Levels

### Major
**Definition:** An error that, if not corrected, will result in wrong hardware being fabricated or installed, a safety risk, a regulatory non-compliance, or a contractual breach.

**Use when:**
- A material or component is specified incorrectly (e.g. wrong SS grade, wrong cable rating)
- A calculation or study result is wrong or internally contradictory
- A document is issued as "For Use" or "For Approval" but contains placeholder content that makes it non-functional
- A non-compliance with a mandatory IEC or applicable standard cannot be resolved by a direct alternative
- A scope interface that is commercially significant is not documented
- The same critical error appears across multiple documents (systemic)

**Examples from NSC A:** EN 1.4044 material typo (ENG-00046), 9 placeholder notes in FECB operation mode document (ENG-00032), IAC scope boundary not documented in design report (ENG-00006).

---

### Medium
**Definition:** A significant error or gap that must be corrected before the document is approved for client issue, but does not immediately result in wrong hardware or a safety risk.

**Use when:**
- A cross-document inconsistency where two documents give different values for the same item (e.g. BTP socket location described differently in two documents)
- A reference table entry uses an incorrect document ID (e.g. ALL instead of NSCA) — per entry
- Equipment is absent from a document where it should appear, and absence is not explained by a scope rule
- An IP rating in the specification does not match the schematic
- A signal or monitoring point is missing from the SCADA signal list without a scope justification
- A cable specification conflicts with a WTG manufacturer requirement documented in a TQ

**Examples from NSC A:** BTP socket location label "WTG tower - Foundation flange level" (systemic, ENG-00013/00016/00029), ALL not NSCA in reference tables (ENG-00015/00027/00042), IP66 vs IP55 discrepancy (ENG-00018/ENG-00010).

---

### Minor
**Definition:** A document quality issue, minor inconsistency, or administrative gap that does not affect technical correctness but should be corrected before final issue.

**Use when:**
- Revision history is truncated (prior revisions missing)
- DMS version does not match document title block version (not found case)
- A referenced document has no document ID (untraceable reference)
- An abbreviation used in the document is not defined in the abbreviation list
- A revision date is chronologically inconsistent (later revision has earlier date)
- A self-reference appears in the reference table
- A typographical error in non-critical text

**Examples from NSC A:** Revision history truncated across drawing set, ENG-00007 Rev 03 date before Rev 02, self-reference in ENG-00006 reference table, "Ceanex" instead of "Seanex" (ENG-00046).

---

### Info
**Definition:** An observation for awareness only. No corrective action required. Used to flag scope confirmations, design decisions on record, or patterns that do not rise to a finding but are worth noting.

**Use when:**
- Self-approval or checker = approver (handled at management level, not a technical finding)
- A scope assignment is confirmed as correct (e.g. confirming BTP lighting is WTG manufacturer scope)
- A non-standard practice is noted but accepted (e.g. contractor version numbering gap)
- A data point is recorded for cross-checking later (e.g. sonar scope = NC255 and NC265 only)

**Examples from NSC A:** Role overlap in FECB activation sequence (ENG-00033), sonar WTG scope confirmation (ENG-00029), Scotchkote requirement noted on earthing drawing (ENG-00082).

---

## Category Definitions

| Category | Use for |
|---|---|
| `Technical` | Engineering technical content — wrong specification, wrong calculation, wrong material, wrong rating, wrong value |
| `Standards` | Non-compliance with an applicable IEC standard or mandatory industry requirement |
| `Completeness` | Content that should be present but is missing — missing platform, missing equipment, missing reference, missing abbreviation |
| `Consistency` | Cross-document mismatch — same data appears differently in two or more documents |
| `Doc Control` | Document management issues — wrong document ID, version mismatch, incomplete revision history, DMS misalignment |
| `Scope` | Scope boundary not defined, incorrectly defined, or incorrectly attributed to a party |

A finding should be assigned the category that best describes the **primary nature of the issue**. If a finding spans two categories (e.g. a missing SCADA signal that is both a completeness issue and a scope issue), choose the more specific one — `Scope` over `Completeness` in that example.

---

## Finding Description Writing Rules

Good finding descriptions are:

1. **Specific** — name the section, figure, table, or row where the issue occurs. "Reference table entry [2] cites NSC-HYND-ALL-FOU-ENG-00016" is better than "wrong document ID in references."
2. **Self-contained** — anyone reading the finding without opening the document should understand what is wrong. Include the wrong value and what the correct value should be, where known.
3. **Factual** — describe what is, not what you think the author intended. Avoid "the author probably meant..." unless it is directly relevant to the severity.
4. **Action-implied** — the description should make clear what correction is needed, even if you don't explicitly state it.

**Template:** `[Location in document]: [What is wrong]. [What it should be / what the consequence is].`

**Example:**
> *ENG-00046 Section 3.5: CMS material specified as EN 1.4044. This is not a recognised offshore structural grade and is almost certainly a typographical error for EN 1.4404 (AISI 316L). Procurement or fabrication based on this specification could result in supply of incorrect material.*

---

## Status Values

| Status | Meaning |
|---|---|
| `open` | Finding recorded, awaiting contractor or author response/correction |
| `closed` | Finding resolved — document corrected and re-issued, or equivalent action taken |
| `not-a-finding` | On review, the issue is not actually an error — the document is correct. Resolution field must explain why. |
| `closed-deviation` | Finding acknowledged but accepted as a deviation — e.g. minor revision with no checker, approved by Engineering Director. Resolution field must record who approved and on what basis. |

---

## Rules That Are NOT Findings

The following are explicitly not findings at Procon, by standing decision. Do not record them:

| Pattern | Reason |
|---|---|
| Checker = Approver / self-approval | Small team workflow; handled at management level; Info at most |
| Contractor version number gaps between revisions | By design in contractor version tracking |
| Document Status vs Reason for Issue mismatch | No project standard defined yet; ignore until standard exists |
| Intermediate Platform absent from LV documents | HV-only platform; absence is correct by design |
| FECB absent from Procon foundation layout drawings | Tower-side scope; absent by design |
| Tower Panel (MDY10-UC001) absent from Procon layouts | Tower manufacturer scope; Procon interface only |
| BTP lighting absent from Procon scope | WTG manufacturer scope (verify per TQ); absent by design |
| NSC-EMP-ALL references in Employer documents | "ALL" may be legitimately correct for Employer documents; distinguish from NSC-HYND-ALL which must be NSCA |
| Trial fit drawing components in S235 | Temporary mockup use only; not production hardware |
| 3D model content (visual-only documents) | Text extraction not possible; mark as reviewed with visual inspection flag |

---

## Reviewer Scope Summary

| Reviewer | Checks |
|---|---|
| **Tom / Bart** (Lead Engineer) | Cross-document consistency, design intent, platform coverage (MAP/TEP/BTP/ATP), scope completeness, scope boundary documentation |
| **Clara** | DMS version vs document version, revision dates, ALL→NSCA corrections (every reference entry), reference traceability (document IDs present), abbreviation list completeness, title block completeness |
| **Alex** | IEC standards compliance, cable sizing and type, protection coordination, earthing design, IP ratings, material grades, galvanic isolation, specialist electrical calculations |

Findings from Clara and Alex are recorded in the project findings table by the Lead Engineer after review. `reviewer` field is set to `Clara` or `Alex` as appropriate.

---

*This document should be adopted into the Engineering Charter as a formal procedure. Approval: Engineering Director.*
