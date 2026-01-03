docs end-to-end-request-workflow.md

# End-to-End Request Workflow — rag-copilot

## Overview
Defines the lifecycle of a typical end-user request from submission through resolution or escalation.

---

## Workflow Steps

1. User submits a request to Copilot
2. Copilot identifies intent and context
3. Policy & Scope Gate validates:
   - role
   - scope
   - sensitivity
4. If approved:
   - retrieve SOP guidance
   - generate response with citations
5. If not approved or insufficient:
   - escalate to ITSM
6. Log all steps for audit

---

## Primary Outcomes
- Guided self-service resolution
- Safe refusal with explanation
- Escalated human handling
