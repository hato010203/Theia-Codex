# Theia Development Guidelines

## Core Principles

- Document before implementation.
- Single Responsibility Principle.
- Data-driven whenever possible.
- Resolver computes.
- Manager provides.
- Profile stores.
- Cache only expensive computations.
- Never duplicate logic.
- Prefer extensibility over short-term convenience.

Implementation follows documentation.

Managers provide data.

Resolvers compute state.

Profiles store resolved results.

Prefer event-driven over per-frame logic.

Prefer data-driven over hardcoded branching.

Separate mechanics from presentation.

Every expensive calculation must have explicit invalidation.

Never duplicate logic.
