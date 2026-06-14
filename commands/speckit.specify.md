Before continuing, apply the iSAQB Architecture Governance preset:

- identify whether the feature affects architecture goals, context,
  quality attributes, interfaces, runtime behavior, deployment, or
  technical debt
- record the architecture evidence expected under `docs/architecture/`
- identify whether general ADRs or architecture-risk records are needed
- if security-relevant architecture is affected, also apply the
  `architecture-governance` secure-architecture preset

{CORE_TEMPLATE}

Audit-ready evidence requirement:

- Ensure this specify wrapper requires concrete Markdown evidence/checklist updates for every applicable checkpoint.
- If a checkpoint does not apply in the current Spec-Kit run, require `N/A` with a short rationale instead of omitting it.
- If a checkpoint is undecided, require `Open` with owner, follow-up, and re-evaluation trigger.
