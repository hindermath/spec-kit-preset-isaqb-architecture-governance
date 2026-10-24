# User guide: isaqb-architecture-governance

<!-- current-package: 0.2.4 -->

[Release-Abschluss und Verbesserungsprofil / Publication closeout and improvement profile](release-0.2.4-validation.md).

The later main-branch documentation follow-up does not change the existing tag archive.

[Deutsch](user-guide.md) · [Preset reference](../README.md)

Published package **v0.2.4**. Verify the actually published version on the [release page](https://github.com/hindermath/spec-kit-preset-isaqb-architecture-governance/releases). This guide grants no merge, release or project authority.

Contents: [Start](#start) · [Example](#example) · [Terms](#terms) · [Routing](#routing) · [Troubleshooting](#help) · [References](#references)

<a id="start"></a>

## Start and audience

Explain system structure and architecture decisions with a few suitable templates.

For apprentices in all four IHK IT occupations: IT specialists (application development, systems integration, data/process analysis, digital networking), IT systems electronics technicians, digitalisation management specialists and IT systems management specialists. Also for developers without specialist governance knowledge. You do not need to edit hashes or invent model IDs to ask for the next step. Ask the maintainer to check technical bindings.

Use an already initialized Spec Kit target repository. Read the prerequisites and installation instructions in the preset reference first; replace example paths. A template is a starter, not completed evidence. Installation adds instructions and files; it does not start a feature or grant approval.

Input: Name asynchronous processing, existing architecture files and affected quality goals.

<a id="example"></a>

## One complete example

1. Describe the bounded task and existing files. Do not silently widen scope.
2. Use the following example in the agent chat. It is a prompt, not a shell command:

~~~text
For asynchronous jobs use runtime-view-template, quality-scenarios-template and architecture-decision-template. Reuse existing docs/architecture files and plan failure-case tasks.
~~~

3. Runtime view, quality scenarios and the decision explain order, failures and alternatives. The agent does not deterministically select starters from a feature name.
4. Check the result and recorded next action. Changes, repair, feature execution and delivery each need their applicable authority. A passing technical check is not human acceptance.

Read-only installation check in the initialized target repository:

~~~text
specify preset info isaqb-architecture-governance
specify preset resolve runtime-view-template
~~~

Resolve reports the selected template source; it does not fill in or execute that template.

<a id="terms"></a>

## Terms and evidence

- **arc42:** Structure for architecture documentation, not a required pile of empty files.
- **CPSA-F:** Software-architecture fundamentals from the iSAQB curriculum; the preset is not an examination or certification.
- **ADR:** Architecture Decision Record: decision, alternatives and consequences.

Where the existing contract uses these values: Applicable means relevant, not passed; N/A needs a reason; Open needs the recorded next action and responsible person. This explanation adds no fields to existing schemas. Keep genuine historical evidence; never edit a hash or approval just to make a check pass.

<a id="routing"></a>

## Stable routing and explicit actions

| Command | Declared role |
|---|---|
| `speckit.specify` | `frontier-reasoning` |
| `speckit.plan` | `frontier-reasoning` |
| `speckit.tasks` | `frontier-reasoning` |

Roles describe tasks, not a model name or quality guarantee. Read the actual model-routing.json contract; generic examples such as coding-review do not override a stronger command requirement. The existing autonomous runner retains the strongest overlapping role, independently of installation priority. Merely installing a role contract does not switch a live chat or configure personal profiles.

A model-free script check and an agent assessment are different activities. Model calls, including model-access preflights, can consume quota even when they are read-only. No probe or provider switch is authorized by this documentation. No new dynamic-routing implementation is included.

Package version, schema version and historical field test are different facts. Earlier acceptance applies only to its recorded scope and source state.

<a id="help"></a>

## Troubleshooting and safe next action

If a starter is missing, check its registered manifest name. Evidence must explain the specific case; do not duplicate suitable existing documents.

If a command or template is missing, inspect preset info and the manifest below. Check the documented minimum tools and enabled installation. Resolve ambiguity with the maintainer; do not change policy, disable validators or claim an unperformed test. A safety blocker remains a blocker.

This language/accessibility pass targets CEFR B2 and applicable WCAG 2.2 AA. Static tests do not certify that target. Screen-reader, Braille and representative-user tests not actually performed remain unverified.

<a id="references"></a>

## Templates and deeper reference

- [`architecture-vision-template`](../templates/architecture-vision-template.md)
- [`context-view-template`](../templates/context-view-template.md)
- [`building-block-view-template`](../templates/building-block-view-template.md)
- [`runtime-view-template`](../templates/runtime-view-template.md)
- [`deployment-view-template`](../templates/deployment-view-template.md)
- [`quality-scenarios-template`](../templates/quality-scenarios-template.md)
- [`architecture-decision-template`](../templates/architecture-decision-template.md)
- [`architecture-risks-template`](../templates/architecture-risks-template.md)

These names identify available starters; they are not an instruction to create every file. Reuse existing suitable evidence. JSON field names remain technical identifiers, not translated keys.

- [Manifest and prerequisites](../preset.yml)
- [Stable command-role contract](../model-routing.json)
- [Documentation scope, review and test limits](documentation-closeout.md)
