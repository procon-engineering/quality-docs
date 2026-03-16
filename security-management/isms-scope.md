# ISMS Scope — Procon Engineering Department

**Document ID:** ISMS-001 | **Version:** 0.1 (DRAFT)
**Standard:** ISO 27001:2022, Clause 4.3
**Owner:** Aegis (Security Manager)
**Approved by:** _Pending Magnus approval_
**Date:** 2026-03-16
**Classification:** Internal

---

## 1. Purpose

This document defines the scope of Procon's Information Security Management System (ISMS). It establishes what information assets, processes, systems, and locations are covered by the ISMS, and what is explicitly excluded.

The ISMS is built on top of Procon's existing ISO 9001:2015 Quality Management System and shares its management infrastructure (NCR register, corrective action process, document control, internal audit framework).

---

## 2. Context of the Organisation (Clause 4.1)

### 2.1 Internal Context

**Procon** is an EPC provider specialising in electrical installations for offshore wind foundations and substations. The Engineering Department operates two streams:

- **Stream A** — Design & Development (ISO 8.3): Original LV and mechanical design packages for offshore wind
- **Stream B** — Technical Support (ISO 8.5): Review, procurement, and verification of external designs

Engineering work is managed through a multi-agent AI system (OpenClaw) that handles project coordination, document control, quality management, communications, and engineering support. This system processes sensitive engineering data, client information, and internal communications.

### 2.2 External Context

- **Industry:** Offshore wind energy — subject to IEC 60204-1, IEC 61892, and client-specific security requirements
- **Clients:** Major energy companies (e.g. RWE) with their own information security expectations
- **Regulatory:** GDPR (EU), Danish data protection law (personal data of employees and contacts)
- **Supply chain:** Subcontractors, vendors, and consultants with potential access to engineering data

### 2.3 Key Stakeholders (Clause 4.2)

| Stakeholder | Information Security Expectations |
|-------------|-----------------------------------|
| Magnus (Engineering Director) | Confidentiality of engineering data, system integrity, agent safety |
| Procon Management | Compliance with client security requirements, data protection |
| Clients (RWE et al.) | Protection of project data, design IP, contractual confidentiality |
| Employees / Engineers | Protection of personal data, safe communication channels |
| Subcontractors | Secure data exchange, access limited to need-to-know |
| Certification bodies | Evidence of ISMS conformity if pursuing certification |

---

## 3. Scope Statement

### 3.1 In Scope

The ISMS covers the information security of **Procon's Engineering Department operations**, including:

#### 3.1.1 Information Assets
- Engineering design documents (calculations, drawings, specifications)
- Project management data (schedules, budgets, risk registers)
- Client communications and contractual information
- Internal communications (agent-to-agent, agent-to-human)
- Quality management records (NCRs, audit reports, corrective actions)
- Personal data of employees, contractors, and contacts
- API credentials, authentication tokens, and system access keys
- Software configurations and agent system prompts

#### 3.1.2 Systems and Technology
- **OpenClaw agent system** — all agents, plugins, skills, and configurations running on the dedicated Mac mini (`Dwights-Mac-mini.local`)
- **Google Workspace** — Gmail, Calendar, Drive, Docs (under `@hyndla.com`, pending migration)
- **Monday.com** — project tracking and risk management
- **Local infrastructure** — Mac mini hardware, macOS, network connectivity, Docker containers
- **Communication channels** — Discord (agent coordination), email (external communications)
- **Data stores** — SQLite databases, workspace files, LCM context database, contact databases

#### 3.1.3 Processes
- External content handling and review (Pip → Aegis flow)
- Skill and integration auditing
- Agent access control and privilege management
- Credential and secret management
- Backup and recovery procedures
- Incident detection and response (daily security audits)
- Change management for agent configurations and permissions

#### 3.1.4 Physical Location
- Mac mini hosting environment (Magnus's premises, LAN-connected)

### 3.2 Out of Scope

The following are explicitly excluded from this ISMS scope:

- **Procon corporate IT** — servers, network infrastructure, and systems managed by Procon's IT department (outside Engineering Department control)
- **Client-side systems** — client infrastructure and their information security (covered by their own ISMS)
- **Subcontractor internal systems** — covered by subcontractor agreements and their own controls
- **Physical office security** — building access, physical server rooms (Procon corporate responsibility)
- **Non-engineering departments** — HR, finance, sales systems not managed by the Engineering Department
- **Personal devices** — unless used to access Engineering Department systems (then access controls apply)

### 3.3 Scope Boundaries

| Boundary | Inside ISMS | Outside ISMS |
|----------|-------------|--------------|
| Mac mini | All services, agents, data | Hardware procurement |
| Google Workspace | Engineering team usage, data in Drive/Gmail | Google's infrastructure security |
| Monday.com | Data entered by Engineering, API integrations | Monday.com's platform security |
| Email | Content and routing of engineering emails | Email provider infrastructure |
| Network | LAN exposure, port management, tunnels | ISP infrastructure |
| Discord | Agent channels, coordination messages | Discord's platform security |

---

## 4. ISMS Integration with QMS

This ISMS is integrated with Procon's existing ISO 9001:2015 QMS as follows:

| Function | ISMS (Aegis) | QMS (Angela) | Shared |
|----------|-------------|-------------|--------|
| Policy & scope | ✅ | | |
| Risk assessment (security) | ✅ | | Risk methodology (future) |
| Annex A controls | ✅ | | |
| Document control | | ✅ | |
| NCR register & corrective actions | | ✅ | Security findings via inbox |
| Internal audit — security | ✅ | | Audit framework |
| Internal audit — quality | | ✅ | |
| Management review | | | ✅ Joint |

ISMS documents are stored in `knowledge-base/security-management/` with naming convention `isms-*.md`.

Security findings are submitted to Angela's QMS inbox and gated by Angela before entering the NCR register. The `affected_assets` field links findings to the information asset register.

---

## 5. Applicable Standard

This ISMS is designed to conform to **ISO/IEC 27001:2022**, including the restructured Annex A (93 controls across 4 themes: Organisational, People, Physical, Technological).

---

## 6. Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-03-16 | Aegis | Initial draft |

**Review cycle:** Annually, or when significant changes occur to scope, systems, or organisation.
**Next review:** 2027-03-16

---

_This document requires approval from Magnus (Engineering Director) before Phase 2 of the ISMS implementation proceeds._
