# What Procon Delivers — The LV Electrical Package (Plain Language)
**Written for:** Non-technical team members (Mona, Toby, Pip, Angela, Tick, Penny, etc.)  
**Author:** Tom (Lead Engineer, Project 10260)  
**Date:** 2026-03-11  
**Reviewed by:** Magnus Halvorsen (Engineering Director)

---

## The Short Version

Procon designs and installs the **electrical systems on the steel foundations of offshore wind turbines** — the part that sticks up out of the sea before the turbine tower is placed on top.

Each foundation has several floors (called platforms). Procon puts lights, sockets, safety equipment, and cable systems on those floors. We also design the system that carries high-voltage electricity from the offshore grid into the turbine.

Our deliverable is a **complete engineering package** — a set of 60–100 documents that describe exactly what is installed, where, how it is wired, and how it works.

---

## The Structure — Picture a Steel Column

Imagine the foundation as a hollow steel column rising out of the sea. Inside and around it are several platforms (floors) stacked at different heights:

```
    ┌──────────────────────┐
    │   WTG Tower begins   │  ← Tower manufacturer takes over here
    │   (not Procon scope) │
    ├──────────────────────┤  ← Foundation flange (where tower bolts on)
    │  TEP — Tower         │  Procon designs, tower mfr installs
    │  Equipment Platform  │  (instruments, cable interfaces)
    ├──────────────────────┤
    │  ATP — Airtight      │  ← Top internal platform
    │  Platform            │  (lights, sockets, safety equipment)
    ├──────────────────────┤
    │  FECB                │  ← Procon's main control cabinet
    │  (control cabinet)   │  (goes into the tower, but Procon designs it)
    ├──────────────────────┤
    │  Intermediate         │  ← HV cable support only — no general equipment
    │  Platform            │  (this is the confusing one — see below)
    ├──────────────────────┤
    │  BTP — Bolting       │  ← Platform at the transition zone
    │  Platform            │  (1 socket outlet, Procon scope)
    ├──────────────────────┤
    │  MAP — Main Access   │  ← Main external platform (bottom)
    │  Platform            │  (lights, sockets, OVP panels, crane)
    ├──────────────────────┤
    │  Subsea / pile       │  ← Below water (ICCP corrosion protection)
    └──────────────────────┘
```

---

## What "LV" and "HV" Mean

**LV = Low Voltage** — the everyday electrical systems: lights, sockets, control panels, safety systems. This is the core of what Procon designs. When we say "LV package," we mean all of this.

**HV = High Voltage** — the main power cable that runs from the offshore electrical grid (called the inter-array cable) up into the turbine. Procon does not design the cable itself, but we design and supply the **steel support structure** that holds this cable as it runs up the outside of the foundation.

**Why is HV support in the LV package?** Because it is physically on our foundation and mechanically our responsibility, even though the cable itself belongs to a different contractor (the IAC — Inter-Array Cable contractor). It is an anomaly in the package name — the electrical engineers own the support drawings because they understand the cable behaviour, even though it is a structural product.

---

## Who Else Is Involved (and Why It Matters)

Procon does not work alone. Several other parties have scope on the same foundation:

| Party | What they do | Interface with Procon |
|---|---|---|
| **WTG Manufacturer (e.g. Vestas)** | Builds the turbine tower and all equipment inside it | Procon cables connect to their panels; they also supply some platform equipment (e.g. BTP lighting) |
| **IAC Contractor** | Installs the high-voltage inter-array cable from the seabed into the turbine | Uses Procon's HV support structure; supplies the cable cleats themselves |
| **Client (e.g. RWE)** | Owns the wind farm; approves all design documents | Reviews and approves Procon's document package before fabrication starts |
| **Foundation Manufacturer (JBO)** | Fabricates the steel monopile foundation | Procon coordinates cable penetrations, platform positions, and earthing connections with them |

A large part of document review is making sure **scope boundaries are correctly documented** — who supplies what, who installs what, and what happens at the handover points.

---

## What the Document Package Actually Contains

Here is what each type of document does, in plain language:

### Design Reports and Studies
These are the "why" documents — they explain the engineering thinking.
- **LV Design Report** — the master document. Describes every system, every platform, all design choices. If you read one document about what Procon installs, this is it.
- **Earthing Study** — explains how the foundation is protected against electric shock and lightning. All metal parts are connected together and to the seabed.
- **Illumination Study** — proves there is enough light on every platform for safe working. Uses computer simulation.
- **Power Studies** — checks that the electrical supply can handle everything running at once, and that safety equipment (fuses, breakers) will trip correctly in a fault.
- **Lightning Rods Assessment** — assesses whether lightning rods are needed. (On NSC A, the conclusion was: they are not warranted.)

### Specifications and Lists
These are the "what" documents — they define every component.
- **LV Component Specification** — specifies each panel and piece of equipment (what IP rating, what voltage, what brand standards).
- **Electrical Tagging Schedule** — the master list of every tagged item (every panel, junction box, and light fitting gets a unique ID called an RDS-PP tag).
- **Equipment List** — one row per piece of equipment, per platform, per turbine. 44 turbines × ~10 items = ~440 rows.
- **Cable Lists** — one row per cable. There can be 300+ cables per foundation. Two lists: one for power cables (LV), one for earthing cables.
- **Load List** — lists every electrical load (everything that draws power) with its wattage. Feeds into the power studies.

### Drawings
These are the "where" documents — they show physical locations and wiring.
- **Single Line Diagram (SLD)** — a simplified schematic of the whole electrical system. Shows which breaker feeds which platform. Not drawn to scale.
- **FECB Schematics** — detailed wiring diagrams for the main control cabinet (FECB). Shows every terminal, every wire.
- **OVP Schematics** — wiring for the surge protection panels (OVP = Overvoltage Protection). Protects equipment against lightning surges.
- **Layout Drawings** — top-down and side-view drawings of each platform showing where each piece of equipment is physically located.
- **Cable Containment Drawings** — show the routes that cable trays follow across the platforms.
- **HV Cable Support Drawings** — show the steel bracket system that holds the high-voltage inter-array cable as it runs up the foundation.

### Per-Turbine Documents
- **WTG Schedule** — a spreadsheet with one tab per turbine (44 tabs). Lists every tagged piece of equipment installed on that specific turbine. Some turbines have special equipment (sonar systems, extra helicopter lights) that others don't.

### SCADA / Control
- **SCADA Signal List** — lists every signal that the FECB control cabinet sends to the turbine's central computer system. Things like "lights on/off," "OVP tripped," "UPS battery low."
- **SCADA Activation Sequence** — step-by-step instructions for first energising the FECB during commissioning.
- **SCADA Operation Mode** — describes the different operating modes and how to switch between them. Used by operations teams.

### Verification
- **HV Cable Support FEA** — a computer simulation (Finite Element Analysis) that proves the steel bracket structure can survive a short circuit in the HV cable (which produces a violent mechanical shock). Subcontracted structural analysis.
- **Dropper Cable Technical Note** — documents the engineering basis for the "dropper" cable — the short section of flexible HV cable that hangs between the fixed cable and the connector box.

### Installation and Operations Documents
- **Installation Manuals** — step-by-step field instructions for installing equipment like the FECB cabinet or OVP panels.
- **O&M Manuals** — instructions for maintenance teams operating the equipment after installation.
- **Cable Gland Instructions** — specifies the exact cable glands (cable entry fittings) for each panel entry, including manufacturer part numbers.
- **Check/Test Sheets** — field sign-off sheets. Installers tick boxes and sign to confirm each step was completed correctly. These become quality records.

### Technical Queries (TQs)
- **TQs** are formal questions and answers exchanged with the turbine manufacturer (Vestas) or other parties when something needs clarification or a design decision needs to be made jointly. They are part of the permanent project record and affect what is specified in the engineering documents.

---

## The Confusing Part — Why Is HV Support in This Package?

The package is called the "LV electrical package" but it includes the HV array cable support structure. Here is why:

1. The HV cable runs up the outside of Procon's foundation — it is physically in our space.
2. The support structure (brackets, cable trays, cleats) is Procon's structural design responsibility.
3. The electrical engineers own the design because they understand how the cable behaves (weight, stiffness, fault current forces).
4. The cable itself and the cleats are the IAC contractor's responsibility — but the steel support they sit on is Procon's.

Think of it like this: **Procon builds the road; the IAC contractor drives on it.** The road (structure) is in Procon's package; the vehicle (cable) belongs to someone else.

---

## Scale of a Typical Delivery

For NSC A (44 turbines):
- ~96 documents in the package
- ~320 power cables, ~320 earthing cables
- Equipment on 4 platforms per turbine: MAP, BTP, ATP, TEP
- 44 WTGs × ~10 tagged items = ~440 tagged equipment items
- The FECB cabinet alone has ~33 monitored SCADA signals

---

## What Document Review Means

When Procon reviews these documents before issuing to the client, the team checks:

- **Is the design technically correct?** (Tom and Alex)
- **Are scope boundaries documented?** (Tom)
- **Do the documents reference each other consistently?** (Tom)
- **Is the formatting, version control, and document metadata correct?** (Clara)
- **Do all documents use the correct project ID?** (Clara)

The review process produces **findings** — issues that must be corrected before the document is formally approved by the client. Findings are recorded in a database, reviewed by the Lead Engineer, and returned to the document authors for correction.

---

*This document is intended to give non-technical team members enough context to understand what is being discussed when the engineering team refers to specific documents, findings, or scope boundaries. It is not a technical reference.*
