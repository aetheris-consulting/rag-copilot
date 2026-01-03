docs/architecture.md

# Architecture Overview — rag-copilot (v0.1)

## Objective
Define a governed Microsoft Copilot Studio architecture for a large, regulated enterprise (ECIS-style) that delivers end-user guidance from authoritative SOP and policy content while preserving compliance, auditability, and human oversight.

This architecture prioritizes **control, continuity, and safety** over autonomy.

---

## Architectural Principles
- **Governed by design:** policy and scope enforcement precede generation
- **Grounded responses:** answers derive only from approved SOP sources
- **Separation of concerns:** end-user guidance vs IT operations
- **Fail safe:** refusal and escalation are first-class outcomes
- **Auditable:** all decisions and sources are traceable

---

## Component Overview

### 1. Copilot Studio Agent
- User interaction layer
- Intent detection and conversation flow
- No direct system authority
- Delegates retrieval and actions to governed services

### 2. Policy & Scope Gate (Control Plane)
Deterministic enforcement layer that evaluates:
- User identity and role
- Request scope
- Data classification constraints
- Allowed actions and sources

All requests pass through this layer before retrieval or action.

### 3. Retrieval Orchestrator (RAG)
Responsible for:
- Query normalization and rewrite
- Source allow-listing
- Retrieval from approved SharePoint libraries
- Ranking and deduplication
- Context packet assembly for Copilot

This layer **does not train models** and **does not expand knowledge**.

### 4. SharePoint SOP / Policy Libraries
- Organization-owned
- Durable across contracts
- Permissioned and versioned
- Authoritative source of guidance

### 5. ITSM / Ticketing System
- Human-operated
- Used only via escalation
- No direct knowledge exposure to Copilot

### 6. Audit & Telemetry
Captures:
- User requests
- Policy decisions
- Retrieved sources
- Generated responses
- Escalation events

---

## Control Plane vs Generation Plane

### Control Plane (Deterministic)
- Identity and role checks
- Scope validation
- Source allow-listing
- Escalation rules
- Logging and audit hooks

### Generation Plane (Probabilistic, Constrained)
- Natural language synthesis
- Restricted to retrieved context
- Required citations
- Refusal when context is insufficient

---

## Out-of-Scope by Design
- Autonomous execution
- ITSM KB retrieval
- Model training or fine-tuning
- Cross-tenant data access
