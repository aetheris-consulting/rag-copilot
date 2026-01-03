docs/retrieval-workflow-rag.md

# Retrieval Workflow (RAG) — Internal

## Purpose
Define how authoritative content is selected and provided to Copilot while preventing over-disclosure.

---

## Retrieval Steps

1. Normalize user query
2. Apply role and scope filters
3. Select allowed SharePoint libraries
4. Retrieve relevant SOP excerpts
5. Rank and deduplicate results
6. Package context for Copilot
7. Enforce citation requirement

---

## Guardrails
- No retrieval outside allow-listed sources
- No answer without authoritative content
- No cross-role leakage
- Refusal on low confidence
