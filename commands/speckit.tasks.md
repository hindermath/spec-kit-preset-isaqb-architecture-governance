Before continuing, apply the iSAQB Architecture Governance preset:

- convert architecture goals, quality scenarios, views, ADRs, risks, and
  technical debt into explicit tasks
- include concrete evidence-production tasks under `docs/architecture/`
- add architecture-review tasks for significant structure, interface,
  runtime, or deployment changes
- if security-relevant architecture is affected, include the corresponding
  secure-architecture tasks from `architecture-governance`

{CORE_TEMPLATE}

Audit-ready evidence requirement:

- Ensure this tasks wrapper requires concrete Markdown evidence/checklist updates for every applicable checkpoint.
- If a checkpoint does not apply in the current Spec-Kit run, require `N/A` with a short rationale instead of omitting it.
- If a checkpoint is undecided, require `Open` with owner, follow-up, and re-evaluation trigger.
