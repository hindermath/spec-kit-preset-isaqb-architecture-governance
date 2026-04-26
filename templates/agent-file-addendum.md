## iSAQB Architecture Governance Agent Guidance

- Treat architecture as an explicit work product when a task affects
  structure, interfaces, quality attributes, runtime behavior,
  deployment, or long-term maintainability.
- Use lightweight iSAQB/CPSA-F and arc42-compatible documentation under
  `docs/architecture/`.
- Prefer concrete quality scenarios over generic quality claims.
- Create ADRs for architecturally significant decisions and record
  alternatives considered.
- Record architecture risks and technical debt with mitigation and review
  trigger.
- Keep this preset separate from secure architecture. If trust
  boundaries, threat modeling, Zero Trust, or security program maturity
  are involved, also apply `architecture-governance`.
- Document every `N/A` decision with rationale.
