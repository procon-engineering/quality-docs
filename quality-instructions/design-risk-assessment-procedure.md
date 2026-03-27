# Design Risk Assessment and Register Procedure

**Document ID:** 020506-22
**Version:** 1.0
**Date:** 2026-03-27
**Author:** Hazel (Risk Specialist)
**Approved by:** Pending — Magnus Halvorsen
**Status:** Under Review
**ISO 9001:2015 Clause:** 6.1, 8.3.3

---

## 1. Purpose and Scope

### 1.1 Purpose

This procedure describes the end-to-end process for raising, scoring, mitigating, and closing Design Risk Assessment (DRA) items on Procon engineering projects. It ensures that design-stage risks to personnel safety, system availability, and regulatory compliance are systematically identified, evaluated with reference to published industry data, and reduced to As Low As Reasonably Practicable (ALARP).

### 1.2 Scope

This procedure applies to all Procon EPC projects in the Engineering workspace. A DRA is required for every project from the start of the design phase and must be maintained throughout the project lifecycle until handover.

**Typical triggers for initiating a DRA:**
- Project kick-off / design basis established
- New project added to the Engineering workspace on monday.com

**Out of scope:**
- Construction-phase safety plans and task risk assessments (managed by the site team)
- Supplier/sub-contractor risk registers (managed by procurement)
- Process safety studies (HAZOP/HAZID) — these feed into the DRA but are conducted separately

---

## 2. DRA Board Structure

Each project has a dedicated DRA board on monday.com, created from the Design Risk Assessment Template (board 5093512344) in the Engineering workspace (5935004).

### 2.1 Board Groups

Risk items are organised by discipline category:

| Group | Typical Content |
|-------|----------------|
| **Regulatory** | Statutory compliance items — ATEX, lifting regulations, noise, extreme weather |
| **Electrical Hazards** | Arc flash, body currents, cable integrity, earthing, lightning, IP protection |
| **Controls & Interfaces** | SCADA/WTG interfaces, safety-critical data links, nav aid systems |
| **Mechanical & Human Factors** | Dropped objects, falls from height, slip/trip, boat landing, moving parts |
| **Structural & Environmental** | Water ingress, corrosion, escape routes, grating failure, navigation lights |
| **Fire & Thermal** | Cable fire, arc fault fire, fire detection, hot surfaces, thermal radiation |
| **Closed / Accepted** | Items with status Closed or Accepted — retained for audit trail |

### 2.2 Board Columns

Each item contains the following fields:

| Column | Purpose |
|--------|---------|
| Risk ID | Unique project reference (e.g. NSCB-R-001) |
| Hazard Description | Clear statement of the hazard and its consequence |
| Affected Area / System | Physical location or system scope |
| Pre-Mit Risk Level | Risk level before mitigations (Low / Medium / High / Critical) |
| Pre-Mit Score | Numeric 5×5 matrix score before mitigations |
| Technical Measures (T) | Inherently safe design and safeguarding measures |
| Organisational Measures (O) | Procedures, training, permit-to-work |
| PPE / Personal Measures (P) | Personal protective equipment requirements |
| Mitigation Hierarchy | Highest level of mitigation applied (per ISO 12100 step 1/2/3) |
| Post-Mit Risk Level | Risk level after all mitigations applied |
| Post-Mit Score | Numeric 5×5 matrix score after mitigations |
| ALARP Justification | Written justification where residual risk remains Medium or High |
| Owner | Lead engineer responsible for the item |
| Critical Residual Risk | Flag — requires Engineering Director approval to close |
| Status | Item lifecycle state (Open / In Mitigation / Closed / Accepted) |
| Triggered by Finding | Reference to QMS finding or open point that raised this item |
| Last Review Date | Date of most recent review |
| Notes | Supplementary information |

---

## 3. Risk Scoring

### 3.1 5×5 Matrix

Procon's DRA board uses a Probability × Severity matrix to produce a numeric risk score:

**Probability (1–5):**

| Value | Description |
|-------|-------------|
| 1 | Remote — conceivable but not expected in project lifetime |
| 2 | Unlikely — could occur once in project lifetime |
| 3 | Possible — may occur several times |
| 4 | Likely — expected to occur regularly |
| 5 | Almost certain — occurs frequently |

**Severity:**

| Value | Category | Description |
|-------|----------|-------------|
| 1 | Negligible | No injury or first aid only |
| 2 | Minor | Medical treatment, no lost time |
| 5 | Moderate | Lost time injury (LTI) |
| 10 | Major | Permanent disability |
| 25 | Critical | Fatality |

**Risk Score = Probability × Severity**

**Risk Bands:**

| Score | Level | Colour |
|-------|-------|--------|
| 1–6 | Low | Green |
| 7–14 | Medium | Orange |
| 15–24 | High | Red |
| 25 | Critical | Pink |

> **Note:** The matrix score populates the Pre-Mit Score and Post-Mit Score numeric columns and sets the Pre-Mit Risk Level and Post-Mit Risk Level status fields. Scores are set by the lead engineer at item creation.

### 3.2 Authoritative 3-Tier Rating

In addition to the 5×5 matrix, all DRA items are subject to an authoritative evidence-based review by Hazel (Risk Specialist). This review produces a written rating — **HIGH / MEDIUM / LOW** — based on published industry incident data (G+ annual statistics, ESAW, IOGP) rather than subjective matrix scoring.

The 3-tier rating is posted as an update on each board item and is **the authoritative risk assessment of record**. The 5×5 matrix scores are retained for backwards compatibility and visual consistency.

**3-tier criteria** (see `scoring-methodology.md` for full detail):

| Rating | Criteria |
|--------|---------|
| HIGH | HP rate >20%, or incident rate >1.0/Mhrs, or fatality realistic with standard controls |
| MEDIUM | HP rate 5–20%, or LTI is most likely severe outcome |
| LOW | HP rate <5%, or first aid is most likely outcome with standard controls |

Every 3-tier rating **must include a written citation** from G+ annual data, ESAW, IOGP, or another named source. Bare ratings without citation are not accepted.

---

## 4. Mitigation Hierarchy

All mitigation measures are documented in three dedicated columns — Technical (T), Organisational (O), and PPE/Personal (P) — and classified against the ISO 12100 three-step hierarchy:

### Step 1 — Inherently Safe Design (highest priority)
Eliminate the hazard through design. Examples:
- Remote switching to eliminate arc flash exposure
- Halogen-free LSZH cables to eliminate toxic gas generation in fires
- Normally-unmanned philosophy to minimise exposure time

### Step 2 — Safeguarding
Reduce risk through technical barriers where Step 1 is not practicable. Examples:
- IAC type-tested switchgear (internal arc fault containment)
- RCD protection on all LV circuits
- UPS backup for emergency lighting
- IP-rated enclosures in marine environments

### Step 3 — Information for Use (lowest priority)
Supplement Steps 1 and 2 with procedural and personal controls. Examples:
- Five electrical safety rules
- Permit-to-work systems
- Toolbox talks and personnel induction
- PPE requirements

The **Mitigation Hierarchy** column on the board records the highest step achieved for each item. Step 3-only mitigations are flagged for review — the lead engineer must demonstrate why Steps 1 or 2 are not practicable.

---

## 5. ALARP Justification

A written ALARP justification is required for any item where the post-mitigation risk level remains **Medium or High**.

The justification must:
1. State the residual risk level and explain why further reduction is not practicable
2. Reference the specific mitigations that have already been applied (Steps 1–3)
3. Identify any further measures considered and explain why they were rejected (grossly disproportionate cost, technical infeasibility, or introduction of new hazards)
4. Reference comparable industry practice where relevant (e.g. G+ member project benchmarks, applicable standards)

ALARP justifications are entered in the **ALARP Justification** column on the board item and are reviewed by Hazel as part of the specialist review.

Items with post-mitigation rating of **Critical** require Engineering Director (Magnus Halvorsen) approval before the item can be accepted. The **Critical Residual Risk** checkbox must be ticked, and Magnus must explicitly approve closure via the board update thread.

---

## 6. Roles and Responsibilities

| Role | Responsibility |
|------|---------------|
| **Lead Engineer** (Tom, Bart, Rosa, Kai, Genny, Angus, Elise, Duncan, Morgan, Cedar, Emmy) | Creates and owns DRA board items; sets 5×5 matrix scores; documents mitigations in T/O/P columns; progresses item status; requests Hazel review |
| **Hazel (Risk Specialist)** | Reviews all items; assigns 3-tier evidence-based rating with citation; assesses mitigation adequacy; writes ALARP justification text where required; flags missing hazard categories |
| **Engineering Director (Magnus Halvorsen)** | Approves closure of Critical residual risk items; resolves scope/design changes that affect risk |
| **Angela (QMS)** | Links DRA findings to QMS open points and NCRs; manages QHSE register entry for this procedure |
| **Clara (Doc Controller)** | Formal document control — version numbering, QHSE register linking |
| **Alex (Electrical Specialist)** | Technical input on electrical hazard mitigations — referenced as implementing engineer, not DRA owner |

---

## 7. Item Lifecycle

Each DRA item progresses through the following states:

```
Open → In Mitigation → Closed
                     ↘ Accepted
```

| Status | Meaning |
|--------|---------|
| **Open** | Hazard identified; mitigations not yet fully implemented |
| **In Mitigation** | Mitigations are defined and in progress; risk not yet reduced to final level |
| **Closed** | All mitigations implemented and verified; residual risk is Low or ALARP-justified |
| **Accepted** | Residual risk acknowledged and formally accepted by the responsible party; item moved to Closed/Accepted group |

**Transition rules:**
- Lead engineer progresses status from Open → In Mitigation when mitigation design decisions are made
- Hazel confirms residual risk rating before transition to Closed
- Critical residual risk items require Magnus approval before Accepted status is set
- Closed and Accepted items are moved to the Closed/Accepted board group; they are not deleted

---

## 8. Integration with DMS and QMS

### 8.1 Linking Mitigations to Design Documents

Each mitigation measure should reference the **specific design document** where it is implemented. This creates a traceability chain:

> **Risk → Mitigation → Design Document → Verification**

When updating a DRA item:
- Reference the document by DMS name and version (e.g. "NSC-B-CAB-001 Rev B — Cable Schedule")
- Note which design decision implements the mitigation
- If no document yet exists that implements the mitigation, flag the item as **"design action required"** in the Notes column

### 8.2 QMS Findings

If a DRA review identifies a systemic process issue — a missing hazard category across multiple projects, a recurring mitigation gap, or a scoring inconsistency — this is routed to Angela (QMS) as a QMS observation, not raised directly as an NCR.

**Routing:** Hazel writes a JSON observation file to Angela's inbox (`~/.openclaw/workspace-qms/inbox/`). Angela assesses and recommends action to Magnus.

DRA board items may reference a QMS finding via the **Triggered by Finding** column — this is used when a DRA item was raised in response to a QMS open point or lesson learned.

---

## 9. Review Cadence

| Trigger | Review Action |
|---------|--------------|
| **Project kick-off** | Full DRA board populated by lead engineer; full scoring review by Hazel |
| **Phase gate (design → fabrication)** | Full re-review; confirm all Open items have mitigations defined |
| **Phase gate (fabrication → commissioning)** | Re-review; commissioning phase applies operations-level risk multiplier (2×) |
| **Significant design change** | Affected items re-opened and re-scored |
| **Incident on any Procon project** | Trigger review of equivalent items on all active DRA boards |
| **Annual** | Review against latest G+ annual statistics; update ratings if data changes |
| **Post-handover** | Final DRA status confirmed; all items Closed or Accepted before project closure |

---

## 10. Standards and References

| Standard | Application |
|----------|------------|
| ISO 12100:2010 | Risk assessment and risk reduction — general principles |
| IEC 61892-series | Mobile and fixed offshore units — electrical installations |
| IEC 62271-200/214 | HV switchgear — internal arc classification |
| DIN VDE 0100-410 | LV installation — protection against electric shock |
| DIN VDE 0105-100 | Operation of electrical installations — five safety rules |
| DGUV-V3 | Electrical testing and inspection |
| EN 1838 / EN 12464 | Emergency lighting and workplace illumination |
| G+ Annual Statistics | Offshore wind industry incident data — primary citation source |
| ESAW (Eurostat) | European occupational accident statistics |
| IOGP Safety Performance Indicators | Offshore industry benchmarking |
| `scoring-methodology.md` | Procon 3-tier evidence-based scoring rules (internal) |

---

## Revision History

| Version | Date | Author | Change |
|---------|------|--------|--------|
| 1.0 | 2026-03-27 | Hazel | Initial issue |
