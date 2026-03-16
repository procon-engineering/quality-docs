# Information Security Policy — Procon Engineering Department

**Document ID:** ISMS-002 | **Version:** 0.1 (DRAFT)
**Standard:** ISO 27001:2022, Clause 5.2
**Owner:** Aegis (Security Manager)
**Approved by:** _Pending Magnus approval_
**Date:** 2026-03-16
**Classification:** Internal

---

## 1. Policy Statement

Procon's Engineering Department is committed to protecting the confidentiality, integrity, and availability of information assets under its control. This includes engineering data, client information, personal data, system configurations, and communications processed through our agent-based engineering management system.

Information security is integral to delivering "Zero Harm, First-Time-Right" engineering — our quality commitment extends to the security of the data and systems that support our work.

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

## 3. Principles

### 3.1 Least Privilege
Every agent, user, and system is granted only the minimum access required for their function. Privilege escalation requires security review.

### 3.2 Defence in Depth
No single control is relied upon. Security is layered across organisational, technical, and procedural controls.

### 3.3 Assume Breach
External content is treated as potentially hostile. High-privilege systems are isolated from untrusted inputs. The external content handling process (Pip → Aegis → verdict) embodies this principle.

### 3.4 Transparency
Security decisions are documented, reasoned, and auditable. Findings are tracked through the NCR register with full traceability.

### 3.5 Proportionality
Controls are proportionate to the risk. We invest security effort where the impact of compromise is highest.

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

### 5.1 External Content Handling
All external content must pass through the approved Pip → Aegis → verdict pipeline before reaching high-privilege agents. See `security-management/isms-external-content-procedure.md` (to be created).

### 5.2 Access Control
Agent permissions follow the trust hierarchy. Changes to agent access, credentials, or scope require Aegis review. See the information asset register for classification and access rules.

### 5.3 Skill and Integration Approval
No external skill, package, or integration is deployed without an Aegis security audit and Magnus approval. Verdicts are documented in the audit trail.

### 5.4 Incident Management
Security incidents and anomalies detected in daily audits are logged, classified, and tracked through the NCR register. Critical findings trigger immediate escalation to Magnus.

### 5.5 Data Protection
Personal data is processed in accordance with GDPR. Credentials and secrets are not stored in plain text in workspace files, chat messages, or memory. Data does not leave the local system without explicit authorisation.

### 5.6 Backup and Recovery
Critical data (workspace, configurations, databases) is backed up daily. Recovery procedures are tested periodically.

### 5.7 Change Management
Changes to agent configurations, permissions, system infrastructure, or security controls are reviewed before implementation and documented.

---

## 6. Compliance

This policy is mandatory for all agents and personnel operating within the ISMS scope. Non-compliance is reported as an NCR and addressed through the corrective action process.

This policy is reviewed annually, or when significant changes to the organisation, systems, or threat landscape occur.

---

## 7. Related Documents

| Document | Reference |
|----------|-----------|
| ISMS Scope | `security-management/isms-scope.md` (ISMS-001) |
| Information Asset Register | `security-management/isms-asset-register.md` (ISMS-003, to be created) |
| Risk Assessment & Treatment Plan | `security-management/isms-risk-assessment.md` (to be created, Phase 2) |
| External Content Handling Procedure | `security-management/isms-external-content-procedure.md` (to be created) |
| Operational Security Policy | `security-management/isms-security-policy.md` (migrated from `SECURITY-POLICY.md`) |
| Inter-Agent Communication Security | `quality-instructions/inter-agent-communication-security.md` |
| Engineering Charter | `quality-instructions/engineering-charter.md` |

---

## 8. Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2026-03-16 | Aegis | Initial draft |

**Next review:** 2027-03-16

---

_This document requires approval from Magnus (Engineering Director)._
