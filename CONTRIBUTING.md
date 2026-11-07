# Contributing

## Document types

| Type | Location | Naming | Purpose |
| --- | --- | --- | --- |
| PRD | `docs/prd/` | `NNNN-kebab-title.md` | What a capability must do and why |
| ADR | `docs/adr/` | `NNNN-kebab-title.md` | A single architecture decision and its trade-offs |
| Domain | `docs/domain/` | fixed files | Cross-PRD language, contexts and events |

Numbers are zero-padded, monotonic per type, and never reused. `0000` is reserved for templates and index material.

## PRD status lifecycle

```text
Draft ──► In Review ──► Approved ──► Implemented
  │            │             │
  └────────────┴─────────────┴──► Withdrawn | Superseded by NNNN
```

- **Draft**: open for structural change; may be merged to `main` to enable collaboration.
- **In Review**: scope frozen; only clarifications. Reviewers are listed in the header.
- **Approved**: contract for implementation. Changes require a new revision entry in the changelog section.
- **Implemented**: shipped; the PRD becomes reference documentation.
- **Superseded / Withdrawn**: kept for history, never deleted.

Status is tracked in the PRD header and mirrored in the index tables of [`docs/prd/README.md`](docs/prd/README.md) and [`docs/adr/README.md`](docs/adr/README.md).

## Rules

1. One capability per PRD. If the domain model section spans more than one bounded context, split it.
2. Every new domain term goes into [`docs/domain/glossary.md`](docs/domain/glossary.md) in the same PR.
3. Every produced or consumed event goes into [`docs/domain/events.md`](docs/domain/events.md) in the same PR. Event names are past tense (`TaskDelegated`, not `DelegateTask`).
4. Decisions with long-lived architectural impact are extracted into an ADR and linked from the PRD rather than argued inline.
5. Diagrams are Mermaid, inline in Markdown, so they diff and review like text.

## Workflow

1. Branch from `main`.
2. Author or update documents.
3. Run `npm install` once, then `npm run lint`.
4. Open a pull request using the template; CI runs the same lint.
