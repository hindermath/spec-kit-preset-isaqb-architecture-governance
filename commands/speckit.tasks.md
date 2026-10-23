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

## Nutzungshilfe / Reader help

DE: Systemaufbau und Architekturentscheidungen mit wenigen passenden Vorlagen erklären. Diese Command-Erklärung ändert keine Berechtigungen oder Voraussetzungen.
Die bestehenden technischen Feldnamen und Statuswerte nicht übersetzen oder
nur zum Bestehen eines Tests verändern. Einführung, Begriffe, Beispiel,
Ergebnis und Fehlerhilfe stehen im [deutschen Leserpfad](https://github.com/hindermath/spec-kit-preset-isaqb-architecture-governance/blob/main/docs/user-guide.md).

EN: Explain system structure and architecture decisions with a few suitable templates. This command explanation changes no authority or prerequisites.
Keep technical field names and states unchanged; never alter them just to pass.
See the [English reader path](https://github.com/hindermath/spec-kit-preset-isaqb-architecture-governance/blob/main/docs/user-guide.EN.md)
for introduction, terms, example, result and troubleshooting.
