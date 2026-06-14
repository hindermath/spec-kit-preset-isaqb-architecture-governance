# iSAQB Architecture Governance Preset

Version: `0.2.0`
Requires: `spec-kit >= 0.8.0` (uses the `wrap` and `append` composition
strategies introduced in 0.8.x).

Purpose:

- add general software-architecture governance based on iSAQB/CPSA-F and
  arc42 to Spec Kit workflows
- make architecture goals, quality requirements, views, decisions, risks,
  and technical debt explicit
- keep general architecture work separate from secure-architecture
  governance

Relationship to `architecture-governance`:

- `isaqb-architecture-governance` covers general software architecture:
  architecture goals, context, building blocks, runtime view, deployment
  view, quality scenarios, architecture decisions, risks, and technical
  debt.
- `architecture-governance` covers secure architecture: trust boundaries,
  threat modeling, STRIDE/CAPEC, Zero Trust, S-ADRs, and OWASP SAMM.
- If security-relevant architecture is in scope, use both presets
  together.

Standards and concepts in scope:

- `iSAQB CPSA-F` architecture work products and method discipline
- `arc42` structure beyond Section 8
- architecture goals and constraints
- system context and external interfaces
- building-block view
- runtime scenarios
- deployment view
- quality attribute scenarios
- Architecture Decision Records (ADRs)
- architecture risks and technical debt

Preset strategy:

- append general architecture-governance sections to
  `constitution-template`, `spec-template`, `plan-template`, and
  `tasks-template`
- provide a standalone agent-guidance addendum template for projects that
  maintain agent instruction files
- wrap `speckit.specify`, `speckit.plan`, and `speckit.tasks` with a
  shared iSAQB/arc42 architecture workflow
- provide starter templates for architecture vision, context view,
  building-block view, runtime view, deployment view, quality scenarios,
  ADRs, and architecture risks

Evidence templates included:

- Spec-Kit run evidence fields are embedded in the evidence templates to support audit-ready applicability, N/A rationale, reviewer, and follow-up records.
- `architecture-vision-template`
- `context-view-template`
- `building-block-view-template`
- `runtime-view-template`
- `deployment-view-template`
- `quality-scenarios-template`
- `architecture-decision-template`
- `architecture-risks-template`

Default evidence location: `docs/architecture/`. ADRs default to
`docs/architecture/adr/` as one file per decision.

When to use:

- projects where architecture decisions affect maintainability,
  extensibility, operations, integration, or quality attributes
- teams that want lightweight arc42/iSAQB work products without adopting
  a large documentation process
- systems whose design should be understandable beyond the immediate
  implementation tasks

When not to use:

- tiny scripts or throwaway prototypes with no meaningful architecture
  surface
- projects that only need secure-architecture prompts; use
  `architecture-governance` instead or in combination

Release notes:

- `v0.2.0` adds audit-ready Spec-Kit run evidence fields so generated Markdown documents and checklists can record applicability, N/A rationale, reviewer, evidence path, residual risk, and follow-up per standards-relevant Spec-Kit run.

Recommended standalone install priority:

- `15`
