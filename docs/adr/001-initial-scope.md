# ADR-001: Initial scope and repository naming

## Date

2026-10-20

## Status

Accepted

## Context

The product idea applies to many independent professionals,
but the first real use case is a dental clinic.

## Decision

Start with the dental clinic domain. Keep the data model
multi-tenant (business_id) so other segments can be added later.
Repository name: dental-scheduling.

## Consequences

### Positive

- Focused requirements and a faster MVP.

### Negative

- Some terms (e.g., "dentist") may need renaming if generalized.
