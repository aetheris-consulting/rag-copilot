copilot-studio/conversation-flows.md (Workflows at the agent level)

# Copilot Studio Conversation Flows (Design)

## Flow A — SOP Guidance (Primary)
1. Identify intent (e.g., "How do I request access?")
2. Ask minimum clarifying questions (role/site/system)
3. Retrieve SOP excerpt(s) from allowed SharePoint libraries
4. Provide step-by-step guidance with citations
5. Offer escalation option if blocked

## Flow B — Access / Privileged Action (Escalate)
1. Detect privileged request (unlock, permission change, admin action)
2. Confirm user identity context (no sensitive data collection)
3. Create ITSM ticket with minimal necessary details
4. Return ticket number + expected timeline + what user should do next

## Flow C — Conflicting SOPs / Ambiguity
1. Detect conflict (multiple docs, differing effective dates)
2. Prefer:
   - newest effective date
   - authoritative owner (policy office > team wiki)
3. If still ambiguous: escalate to human (ticket) and show what was found
