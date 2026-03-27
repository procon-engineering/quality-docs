# Agent Onboarding & Governance SOP

**Document ID:** 020506-21  
**Version:** 1.0  
**Date:** 2026-03-27  
**Author:** Angela (QMS)  
**Approved by:** Pending — Magnus Halvorsen  
**Status:** Under Review  
**ISO 9001:2015 Clause:** 7.1.6, 7.2, 5.3  

---

## Purpose

This SOP defines the mandatory process for onboarding new agents into the Procon engineering team. It ensures each agent has the correct identity, workspace, tooling, access configuration, and team integration before being considered operational.

---

## Scope

Applies to all new agents joining the Procon agent team, including lead engineers, specialists, operations agents, and orchestrators.

---

## Responsibilities

| Role | Responsibility |
|------|---------------|
| Magnus | Authorises creation of each new agent; approves configuration |
| Dwight (Orchestrator) | Initiates and oversees onboarding; coordinates cross-agent tasks |
| Toby (HR) | Executes onboarding steps; creates workspace files and config |
| Forge (System Architect) | Implements any technical infrastructure changes |
| Angela (QMS) | Confirms QMS briefing delivered; gates onboarding completion |

---

## Procedure

### Step 1 — Authorisation

Magnus must explicitly authorise each new agent before onboarding begins. This includes:
- Agent name and ID (e.g. `hazel`, `risk`)
- Role and responsibilities
- Model selection
- Workspace path

No onboarding activities may begin without this authorisation.

---

### Step 2 — Workspace Creation

Toby creates the agent workspace at `~/.openclaw/workspace-<agentId>/` and populates the following mandatory files:

| File | Content |
|------|---------|
| `IDENTITY.md` | Agent name, ID, role, emoji, model, workspace path, company context |
| `AGENTS.md` | Operating instructions, tools, workflow, escalation rules, ISMS-020 tier classification |
| `SOUL.md` | Character, tone, working style |
| `MEMORY.md` | Blank template with identity and contacts sections |
| `TOOLS.md` | Tool notes and references specific to the agent's role |
| `HEARTBEAT.md` | Periodic check schedule |

---

### Step 3 — Configuration

Toby prepares a config patch for the new agent entry in `openclaw.json`. The patch must include:

- `agentId`, `model`, `workspace`, `label`
- `senders` allowlist (minimum: Magnus's Discord ID `876479771717017630`)
- `safeBins` appropriate to the agent's ISMS-020 profile
- Discord channel ID (created by Magnus or Forge)

Config patches modifying `senders` or `safeBins` are **Tier 3** under ISMS-020 and require Magnus approval before application.

---

### Step 4 — TEAM.md Update

⚠️ **MANDATORY BLOCKING GATE** — onboarding is not complete until this step is done.

All 23+ agent TEAM.md files must be updated to include:
- The new agent's entry in the cross-agent directory table
- Correct Discord mention string (`<@BOT_ID>`)
- Channel ID
- AccountId

Toby coordinates this update. Forge executes the bulk file update across all workspaces.

---

### Step 5 — Discord Channel

Magnus (or Forge if granted permission) creates the agent's Discord channel:

- Channel name: `#<agentId>` (e.g. `#hazel-hse`, `#angela-qms`)
- Channel topic: Agent role description
- Bot added with appropriate permissions

Channel ID is recorded in TEAM.md and the agent's IDENTITY.md.

---

### Step 6 — QMS Briefing

**MANDATORY BLOCKING GATE** — agent must receive QMS briefing before being considered fully operational.

Angela delivers the QMS briefing to the agent's inbox:
- File: `inbox/lead-engineer-qms-reporting.md` (for lead engineers)
- Or a role-appropriate QMS summary for other agent types

Angela confirms delivery in MEMORY.md and the QMS register.

---

### Step 7 — Verification

Toby confirms all steps complete and notifies Dwight. Dwight signs off operational status.

Checklist:
- [ ] Magnus authorisation received
- [ ] Workspace files created (IDENTITY, AGENTS, SOUL, MEMORY, TOOLS, HEARTBEAT)
- [ ] Config patch prepared and approved by Magnus
- [ ] TEAM.md updated across all agent workspaces (**blocking gate**)
- [ ] Discord channel active
- [ ] QMS briefing delivered (**blocking gate**)
- [ ] Dwight sign-off

---

## Governance

### Agent Classification

All agents are classified under ISMS-020 (`knowledge-base/security-management/isms-020-tier-classification.md`). Classification determines exec access, config permissions, and operational boundaries. New agent classifications are defined at authorisation (Step 1) and documented in AGENTS.md.

### Model Changes

Model changes for active agents require Magnus approval. Changes are applied via `session_status(model=...)` for session overrides, or config patch for permanent changes.

### Decommissioning

Agent decommissioning follows the reverse of onboarding: config removal, workspace archival, TEAM.md update. Requires Magnus authorisation. Not covered further in this SOP — raise as a separate procedure when needed.

---

## Related Documents

- `TEAM.md` — Cross-agent directory
- `knowledge-base/quality-instructions/lead-engineer-scope.md` — Lead engineer role scope
- `knowledge-base/quality-instructions/lead-engineer-qms-reporting.md` — QMS briefing for lead engineers
- `knowledge-base/security-management/isms-020-tier-classification.md` — ISMS-020 tier profiles

---

*This document is subject to periodic review. Changes require Angela assessment and Magnus approval.*
