docs/governance-and-compliance.md

# Governance & Compliance Model — rag-copilot (v0.1)

## Purpose
Ensure Copilot usage aligns with federal security, privacy, records, and responsible AI expectations through enforceable design controls.

---

## Data Classification Model (Illustrative)

| Classification | Description | Copilot Handling |
|---------------|------------|------------------|
| Public | Approved public guidance | Allowed |
| Internal | SOPs and internal procedures | Allowed with role checks |
| Restricted | Sensitive internal guidance | Limited retrieval |
| PII | Personally identifiable data | Avoided / Redacted |

Copilot **never** introduces new PII.

---

## Access Control
- Role-based retrieval (RBAC)
- Site and library allow-listing
- Least-privilege enforcement
- No wildcard access to SharePoint

---

## Records & Retention Awareness
- Responses reference source documents, not cached memory
- Logs support audit reconstruction
- Content lifecycle managed at the document level

---

## Responsible AI Controls
- Grounded responses only
- Citation enforcement
- Refusal for ambiguous or high-risk requests
- No automated decision authority

---

## Audit Events (Minimum)
- Request received
- Policy gate decision
- Sources retrieved
- Response generated
- Escalation created

Audit logs are immutable and reviewable.
