# Offshore Wind Foundation Scope Boundaries
**Discipline:** Engineering — General  
**Applies to:** All offshore wind foundation projects (EPC, electrical installation scope)  
**Source:** Project 10260 (NSC A Design) experience, confirmed Magnus Halvorsen 2026-03-11

---

## Core Principle: Foundation vs Tower Scope

Every offshore wind project has a hard boundary between **foundation scope** and **tower scope**. These are always held by different parties. Understanding this boundary is essential for correct document checking — equipment absent from a foundation document may be correct by design, not a completeness error.

### Foundation Scope (Procon's domain)
- All electrical equipment physically mounted on the foundation platforms (MAP, BTP, ATP, subsea, etc.)
- Any equipment Procon designs that is later handed over to the tower manufacturer for physical integration
- Interface definitions for tower-side equipment that Procon cables connect to

### Tower Scope (Tower manufacturer's domain)
- All equipment physically located inside the WTG tower above the foundation flange
- The WTG tower structure itself
- Physical layout and integration of any Procon-designed equipment handed off to the tower manufacturer

---

## Key Scope Rules for Document Checking

### Rule 1 — Procon-designed, tower-integrated equipment
Some equipment is **designed by Procon** but **physically integrated into the tower** by the tower manufacturer. This equipment:
- Will appear in Procon's design documents (specifications, schematics, cable lists, tagging schedules)
- Will **NOT** appear in Procon's physical layout drawings for foundation platforms
- Its absence from layout drawings is **correct by design — do NOT flag as missing**

**Typical examples:** Control cabinets/panels designed by Procon but mounted in the tower (e.g., FECB in NSC A)

### Rule 2 — Tower manufacturer-designed equipment (interface only)
Some equipment is **fully designed and supplied by the tower manufacturer**. Procon only interfaces to it (cables terminate, signals connect). This equipment:
- May appear in Procon documents as an interface reference only (e.g., in cable lists, tagging schedules, SLDs)
- Will **NOT** be sized, specified, or laid out by Procon
- Its appearance in Procon documents is correct (interface reference); its absence from layout drawings is correct

**Typical examples:** Tower main control panels, SCADA panels, tower internal lighting (project-specific — always verify scope)

### Rule 3 — WTG manufacturer-designed equipment (BTP lighting common case)
On many projects, certain foundation platform equipment is supplied by the **WTG/turbine manufacturer** rather than Procon:
- This is typically documented via a Technical Query (TQ) or interface document
- Always check for a TQ that transfers scope before raising absence as a finding
- BTP (Bolting Platform) lighting is a common example where WTG manufacturer takes scope

**How to verify:** Look for a TQ or scope definition letter. If one exists, absence from Procon layout is correct.

---

## Platform Structure Reference (typical — verify per project)

| Platform | Location | Typical Procon scope |
|----------|----------|----------------------|
| MAP (Main Access Platform) | External, lower | Full layout and equipment |
| BTP (Bolting Platform) | Internal/external, mid | Socket outlets (Procon); lighting often WTG mfr scope |
| Intermediate Platform | Internal, mid | HV cable support only on many projects; NO LV equipment |
| ATP (Airtight Platform) | Internal, upper | Full layout and equipment (lights, sockets) |
| TEP (Tower Equipment Platform) | Inside WTG tower | Procon designs equipment; tower mfr handles layout integration |
| Subsea / MP | Below water | Procon scope (ICCP, earthing) |

> ⚠️ Platform names and abbreviations vary by project and customer. Always verify against the project abbreviation list. "TEP" is not standardised.

---

## Lessons from NSC A (Project 10260)

1. **FECB**: Procon-designed, tower manufacturer integrates. Absent from layout drawings → correct.
2. **Tower Power Panel (=MDY10-UC001)**: Tower manufacturer designed and supplied. Procon only runs cables to it. Present in tagging schedule as interface reference → correct.
3. **BTP lighting**: WTG manufacturer scope, confirmed by TQ-HYND-00005. Absent from illumination study and layout drawings → correct.
4. **Intermediate Platform**: HV array cable support structure only — no LV equipment. Absent from all LV documents → correct.
5. **ATP lights (=BMA82-EA101/102)**: Full Procon scope. Must appear in layout, equipment list, tagging schedule, cable list.

---

## Checking Guidance

Before raising a "missing equipment" finding on a layout or equipment list:
1. Is the equipment tower-side? → Not Procon layout scope
2. Is there a TQ transferring scope to the WTG manufacturer? → Not Procon scope
3. Is the platform HV-only (e.g., Intermediate Platform on many projects)? → LV equipment absence is correct
4. Is the equipment designed by Procon but handed to tower mfr for integration? → Won't appear in layout drawings

If none of the above apply → raise the finding.

---

## Material Compatibility — Fasteners and Galvanic Isolation

**Rule:** In offshore wind foundation assemblies, aluminium structural components (typically EN AW 5083) are almost always fastened with stainless steel (A4-70 or A4-80). Aluminium fasteners are not used for structural connections — they are mechanically unreliable. Exception: certain special rivets, rare cases only.

**Implication for checking:**
- SS fasteners through AL components = mixed material pairing → galvanic isolation IS required at all contact interfaces
- Seeing SS fasteners + AL brackets is a reliable indicator that galvanic isolation measures (HDPE sleeves, isolation washers, etc.) should be present
- AL-to-AL contact interfaces should NOT be isolated — direct metal contact is correct
- AL-to-steel structure interfaces → isolation required (AL is anodic relative to steel in marine environment)

**What to verify (Alex scope):**
1. Are isolation sleeves present at all AL-SS contact points?
2. Are AL-to-AL interfaces free of unnecessary isolation material?
3. Is isolation material (HDPE) appropriate for the environment and load case?

**Source:** NSC A (project 10260) review experience, confirmed Magnus Halvorsen 2026-03-11.

---

## Stainless Steel Grade Requirements — Offshore Foundations

**Minimum grade:** EN 1.4404 (equivalent: AISI 316L) for all stainless steel structural components, brackets, fasteners, cable trays, and fittings on offshore wind foundations.

**Not acceptable:** EN 1.4301 (AISI 304) and lower grades — insufficient corrosion resistance for offshore marine environment.

**Acceptable alternatives:** Duplex steels (e.g. EN 1.4462 / 2205, EN 1.4410 / 2507 super duplex) and higher alloys are acceptable — they exceed the minimum requirement.

**Material selection logic — external vs internal:**
- **External platforms** (MAP, external BTP): Aluminium (typically EN AW 5083) is common for cable trays and brackets because external structures often use aluminium handrails. Matching materials avoids galvanic coupling at the bracket-to-structure interface.
- **Internal platforms** (ATP, internal casette areas): Stainless steel (EN 1.4404/316L) is standard. Internal structure is typically carbon steel or stainless — 316L is compatible.

**When checking drawings and specifications:**
- Verify any SS grade called out is 1.4404/316L or better
- Flag any use of 304/1.4301 as a finding (non-compliant for offshore)
- If material is listed only as "stainless steel" without a grade — flag for clarification

**Source:** Project 10260 (NSC A Design) review, confirmed Magnus Halvorsen 2026-03-11.
