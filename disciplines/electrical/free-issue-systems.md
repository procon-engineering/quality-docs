# Free-Issue Systems — Design Boundary

**Confirmed by:** Magnus Halvorsen, 2026-03-14
**Source brief:** Bart (Lead Engineer, NSC B, project 10283)

## Key Principle

Free-issue systems are NOT connected to or controlled by the Procon/Hyndla FECB cabinet. This is correct by design.

Procon responsibility is **integration only** — earthing connections and cable routing. Not design, not control.

## Free-Issue Systems

| System | Tag Series | Responsible Party |
|--------|-----------|----------------|
| ICCP | =UMD82 | JBO / ICCP specialist |
| Nav aids (marine lanterns, ID marking, brightness/visibility sensors) | =XSD80 | Sabik Offshore |
| Sonar | =XSD70 | Sonar specialist |
| SHM DAU Cabinet | =JYL01 | SHM specialist |

## Review Rules — What Is and Is Not a Finding

| Observation | Finding? |
|------------|----------|
| Free-issue system absent from SCADA IO list | ❌ No — correct by design |
| Free-issue system absent from load list / equipment list | ❌ No — outside Procon scope |
| Free-issue system present in cable lists / earthing lists / GAs | ✅ Expected — integration scope |
| FECB power or IO cable running to a free-issue system | ⚠️ Yes — would be a finding |
| Free-issue system implying Procon design responsibility | ⚠️ Yes — scope creep, raise it |

## Earthing
Free-issue systems receive earthing connections only (XE-series conductors). No FECB power or IO cables run to these systems.

## Notes
- First documented from NSC B (project 10283); likely applicable cross-project
- See also: `suppliers-navigation-aviation.md` for Sabik commercial context
