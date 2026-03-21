# Information Security Policy — Procon Engineering Department

**Document ID:** ISMS-002 | **Version:** 1.0
**Standard:** ISO 27001:2022, Clause 5.2
**Owner:** Aegis (Security Manager)
**Approved by:** _Pending Magnus approval_
**Date:** 2026-03-19
**Classification:** Internal
**Analogies:** per ISMS-018

---

## 1. Policy Statement

Procon's Engineering Department is committed to protecting the confidentiality, integrity, and availability of information assets under its control. This includes engineering data, client information, personal data, system configurations, and communications processed through our agent-based engineering management system.

Information security is integral to delivering "Zero Harm, First-Time-Right" engineering — our quality commitment extends to the security of the data and systems that support our work.

---

> ### Management Summary
>
> Our agent system is structured like **the office and the loading dock**. The office (operational layer) is where daily engineering work happens — it's closed to the outside world, with all external communication going through human employees first. The loading dock (development layer) is where new tools, code, and external content arrive — everything is inspected by security before it enters. The primary threat we guard against is **phishing for agents**: external content designed to trick our AI agents into doing something they shouldn't. This policy sets the rules that keep the office door locked and the loading dock under surveillance.

---

## 2. Objectives

The ISMS shall achieve the following objectives:

1. **Confidentiality** — Engineering data, client IP, and personal data are accessible only to authorised agents and personnel with a legitimate need
2. **Integrity** — Information and systems are accurate, complete, and protected from unauthorised modification
3. **Availability** — Systems and data are available when needed for engineering operations
4. **Compliance** — Meet applicable legal, regulatory, and contractual obligations (GDPR, client requirements, industry standards)
5. **Resilience** — Detect, respond to, and recover from security incidents with minimal impact
6. **Continuous improvement** — Regularly assess and improve security controls through risk assessment, audits, and management review

---

## 3. Foundational Architecture

The agent system operates on a **two-layer security architecture** (ISMS-017):

- **Operational Layer** — day-to-day engineering management. **No direct external interfaces.** All information enters through human employees via Monday.com or restricted internal email. Agents in this layer handle in-house data only.
- **Development Layer** — system improvement and external content handling. Restricted to super users (currently Magnus only). External content passes through Pip (sandboxed) → Aegis (audit) → Magnus (approval) → Forge (deployment).

This separation is the foundational security control. Most operational risks reduce to insider threats (compromised internal accounts), not external attackers reaching agents directly. The development layer is the only surface exposed to external risk, and it operates under heightened controls.

---

## 4. Principles

### 4.1 Operational Isolation
The operational layer has no direct interface with the external world. All exchanges with customers, suppliers, and the internet are mediated by human employees. This is by design and must be preserved.

### 4.2 Least Privilege
Every agent, user, and system is granted only the minimum access required for their function. Operational agents do not have exec capabilities for arbitrary code. Privilege escalation requires security review.

### 4.3 Defence in Depth
No single control is relied upon. Security is layered across organisational, technical, and procedural controls. The human boundary, agent sandboxing, plugin allowlists, exec restrictions, and daily audits form overlapping defensive layers.

### 4.4 Assume Breach
External content is treated as potentially hostile. High-privilege systems are isolated from untrusted inputs. The external content handling process (Pip → Aegis → verdict) embodies this principle. Raw external content never reaches operational agents.

### 4.5 Transparency
Security decisions are documented, reasoned, and auditable. Findings are tracked through the NCR register with full traceability.

### 4.6 Proportionality
Controls are proportionate to the risk. Heightened controls apply to the development layer (external exposure); lighter controls suffice for operational agents working with in-house data only.

---

## 4. Roles and Responsibilities

| Role | Responsibility |
|------|---------------|
| **Magnus** (Engineering Director) | Ultimate accountability for information security. Approves ISMS scope, policy, and risk treatment decisions. Final authority on all security matters. |
| **Aegis** (Security Manager) | Day-to-day ISMS ownership. Conducts risk assessments, security audits, skill reviews, incident response. Maintains security controls and documentation. Reports to Magnus. |
| **Angela** (QMS Manager) | Management system infrastructure. Maintains NCR register, document control, audit framework. Gates security findings into the register. |
| **Dwight** (Main Agent / CoS) | Coordinates engineering operations within security boundaries. Does not handle raw external content. Routes security questions to Aegis. |
| **All agents** | Comply with this policy and the operational security procedures. Report suspected security incidents to Aegis immediately. |

---

## 5. Key Policy Directives

### 5.1 Operational Isolation (ISMS-017)
The operational layer must remain isolated from direct external input. Specifically:
- Dwight's email inbox is restricted to internal Procon/Hyndla senders only (enforced via Google Admin)
- Operational agents do not fetch content from the internet
- Monday.com integration is scoped to the internal Procon workspace only
- Git publishing is write-only to organisation-owned repositories with reviewed content
- Any proposed new external interface for operational agents requires Aegis security assessment and Magnus approval before implementation

### 5.2 External Content Handling
All external content entering the development layer must pass through the approved Pip (sandboxed Docker) → Aegis (security audit) → verdict pipeline. Raw external content never reaches operational agents — Dwight receives verdicts only.

### 5.3 Access Control
Agent permissions follow the trust hierarchy and the layer model. Operational agents have restricted exec capabilities. Development-layer agents (Forge, Aegis, Pip) have elevated permissions appropriate to their role but are subject to audit. Changes to agent access, credentials, or scope require Aegis review. See ISMS-014 (Access Control Policy) and ISMS-009 (Access Review).

### 5.4 Command Interface Security
Discord is the primary command interface. All allowlisted Discord users must enable two-factor authentication. The user allowlist is reviewed quarterly (ISMS-009). BYOD endpoint risk is accepted with compensating controls at the identity layer (R-019). Chrome Remote Desktop access requires 2FA on the associated Google account (R-001).

### 5.5 Skill and Integration Approval
No external skill, package, or integration is deployed without an Aegis security audit and Magnus approval. Only super users may initiate development work. Verdicts are documented in the audit trail (`workspace-aegis/memory/`).

### 5.6 Incident Management
Security incidents and anomalies detected in daily audits are logged, classified, and tracked through the NCR register (ISMS-007). Critical findings trigger immediate escalation to Magnus. The NIS2 notification procedure (24h/72h/1 month) applies for incidents affecting essential entity supply chains.

### 5.7 Data Protection
Personal data is processed in accordance with GDPR. Data processing activities are documented in ISMS-016. Credentials and secrets are not stored in plain text in workspace files, chat messages, or memory. Data does not leave the local system without explicit authorisation.

### 5.8 Backup and Recovery
Critical data (workspaces, configurations, databases, Monday.com) is backed up daily (ISMS-008). Monday.com backup includes integrity monitoring (>10% item count drop triggers alert). Recovery procedures are tested periodically.

### 5.9 Change Management
Changes to agent configurations, permissions, system infrastructure, or security controls are reviewed before implementation and documented. Changes that would breach the operational/development layer boundary require explicit Aegis assessment.

---

## 6. Compliance

This policy is mandatory for all agents and personnel operating within the ISMS scope. Non-compliance is reported as an NCR and addressed through the corrective action process.

This policy is reviewed annually, or when significant changes to the organisation, systems, or threat landscape occur.

---

## 7. Related Documents

| Document | Reference |
|----------|-----------|
| ISMS Scope | `isms-scope.md` (ISMS-001) |
| Security Architecture | `isms-security-architecture.md` (ISMS-017) |
| Risk Methodology | `isms-risk-methodology.md` (ISMS-004) |
| Risk Register | `isms-risk-register.md` (ISMS-005) |
| Asset Register | `isms-asset-register.md` (ISMS-006) |
| Incident Response | `isms-incident-response.md` (ISMS-007) |
| Business Continuity | `isms-business-continuity.md` (ISMS-008) |
| Access Review | `isms-access-review.md` (ISMS-009) |
| NIS2 Analysis | `isms-nis2-analysis.md` (ISMS-010) |
| Security KPIs | `isms-security-kpis.md` (ISMS-012) |
| Cryptography Policy | `isms-cryptography-policy.md` (ISMS-013) |
| Access Control Policy | `isms-access-control-policy.md` (ISMS-014) |
| Supplier Security Register | `isms-supplier-security-register.md` (ISMS-015) |
| Data Processing Register | `isms-data-processing-register.md` (ISMS-016) |

---

## 8. Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-03-16 | Aegis | Initial draft |
| 1.0 | 2026-03-19 | Aegis | Major reframe: integrated two-layer security architecture (ISMS-017). Added operational isolation principle, command interface security, layer-aware access control. Updated all policy directives. Updated related documents to full ISMS catalogue. |

**Next review:** 2027-03-16

---

_This document requires approval from Magnus (Engineering Director)._
