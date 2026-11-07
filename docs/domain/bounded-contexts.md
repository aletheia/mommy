# Bounded contexts

Each context owns its aggregates and publishes events; no context reads another's storage. Add a context only when a PRD requires it.

## Context map

```mermaid
flowchart LR
    DEL[Delegation & Identity]
    DEL -- DelegationGranted / DelegationRevoked --> OTHERS[Capability contexts]
```

## Contexts

| Context | Responsibility | Aggregates | Owner | PRDs |
| --- | --- | --- | --- | --- |
| Delegation & Identity | Principals, Agents, Delegations, Guardrails, audit trail | Principal, Delegation | | |
