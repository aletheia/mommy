# mommy

An experimental agentic app to handle everyday life and passions, interacting with agents and artifacts.

This repository currently hosts the product requirements and architecture decisions for it: a suite of agentic lifestyle management tools that act on behalf of a person across calendar, communications, household, finance, health and errands, under explicit delegation and guardrails.

## Layout

| Path | Content |
| --- | --- |
| [`docs/prd/`](docs/prd/README.md) | Product Requirements Documents, one per capability |
| [`docs/domain/`](docs/domain/README.md) | Shared domain model: ubiquitous language, bounded contexts, event catalog |
| [`docs/adr/`](docs/adr/README.md) | Architecture Decision Records |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Authoring workflow, numbering, status lifecycle |

## Principles

1. **Domain first.** Every PRD starts from entities, aggregates and the domain events they emit. UI and agent behaviour are derived from the model, not the other way around.
2. **Event-driven.** Capabilities integrate through published domain events, never through shared state. Each PRD declares the events it produces and consumes; the shared catalog lives in [`docs/domain/events.md`](docs/domain/events.md).
3. **Explicit delegation.** Any action an agent takes on a person's behalf maps to a declared autonomy level and is auditable.
4. **Measurable.** Every PRD carries success metrics and an evaluation plan for agent behaviour.

## Quick start

1. Copy [`docs/prd/_template.md`](docs/prd/_template.md) to `docs/prd/NNNN-short-title.md` using the next free number.
2. Register any new terms in [`docs/domain/glossary.md`](docs/domain/glossary.md) and events in [`docs/domain/events.md`](docs/domain/events.md).
3. Open a pull request. Lint runs in CI (`npm run lint` locally).
