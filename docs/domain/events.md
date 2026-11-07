# Event catalog

Every event produced or consumed by any PRD is registered here.

## Conventions

- Names are past tense, PascalCase: `DelegationGranted`.
- Envelope fields (implicit on every event): `eventId`, `eventType`, `schemaVersion`, `occurredAt`, `principalId`, `actor` (`person` \| `agent:<id>` \| `policy:<id>`), `correlationId`, `causationId`.
- `actor`, `correlationId` and `causationId` are mandatory: they form the audit trail of agent behaviour.
- Breaking payload changes bump `schemaVersion`; old versions remain listed until no consumer depends on them.

## Catalog

| Event | Producer context | Consumers | Payload (key fields) | Version | Defined in |
| --- | --- | --- | --- | --- | --- |
| — | — | — | — | — | — |
