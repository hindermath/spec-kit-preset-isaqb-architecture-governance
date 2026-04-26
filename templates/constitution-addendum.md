## iSAQB Architecture Governance

### Mandate

Software architecture MUST be treated as an explicit design artefact when
changes affect structure, interfaces, quality attributes, runtime
behavior, deployment, or long-term maintainability. Implementation work
without visible architecture reasoning creates hidden coupling and
unreviewed technical debt.

### General Architecture Principles

- Architecture work SHOULD follow iSAQB/CPSA-F method discipline and use
  lightweight arc42-compatible documentation where useful.
- Architecturally significant decisions MUST be documented as ADRs.
- Quality attributes MUST be expressed as concrete scenarios, not only as
  generic terms such as "fast", "maintainable", or "scalable".
- System context, building blocks, runtime behavior, and deployment
  constraints MUST be documented when they materially affect the design.
- Architecture risks and technical debt MUST be recorded with owner,
  impact, mitigation, and review trigger.
- Architecture documentation MUST stay proportional: enough to support
  review, maintenance, onboarding, and later change decisions.

### Scope Boundary

This preset covers general software architecture. Security-specific
architecture concerns such as trust boundaries, threat modeling,
STRIDE/CAPEC, Zero Trust, S-ADRs, and OWASP SAMM belong to the
`architecture-governance` secure-architecture preset. If security is in
scope, both presets SHOULD be used together.

### Evidence

- Default architecture evidence location: `docs/architecture/`.
- Default ADR location: `docs/architecture/adr/`.
- Record `N/A` decisions with rationale. Silent omission is not allowed.
