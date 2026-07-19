# iSAQB Architecture Governance Preset

Version: `0.2.1`
Status: published, standard governance preset
Priority: `30`
Requires: Spec-Kit `>=0.8.0` (uses the `wrap` and `append` composition
strategies introduced in `0.8.x`).

## Zweck / Purpose

Dieses Standard-Preset bringt allgemeine Softwarearchitektur nach
iSAQB/CPSA-F und arc42 in Spec-Kit-Workflows. Es macht Architekturziele,
Kontext, Bausteine, Runtime View, Deployment View, Qualitätsanforderungen,
ADRs, Risiken und technische Schulden sichtbar.

*This standard preset injects general software architecture based on
iSAQB/CPSA-F and arc42 into Spec-Kit workflows. It makes architecture goals,
context, building blocks, runtime view, deployment view, quality requirements,
ADRs, risks, and technical debt visible.*

Das Qualitätsziel ist ein verständliches Architekturmodell, das
Implementierungsentscheidungen begründet und über einzelne Tasks hinaus
wartbar bleibt. Sichere Architektur im engeren Sinn bleibt Aufgabe von
`architecture-governance`.

*The quality goal is an understandable architecture model that explains
implementation decisions and remains maintainable beyond individual tasks.
Secure architecture in the narrower sense remains the responsibility of
`architecture-governance`.*

## Zielgruppen / Audience

Dieses Preset eignet sich, wenn:

- Architekturentscheidungen Wartbarkeit, Erweiterbarkeit, Betrieb,
  Integration oder Qualitätsattribute prägen;
- Teams leichte arc42/iSAQB-Artefakte ohne schweres Dokumentationsprogramm
  nutzen möchten;
- Lernende und neue Maintainer Systemstruktur und Begründungen nachvollziehen
  sollen;
- allgemeine Architekturarbeit getrennt von Security-Architektur geführt
  werden soll.

*Use this preset when architecture decisions shape maintainability,
extensibility, operations, integration, or quality attributes; when teams want
lightweight arc42/iSAQB artifacts; when learners and new maintainers should
understand system structure and reasoning; and when general architecture should
remain separate from secure architecture.*

## Lieferumfang / What It Provides

- Addenda für Constitution, Spec, Plan, Tasks und Agent-Guidance
- Wrapper für `speckit.specify`, `speckit.plan` und `speckit.tasks`
- Templates für Architecture Vision, Context View, Building Block View,
  Runtime View, Deployment View, Quality Scenarios, ADRs und Risiken
- auditfähige Spec-Kit-Run-Evidence-Felder für Anwendbarkeit, `N/A`-Begründung,
  Reviewer, Evidence-Pfad, Restrisiko und Follow-up

*The preset provides addenda for the main Spec-Kit artifacts and agent
guidance, wraps the normal Specify/Plan/Tasks flow, and supplies templates for
architecture vision, context view, building-block view, runtime view,
deployment view, quality scenarios, ADRs, and risks.*

## Nicht enthalten / What It Does Not Provide

Das Preset entscheidet keine Architektur, erzeugt keine Diagramme
automatisch, validiert keine vollständige arc42-Dokumentation und ersetzt
keine Architekturreview. Es erteilt keine Repository-, Merge-, Deployment-
oder Provider-Administrationsrechte.

*The preset does not decide architecture, create diagrams automatically,
validate complete arc42 documentation, or replace architecture review. It
grants no repository, merge, deployment, or provider-administration authority.*

## Voraussetzungen / Prerequisites

1. kompatible GitHub Spec-Kit CLI;
2. gültige Spec-Kit-Integration im Ziel-Repository;
3. versionierte Constitution und Agent-Guidance;
4. geklärte Evidence-Orte, standardmäßig `docs/architecture/` und
   `docs/architecture/adr/`;
5. ein initiales Verständnis von Systemzweck, Stakeholdern, Kontext und
   Qualitätszielen.

*Before installation, use a compatible GitHub Spec-Kit CLI, a valid Spec-Kit
integration, versioned constitution and agent guidance, clear evidence
locations, and an initial understanding of system purpose, stakeholders,
context, and quality goals.*

## Installation / Installation

### Veröffentlichter Tag / Published Tag

```bash
specify preset add \
  --from https://github.com/hindermath/spec-kit-preset-isaqb-architecture-governance/archive/refs/tags/v0.2.1.zip \
  --priority 30
specify preset info isaqb-architecture-governance
```

### Entwicklungs-Checkout / Development Checkout

```bash
specify preset add --dev /path/to/isaqb-architecture-governance --priority 30
specify preset info isaqb-architecture-governance
```

### Empfohlene Kombination / Recommended Composition

| Priority | Preset |
|---:|---|
| 10 | `security-governance` |
| 20 | `architecture-governance` |
| 30 | `isaqb-architecture-governance` |
| 40 | `a11y-governance` |
| 50 | `cross-platform-governance` |
| 60 | `agent-parity-governance` |

`isaqb-architecture-governance` behandelt allgemeine Architektur.
`architecture-governance` behandelt sichere Architektur. Wenn beide Flächen
relevant sind, werden beide Presets zusammen genutzt.

*`isaqb-architecture-governance` covers general architecture.
`architecture-governance` covers secure architecture. Use both presets when
both surfaces are relevant.*

## Standards und Konzepte / Standards and Concepts

- `iSAQB CPSA-F` architecture work products and method discipline
- `arc42` structure beyond Section 8
- architecture goals and constraints
- system context and external interfaces
- building-block view
- runtime scenarios
- deployment view
- quality attribute scenarios
- Architecture Decision Records (`ADRs`)
- architecture risks and technical debt

## Preset-Strategie / Preset Strategy

- allgemeine Architektur-Governance an `constitution-template`,
  `spec-template`, `plan-template` und `tasks-template` anhängen
- ein eigenständiges Agent-Guidance-Addendum bereitstellen
- `speckit.specify`, `speckit.plan` und `speckit.tasks` mit einem
  iSAQB/arc42-Workflow umhüllen
- Starter-Templates für Architekturvision, Kontext, Bausteine, Runtime,
  Deployment, Qualitätsszenarien, ADRs und Risiken liefern

## Evidenzvorlagen / Evidence Templates

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

## Prüfung / Verification

```bash
specify preset list
specify preset info isaqb-architecture-governance
specify preset resolve
specify check
```

Prüfe zusätzlich, ob Architektur-Evidence entweder vorhanden oder im Plan als
zu erzeugendes Artefakt benannt ist.

*Also verify that architecture evidence already exists or is named in the plan
as work to create.*

## Fehlersuche / Troubleshooting

### Architektur bleibt task-nah / Architecture Stays Task-Level

Ergänze Kontext, Bausteine, Runtime- oder Deployment-Sicht, sobald einzelne
Tasks ohne Systembild nicht mehr sinnvoll bewertbar sind.

### Security-Architektur fehlt / Secure Architecture Is Missing

Nutze zusätzlich `architecture-governance`, wenn Trust Boundaries, Threat
Modeling, STRIDE/CAPEC, Zero Trust oder S-ADRs relevant sind.

### Diagramme fehlen / Diagrams Are Missing

Dieses Preset erzwingt keine Diagrammform. Halte Text, Tabellen oder Diagramme
so, dass Zielgruppen Entscheidungen und Struktur nachvollziehen können.

## Version 0.2.1 / Version 0.2.1

`v0.2.1` ergänzt Qualitätsszenarien für Teilfehler, Unterbrechung,
Wiederaufnahme, idempotente Wiederholung und gestapelte Abhängigkeiten.

*`v0.2.1` adds quality scenarios for partial failure, interruption, resume,
idempotent retry, and stacked dependencies.*

## Version 0.2.0 / Version 0.2.0

`v0.2.0` ergänzt auditfähige Spec-Kit-Run-Evidence-Felder, damit generierte
Markdown-Dokumente und Checklisten Anwendbarkeit, `N/A`-Begründung, Reviewer,
Evidence-Pfad, Restrisiko und Follow-up pro standardsrelevantem Spec-Kit-Lauf
aufzeichnen können.

*`v0.2.0` adds audit-ready Spec-Kit run evidence fields so generated Markdown
documents and checklists can record applicability, `N/A` rationale, reviewer,
evidence path, residual risk, and follow-up per standards-relevant Spec-Kit
run.*

## Kompatibilitäts- und Sicherheitsübersicht / Compatibility and Safety Summary

- kompatibel mit Spec-Kit `>=0.8.0`
- priorisiert als Stufe `30`
- ergänzt, aber ersetzt nicht sichere Architektur-Governance
- keine automatische Diagramm-, Review-, Remote- oder Provider-Aktion
- Architekturentscheidungen bleiben projektbezogene Evidence

## License

MIT. See `LICENSE`.
