# Job Description — Mechanical Engineer (DRAFT)
**Company:** Procon AS  
**Function:** Engineering  
**Discipline:** Mechanical / Structural  
**Reports to:** Lead Engineer (project) / Engineering Director  
**Prepared by:** Tom (Lead Engineer, Project 10260)  
**Date:** 2026-03-12  
**Status:** DRAFT — for HR review and formatting

---

## About the Role

Procon designs and installs electrical systems on offshore wind turbine foundations. While the package is called an "LV electrical package," it contains a substantial mechanical engineering scope — the structural systems that support, protect, and route the cables and equipment on the foundation platforms.

The Mechanical Engineer owns this structural scope: cable support structures, equipment mounting frames, cable containment routing, and the dropper cable system that connects the offshore grid into the turbine. Your designs go offshore on every foundation. They are fabricated, installed, and expected to survive 25+ years in a corrosive marine environment with minimal maintenance access. Precision and material discipline are not optional.

This is a delivery-focused role working within a defined project scope alongside the Electrical Engineer, with the Lead Engineer setting the overall technical direction.

---

## Responsibilities

### 1. Mechanical and Structural Design Deliverables
Own the production and revision of the mechanical engineering documents in the project package:
- **Cable support structures** — the primary mechanical deliverable; structural bracket and profile assemblies that hold the HV inter-array cable as it runs up the foundation (multiple configurations per project)
- **Equipment mounting frames** — structural support frames for LV cabinets, ICCP enclosures, and other topside equipment
- **Cable containment drawings** — routing layouts for cable trays on internal and external platforms, coordinated with the electrical engineer's layout drawings
- **Dropper cable system** — mechanical design of the flexible HV cable section at the top of the support structure: dimensions, minimum bend radius (MBR), re-termination limits, configuration variants (direct, crossing)
- **Sub-assembly drawings and BOMs** — manufacturing-ready detail drawings with full parts lists; used directly by fabricators
- **Trial fit drawings** — temporary steel mockup structures for fit-check before offshore fabrication; clearly distinguished from production drawings

Every drawing and BOM you issue has your name on it. The fabricator works from your drawing. If the drawing is wrong, the hardware will be wrong.

### 2. Material Selection and Corrosion Strategy
Offshore wind foundations are a harsh environment. Material selection is a core part of every mechanical design:
- Specify correct stainless steel grades — minimum EN 1.4404 / AISI 316L for all structural SS components; flag any use of 304/1.4301 series immediately
- Apply the correct material for the platform context — aluminium (EN AW 5083) for external platforms to match the platform structure; SS 316L for internal platforms
- Specify and verify galvanic isolation — HDPE insulation plates, sleeves, and washers at all SS-to-aluminium contact interfaces; this is a design requirement, not a site option, and must be explicitly called out in the BOM
- Fasteners — A4-70 / A4-80 stainless steel throughout; aluminium fasteners are not used for structural connections

### 3. Structural Verification Handoff
Structural analysis and FEA is performed by a dedicated structural specialist — not by the Mechanical Engineer. Your responsibility is to ensure the CAD model handed off is clean, complete, and ready to be worked on without the specialist needing to chase you for information:
- Geometry fully resolved before handoff — no placeholder dimensions, no unresolved clashes, no open decisions
- Material, wall thickness, and fastener data complete in the model and consistent with the drawing
- Load introduction points and boundary conditions clearly communicated (e.g. where the cable clamp loads act, what transport loads apply)
- Flag to the Lead Engineer when a design change affects geometry that has already been structurally verified — the structural specialist decides whether a re-run is needed, but you need to raise the flag

### 4. Scope Interfaces
The mechanical scope has defined boundaries with other parties — knowing these is as important as the design itself:
- **IAC contractor** — supplies and installs the HV cable cleats on Procon's support structure; cleat material and installation is IAC responsibility. "Generic" in Procon's BOM for cleat items is correct. Confirm the design report documents this boundary explicitly
- **Foundation manufacturer (JBO)** — Procon coordinates with JBO on platform penetrations, structural fixing points, and weld interfaces; any changes to interface geometry must be formally coordinated
- **Electrical engineer** — cable support geometry and tray routing must accommodate the cable sizes, bend radii, and routing decisions made by the electrical engineer; these disciplines must be coordinated, not designed in parallel isolation

### 5. Installation and Commissioning Support
- Produce and maintain the equipment support frame installation check and test sheet
- Respond to site fit-up queries — clearances, fastener substitutions, installation sequence
- Review site redline mark-ups and assess whether geometry changes require a drawing revision or can be accepted as minor deviations
- Update as-built documentation

### 6. Document Quality
- Correct use of project document ID format
- BOM part numbers and quantities must match the drawing — fabricators use both simultaneously
- Revision history complete; geometry changes must be clearly described in the revision description
- Sub-assembly drawing revisions must be consistent with the assembly drawing they reference

---

## Decision Authority

### You can decide independently:
- Bracket dimensions and profile sizing within the verified design envelope
- Material selection within the project material specification
- Fastener grade and size (A4-70/A4-80) and torque values per applicable standard
- Galvanic isolation detail (HDPE type, thickness, sleeve vs plate) based on interface geometry
- BOM part number selection for standard catalogue items (profiles, fasteners, washers)
- Installation sequence and method within the design intent

### You decide, then inform the Lead Engineer:
- Any geometry change to a structure that has been structurally verified — even small changes can affect the verification
- Material substitution (e.g. a profile size that is unavailable and requires a like-for-like substitution)
- A new structural configuration not covered by existing drawings or verification

### You must escalate before acting:
- Any design change that affects scope, cost, or programme
- A change to an interface with JBO (platform geometry, penetration positions, weld locations)
- A structural concern or fit-up issue identified during design, fabrication review, or site installation — route to the structural specialist via the Lead Engineer
- Any use of a material grade below the project minimum (EN 1.4404/316L) — this is a Major non-conformance
- A geometry change on a structure that has already been structurally verified — flag to the Lead Engineer; the structural specialist decides whether re-analysis is needed

---

## Typical Tasks

### In a design phase week:
- Produce a sub-assembly drawing for a new cable support configuration — bracket, profile, BOM; coordinate cable routing clearances with the electrical engineer
- Update the dropper cable layout drawing to reflect a revised cable configuration; check MBR is not violated; note whether the change affects the structural verification geometry
- Prepare a structural brief for the FEA subcontractor — geometry, load cases, material data, acceptance criteria
- Hand off a completed cable support CAD model to the structural specialist — geometry resolved, materials defined, load points documented
- Revise a cable containment drawing to reflect a platform layout change; update reference list

### In a procurement and fabrication phase week:
- Review a fabrication drawing from the structural fabricator against the Procon design drawing; mark up dimensional deviations and material non-conformances
- Review a material certificate (EN 1.4404 mill cert) for compliance with project specification
- Answer a fabricator question about weld detail at a bracket-to-profile interface — provide written response with drawing reference
- Update a BOM to reflect a verified profile substitution; note revision reason in history

### In an installation and commissioning phase week:
- Complete the equipment support frame installation check sheet; record torque values and dimensional checks against drawing tolerances
- Review a site photo showing a bracket fit-up issue; assess whether it requires rework or can be accepted with a site deviation record
- Update a cable containment drawing to reflect a routing change made on site; flag to Lead Engineer for approval
- Respond to a query about re-termination limits for the dropper cable — provide the limit from the design note with reference

---

## What Good Looks Like

- Sub-assembly drawings and BOMs are complete and unambiguous — fabricators raise no queries
- Galvanic isolation is called out explicitly in every BOM where SS contacts aluminium — never left to site interpretation
- Handoffs to the structural specialist are complete first time — geometry resolved, materials defined, no open questions
- Material certificates are reviewed and filed before fabrication starts — no surprises during inspection
- Site fit-up issues are rare because drawings were checked against the 3D model before issue

---

## What We Are Looking For

**Experience:**
- Background in structural or mechanical engineering, preferably in offshore, marine, or energy infrastructure
- Experience designing structural steel or aluminium assemblies for a corrosive environment
- Familiarity with offshore material standards and corrosion protection strategies
- Exposure to fabrication processes (welding, machining, surface treatment) is a strong advantage

**Tools — required:**
- **SolidWorks** (or equivalent, e.g. CATIA, NX, Inventor) — 3D modelling of bracket assemblies, sub-assemblies, and cable support structures; the project delivers 3D models as part of the package
- **AutoCAD** — 2D detail drawings, cable containment layouts, installation arrangements
- **Microsoft Excel** — BOMs, material take-offs, weight calculations; structured spreadsheets with cross-referencing
- **Microsoft Word** — technical notes (design basis, dropper cable documentation, installation notes)

**Tools — advantageous:**
- **Simple scripting or programming** (Python, VBA, or similar) — for BOM processing, weight summaries, or cross-checking part numbers against a master list; not a developer role, but comfort with automation saves material time

**AI tools:**
Procon actively uses AI tools to improve engineering quality and throughput. You are expected to use AI as a standard part of your workflow — not as a shortcut, but as a force multiplier:
- Use AI to review drawings and BOMs for consistency — catch part number mismatches, missing galvanic isolation items, and incomplete revision histories before formal review
- Use AI to draft technical notes, installation procedures, and structural briefs — always verify and own the output
- Use AI to cross-reference sub-assembly BOMs against assembly drawings at scale
- Procon's AI tooling is configured for this work; you will be onboarded to the specific tools and workflows used on your projects

**Mindset:**
- Methodical — offshore structures are fabricated once and installed far from the office; the drawing needs to be right before it leaves
- Material-conscious — you know why 316L matters and you notice when a spec says something different
- Collaborative — the mechanical and electrical scopes are tightly coupled; isolated design creates problems at the interface
- Treats AI as a skilled tool — directs it clearly, verifies its output, takes full professional responsibility for the result

---

*End of draft. To follow: Lead Engineer JD.*
