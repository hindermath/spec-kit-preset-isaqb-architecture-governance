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
- Add concrete quality scenarios for partial failure, interruption, resume,
  idempotent retry, and state reconstruction when orchestration or remote
  delivery is architecturally significant.
- Model direct and stacked dependency structures explicitly. Re-evaluate
  affected runtime and building-block views when a dependency base changes.
- Record why the selected state and event model can distinguish completed,
  pending, failed, and `NeedsRevalidation` operations after process loss.

## Audit-Ready Spec-Kit Evidence

- When this preset applies, generated or updated Markdown evidence must include the Spec-Kit run, owner/reviewer, evidence path, applicability decision, N/A rationale where relevant, and open follow-up tracking.
- Do not treat an unfilled starter template as evidence. Evidence exists only after the current run has recorded concrete decisions, paths, and rationale.
