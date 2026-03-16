# Offshore Wind Foundation — LV Electrical Package Patterns
**Discipline:** Engineering — General  
**Applies to:** All offshore wind foundation LV electrical EPC packages  
**Source:** Full review of NSC A Design (Project 10260, RWE), 60 documents, March 2026  
**Author:** Tom (Lead Engineer, Project 10260)  
**Status:** Living document — update as new project evidence is added

---

## Purpose

This document captures repeating patterns and relationships discovered across a complete LV electrical offshore wind foundation delivery package. These are not project-specific — they represent how the package is structured and where errors consistently appear. Use this as a starting point when onboarding a new project or agent to a similar scope.

---

## Package Structure

A complete LV electrical package for an offshore wind monopile foundation (Procon EPC scope) typically consists of:

### Tier 1 — Design Basis
| Document type | Role | Common errors |
|---|---|---|
| LV Design Report | Master design intent and scope statement | ALL→project ID in refs, BTP socket label, IAC boundary not documented |
| Earthing Study | Earthing design basis and calculations | Short study, mostly references; often missing cross-refs to own SLD |
| Illumination Study | Lighting design and lux calculations | BTP lighting WTG-scope (not Procon); summary table vs simulation data discrepancy |
| Power Studies | Load flow and fault calculations | ALL→project ID in refs; cross-check against load list |
| Lightning Rods Assessment | Class assessment, IEC 62305 | References often untraceable; NSC-EMP (Employer) refs may legitimately use "ALL" |

### Tier 2 — Specifications
| Document type | Role | Common errors |
|---|---|---|
| LV Component Specification | Equipment spec for each platform | IP rating vs schematic discrepancy; BTP socket spec inconsistency |
| Electrical Tagging Schedule | RDS-PP master list | Equipment in procurement docs not always in schedule; Nav Aid OVP easy to miss |
| Equipment List | Per-WTG equipment per platform | BTP socket location label systemic error |
| LV Cable List | All LV cables | Signal cable size vs WTG manufacturer requirement; interface tab for pending turbine assignment |
| Earthing Cable List | All earthing cables | "Intermediate Platform" mislabel for ATP; interface tab for pending WTG coordination |

### Tier 3 — Engineering Drawings
| Document type | Role | Common errors |
|---|---|---|
| SLD (Single Line Diagram) | System-level power distribution | BTP socket circuit missing; sparse reference table |
| FECB Schematics | Control cabinet wiring | Revision date chronological errors; role inversion in preparer/approver |
| OVP Schematics | Surge protection wiring | Nav Aid OVP may be absent; IP rating discrepancy |
| LV Layout External/Internal | Platform equipment locations | FECB absent = correct (tower-side); Tower Panel absent = correct (tower mfr) |
| Cable Containment Drawings | Tray routing and support | Zero referenced documents is a common pattern; material: ext=Al, int=SS |
| HV Cable Support Drawings | Array cable mechanical support | IAC scope for cleats = "Generic" in BOM; material 316L; galvanic isolation in sub-assemblies |

### Tier 4 — Studies and Verifications
| Document type | Role | Common errors |
|---|---|---|
| Short Circuit FEA | HV cable support structural verification | ALL→project ID in refs; geometry locked to support drawing — any change needs re-run |
| Dropper Cable Design Note | Technical basis for dropper config | Material typo risk (EN 1.4044 vs 1.4404); MBR and re-termination limits documented here |

### Tier 5 — Per-WTG Data
| Document type | Role | Common errors |
|---|---|---|
| WTG Schedule | Per-turbine equipment fit | Sonar/SHM/Heli light variations; BTP socket label error repeated per WTG |

### Tier 6 — SCADA
| Document type | Role | Common errors |
|---|---|---|
| SCADA Activation Sequence | Commissioning sequence | Self-approval; Magnus occasionally appearing as preparer for re-check |
| SCADA Signal List | FECB-monitored signals | Nav Aid OVP consistently missing; contractor version much lower than NSC revision |
| SCADA Operation Mode | O&M procedure | "For Use" documents containing placeholders — incomplete at issue |

### Tier 7 — Manuals and Installation
| Document type | Role | Common errors |
|---|---|---|
| Installation/O&M Manuals | Field instructions | Low finding frequency; check Scotchkote notes on earthing drawings |
| Cable Glands Instructions | Gland specification per panel | Tags may not match master tagging schedule |
| Check/Test Sheets | Installation hold points | Clara scope only (format and completeness) |

---

## Recurring Error Patterns

### Pattern 1: ALL → Project ID in Reference Tables
**Description:** When a document is derived from a template prepared for all clusters (NSC-HYND-ALL-...), reference table entries often retain the "ALL" project ID even after the title block is corrected to the specific cluster ID (e.g., NSCA, NSCB).

**Why it happens:** Authors correct the title block using find-and-replace but the reference table is a separate structured table — not always swept.

**Checking action:** Open every reference table in every document. Check each row individually, not just the first one. Do not assume a document is clean because the header looks right.

**Severity:** Medium per entry.

---

### Pattern 2: BTP Socket Location Label
**Description:** The BTP (Bolting Platform) socket outlet is consistently mislabelled as "WTG tower - Foundation flange level" rather than "Bolting Platform (BTP)".

**Why it happens:** The label originated in one master document and was copy-pasted into cable lists, equipment lists, schematics, and reports without correction.

**Checking action:** Whenever you see a socket outlet near the BTP level — check its description/location field against the actual BTP elevation from the overview drawing.

**Severity:** Medium (systemic, field team confusion risk).

---

### Pattern 3: Revision History Truncation
**Description:** AS-BUILT drawing sets commonly show only the current revision in the revision history — all prior revisions are absent.

**Why it happens:** CAD/document practice — revision history is not always carried forward when a drawing is reissued or converted.

**Checking action:** Note it per document as Minor. Record it as a systemic observation in the project finding summary. Do not escalate to Major.

**Severity:** Minor per instance; systemic pattern.

---

### Pattern 4: Platform Scope Confusion
**Description:** Reviewers flag absent equipment on the Intermediate Platform as a completeness finding. The Intermediate Platform is an HV cable support structure with no LV equipment.

**Why it happens:** Platform names are not standardised across the industry. Intermediate Platform sounds like it should have general equipment.

**Rule:** Intermediate Platform = HV-only. No LV equipment. Absence from LV documents is always correct. LV platform scope = MAP, TEP, BTP, ATP only.

---

### Pattern 5: Design Report Falls Behind the Drawing Set
**Description:** The LV Design Report sets out design intent, scope boundaries, and interface definitions. As the drawing set matures, errors are corrected in individual drawings but the corresponding section in the design report is not updated. The report increasingly lags the drawing set.

**Why it happens:** The design report is a narrative document — harder to update than a table or drawing. Engineers update the drawing; updating the report feels like rework.

**Checking action:** After completing the full drawing/document review, re-read the design report with cross-doc context. Check:
1. Does the scope boundary description still match what the drawings show?
2. Are interface decisions (IAC scope, WTG manufacturer scope) documented in the report?
3. Are any platform descriptions or circuit descriptions now wrong based on what you found elsewhere?

This second pass on the design report is essential and consistently yields new findings.

---

### Pattern 6: IAC Scope Not Documented
**Description:** The Inter-Array Cable (IAC) contractor supplies and installs HV cable cleats. These are shown as "Generic" in Procon's HV support drawing BOMs. However, the LV Design Report consistently fails to include an explicit statement of this scope boundary.

**Why it happens:** The HV support package and the LV design report are written by different engineers. The scope interface is understood informally but not written down.

**Risk:** Commercial disputes; duplicate supply; field teams uncertain who provides cleats.

**Checking action:** Find the section in the design report covering HV cable containment. Check for an explicit statement that cleat supply and installation is IAC scope.

---

### Pattern 7: SCADA Signal List Omissions
**Description:** The FECB SCADA signal list consistently omits the Nav Aid OVP from monitored signals, even though the Nav Aid OVP appears in the tagging schedule and schematics.

**Why it happens:** Nav Aid equipment is often treated as a maritime/aviation scope item, separate from the main electrical SCADA scope.

**Checking action:** Cross-check every OVP tagged in ENG-00005 (or equivalent tagging schedule) against the FECB SCADA signal list. Any OVP not in the signal list requires explicit scope clarification.

---

### Pattern 8: WTG-Specific Equipment Not Propagated
**Description:** Equipment that applies to only certain WTGs (sonar, SHM, extra heli floodlights) may appear correctly in the WTG schedule per-sheet but not be consistently reflected in:
- Earthing cable list (cable tagged as applicable when it should be N/A, or vice versa)
- LV cable list (signal cables for equipment that is N/A on most WTGs)
- Layout drawings (equipment shown on all generic platform drawings but only installed on select WTGs)

**Checking action:** Identify which WTGs have non-standard equipment fits from the WTG schedule. Then verify the cable lists and earthing lists have the correct apply/N/A flags for those specific WTG numbers.

---

## Cross-Document Consistency Matrix

This table shows which pairs of documents are most likely to have contradictions. Check these relationships explicitly.

| Document A | Document B | What to compare |
|---|---|---|
| LV Design Report | FECB Signal List | SCADA monitoring scope — all OVPs covered? |
| LV Design Report | LV Cable List | Signal cable sizes match? |
| LV Design Report | HV Support Drawing | IAC scope boundary documented? |
| LV Component Spec | OVP Schematics | IP ratings consistent? |
| LV Component Spec | Equipment List | Socket types and quantities match? |
| Tagging Schedule | Cable List | Every tagged item has at least one cable? |
| Tagging Schedule | Equipment List | All tagged equipment appears in list? |
| Tagging Schedule | SCADA Signal List | All monitored OVPs are tagged? |
| Load List | Power Studies | Total load matches? Fault level consistent? |
| Earthing SLD | Earthing Cable List | All cables on SLD appear in list? |
| Earthing Cable List | LV Cable List | No earthing cable miscoded as LV cable? |
| WTG Schedule | Earthing Cable List | WTG-specific cables (sonar, SHM) correctly flagged per WTG? |
| HV Support Drawing | FEA Verification | Geometry locked — any dimension change needs re-run |
| Dropper Design Note | Dropper 2D Layout | Cable config (direct vs crossing) matches? MBR not violated? |
| Dropper Layout | Earthing Drawing | Earthing cable design matches isolation strategy in layout? |
| Cable Glands Doc | Tagging Schedule | Gland tags appear in master schedule? |
| OVP Schematics | SCADA Signal List | Nav Aid OVP monitored? |

---

## Material Reference Summary

| Location | Standard material | Fasteners | Isolation |
|---|---|---|---|
| Internal platforms | EN 1.4404 / 316L SS | A4-70/A4-80 | N/A (SS-to-SS or SS-to-steel) |
| External platforms | EN AW 5083 Al | A4-70/A4-80 (SS) | HDPE at SS/Al interfaces |
| HV cable support | EN 1.4404 / 316L SS | A4-70/A4-80 | HDPE at SS/Al interfaces |
| Dropper sub-assemblies | EN 1.4404 / 316L SS | A4-70/A4-80 | HDPE isolators in beam clamps |
| Trial fit rig | S235 carbon steel | Mixed | N/A (temporary) |
| Earthing cables | Copper | M12 A4 bolts | Scotchkote on all connections |

**Non-compliant:** EN 1.4301 / 304 series — insufficient corrosion resistance, not acceptable offshore.  
**Typo risk:** EN 1.4044 (seen in NSC A) — almost certainly a transposition of 1.4404. Always verify.

---

*Last updated: 2026-03-11 by Tom (Project 10260). Add findings from future projects below this line.*
