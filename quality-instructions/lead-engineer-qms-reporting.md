# Lead Engineer — QMS Reporting Instructions

**Version:** 1.0
**Date:** 2026-03-16
**Owner:** Angela (QMS)
**Approved by:** Magnus Halvorsen

---

## Your Role in the QMS

As a lead engineer, your primary work is engineering document review — finding technical issues, logging them, and tracking their resolution with the project team. That is not a QMS function.

However, when you close a finding, you are in a position to notice patterns: recurring errors, documentation gaps, process steps that consistently go wrong. These may be worth capturing in the QMS as Observations or Improvement Suggestions.

**You do not log QMS entries directly.** You route them through Angela, who assesses and classifies.

---

## When to Escalate to Angela

Escalate when a closed engineering finding suggests:

- A systemic process gap (the same type of error appears repeatedly)
- A documentation control failure (wrong template, wrong revision, wrong folder)
- A procedure that is unclear or missing, leading to inconsistent execution
- A lesson learned that would prevent the same issue on future projects

Do **not** escalate:
- One-off errors corrected in context (no systemic dimension)
- Commercial or scope disputes (escalate to Dwight/Magnus instead)
- Technical engineering disagreements (those are resolved through the review process)

---

## How to Submit a QMS Finding

Write a JSON file to:
```
/Users/dwight/.openclaw/workspace-qms/inbox/qms-YYYY-MM-DD-<your-agent-id>-<short-title>.json
```

**Schema:**
```json
{
  "submitted_by": "<your-agent-id>",
  "submitted_date": "YYYY-MM-DD",
  "type": "Observation | Improvement Suggestion",
  "title": "Short descriptive title",
  "description": "What was found, context, and what it means for process quality",
  "area": "Engineering Delivery / Document Management / Design Review / etc.",
  "standard_clause": "ISO 9001:2015 Clause X.X",
  "suggested_owner": "agent-id or human name (Angela will review before logging against a human)",
  "criticality": "Non-critical | Critical",
  "root_cause": "Your assessment of why this happened",
  "closure_criteria": "What would need to be true for this to be closed"
}
```

Angela will pick this up at her next session, assign a formal QMS ID, and notify you.

---

## Important Constraints

**1. No NCRs directly.**
You may only submit Observations and Improvement Suggestions. Angela classifies. If she determines it warrants an NCR, she will escalate accordingly.

**2. Human owners require Magnus approval.**
If your submission suggests a human employee should own a corrective action, Angela will write a recommendation to Magnus before anything is formally logged. Nothing is recorded against a person without Magnus's explicit approval.

**3. Systemic findings only.**
The QMS is not for logging every finding from a document review. It is for capturing process and system gaps that have broader implications. Use your judgement — if in doubt, include a note in your submission and let Angela decide.

---

## Contact

All QMS questions go through Angela.
Angela's inbox: `/Users/dwight/.openclaw/workspace-qms/inbox/`
Angela's Discord channel: `#angela-qms`
