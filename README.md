# iSAQB Architecture Governance Preset

Version: `0.2.2`
Status: published, standard governance preset
Priority: `30`
Requires: Spec-Kit `>=0.8.0` (uses the `wrap` and `append` composition
strategies introduced in `0.8.x`).

## Orientierung / Start Here

Du brauchst keine vollständige arc42-Dokumentation, um zu beginnen. Benenne
deine Änderung, die betroffenen Architekturaspekte und vorhandene Dokumente.
Das Preset ergänzt Arbeitsanweisungen; passende Starter und Zielpfade solltest
du ausdrücklich nennen. Ein Starter ist eine auszufüllende Vorlage, noch kein
Nachweis (Evidence). Ein Architecture Decision Record (ADR) hält eine wichtige
Entscheidung, Alternativen und Folgen fest.

*You do not need a complete arc42 document set to begin. Describe your change,
the affected architecture concerns, and existing documents. The preset adds
workflow instructions; explicitly name relevant starters and output paths.
A starter is a template to fill in, not evidence yet. An Architecture Decision
Record (ADR) records a significant decision, alternatives, and consequences.*

- Einstieg / Getting started: [Voraussetzungen / Prerequisites](#prerequisites),
  [Installation / Installation](#installation),
  [Automatik und Grenzen / Automation and Limits](#automation).
- Anwendung / Using the preset: [Vorlagenauswahl / Template Selection](#templates),
  [Ablauf / Workflow](#workflow), [Beispiel / Example](#async-example).
- Vertiefung / Further reading: [Komposition / Composition](#composition),
  [Anwendbarkeit / Applicability](#applicability),
  [Prüfung / Verification](#verification), [Fehlersuche / Troubleshooting](#troubleshooting).
- Referenz / Reference: [Zweck / Purpose](#purpose),
  [Zielgruppen / Audience](#audience), [Lieferumfang / Contents](#contents),
  [Nicht enthalten / Exclusions](#exclusions), [Standards / Standards](#standards),
  [Strategie / Strategy](#strategy), [Versionen / Versions](#versions),
  [Kompatibilität / Compatibility](#compatibility), [Lizenz / License](#license).

<a id="purpose"></a>

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

<a id="audience"></a>

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

<a id="contents"></a>

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

<a id="exclusions"></a>

## Nicht enthalten / What It Does Not Provide

Das Preset entscheidet keine Architektur, erzeugt keine Diagramme
automatisch, validiert keine vollständige arc42-Dokumentation und ersetzt
keine Architekturreview. Es erteilt keine Repository-, Merge-, Deployment-
oder Provider-Administrationsrechte.

*The preset does not decide architecture, create diagrams automatically,
validate complete arc42 documentation, or replace architecture review. It
grants no repository, merge, deployment, or provider-administration authority.*

<a id="prerequisites"></a>

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

<a id="installation"></a>

## Installation / Installation

Führe CLI-Befehle im bereits mit Spec Kit initialisierten Ziel-Repository aus,
nicht im Quell-Repository dieses Presets. Die einzeiligen Befehle funktionieren
ohne Shell-spezifische Zeilenfortsetzung in Bash und PowerShell. Der
Entwicklungspfad unten ist ein Platzhalter und muss ersetzt werden.

*Run CLI commands in your existing Spec Kit target repository, not in this
preset's source repository. The single-line commands need no shell-specific
continuation in Bash or PowerShell. Replace the development path placeholder
below with your actual checkout path.*

### Veröffentlichter Tag / Published Tag

```bash
specify preset add --from https://github.com/hindermath/spec-kit-preset-isaqb-architecture-governance/archive/refs/tags/v0.2.2.zip --priority 30
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
| 10 | [security-governance](https://github.com/hindermath/spec-kit-preset-security-governance) |
| 20 | [architecture-governance](https://github.com/hindermath/spec-kit-preset-architecture-governance) |
| 30 | [isaqb-architecture-governance](https://github.com/hindermath/spec-kit-preset-isaqb-architecture-governance) |
| 40 | [a11y-governance](https://github.com/hindermath/spec-kit-preset-a11y-governance) |
| 50 | [cross-platform-governance](https://github.com/hindermath/spec-kit-preset-cross-platform-governance) |
| 60 | [agent-parity-governance](https://github.com/hindermath/spec-kit-preset-agent-parity-governance) |

`isaqb-architecture-governance` behandelt allgemeine Architektur.
`architecture-governance` behandelt sichere Architektur. Wenn beide Flächen
relevant sind, werden beide Presets zusammen genutzt.

*`isaqb-architecture-governance` covers general architecture.
`architecture-governance` covers secure architecture. Use both presets when
both surfaces are relevant.*

<a id="automation"></a>

## Automatik und Grenzen / Automation and Limits

Bei aktivierter, korrekt erzeugter Integration verbindet Spec Kit die im
[Manifest](preset.yml) registrierten Beiträge mit seinem normalen Ablauf:

- `wrap` umhüllt `speckit.specify`, `speckit.plan` und `speckit.tasks` mit
  Architektur-Anweisungen; `{CORE_TEMPLATE}` erhält den darunterliegenden
  Command-Inhalt.
- `append` ergänzt `constitution-template`, `spec-template`, `plan-template`
  und `tasks-template` um Architektur- und Evidence-Anforderungen.
- Die acht eigenständigen Architektur-Starter sind separat auflösbar. Das
  Agent-Guidance-Addendum ist ebenfalls eigenständig bereitgestellt; seine
  Registrierung allein belegt keine Übernahme in jede Agenten-Datei.

*With an enabled preset and correctly generated integration, Spec Kit combines
the contributions registered in the [manifest](preset.yml) with its normal flow:
`wrap` surrounds Specify/Plan/Tasks with architecture instructions and inserts
the lower command content at `{CORE_TEMPLATE}`; `append` adds requirements to
the constitution, spec, plan, and tasks templates. The eight architecture
starters and the agent-guidance addendum are separately available. Registering
the addendum does not prove that every agent file incorporates it.*

**Automatisch sind die eingebundenen Anweisungen, nicht die fertigen
Architekturdokumente.** v0.2.2 enthält keine feste Zuordnung
„Feature-Typ → Starter“, keinen automatischen Kopierlauf nach
`docs/architecture/` und keinen eigenständigen Architektur-Validator.
Der Agent beurteilt den Kontext; sein Verhalten ist keine deterministische
Vorlagenauswahl. Nenne relevante Starter und Zielpfade ausdrücklich und prüfe
das Ergebnis. Installation startet weder ein Feature noch Review oder Umsetzung.

***The instructions are integrated automatically, not completed architecture
documents.*** v0.2.2 has no fixed feature-to-starter mapping, automatic copying
into `docs/architecture/`, or standalone architecture validator. The agent
interprets context; this is not deterministic starter selection. Explicitly
name relevant starters and output paths, then inspect the result. Installation
starts neither a feature nor review or implementation.

<a id="composition"></a>

## Zusammenspiel und Prioritäten / Composition and Priorities

Die [empfohlene Kombination](#installation) ist eine Orientierung, keine
Voraussetzung, alle anderen Presets zu installieren. Weitere Governance- und
Assurance-Presets können zusätzliche Anforderungen beitragen. Ihre Installation
allein führt keine Prüfungen aus und erteilt keine menschliche Freigabe.

*The [recommended composition](#installation) is guidance, not a requirement to
install every other preset. Additional governance and assurance presets may
contribute requirements. Installation alone runs no reviews and grants no human
acceptance.*

Eine kleinere Prioritätszahl bedeutet höhere Auflösungspriorität, nicht
„früher freigegeben“. Für denselben Namen und Typ gilt:

- `append`: ergänzt den darunterliegenden Inhalt;
- `wrap`: umhüllt ihn; mehrere Wrapper können verschachtelt werden;
- `replace`: ersetzt ihn; Beiträge unter der wirksamen Ersatzschicht können
  entfallen. Ohne Strategieangabe ist `replace` der Standard bei den hier
  registrierten eigenständigen Startern;
- ein lokaler Projekt-Override kann die Preset-Auflösung ersetzen.

*A lower priority number means higher resolution precedence, not earlier
approval. For the same name and type, `append` adds to lower content, `wrap`
surrounds it and can nest, and `replace` substitutes it, potentially excluding
lower contributions. The standalone starters registered here use the default
`replace` strategy. A project-local override can replace preset resolution.*

Eigene Prioritäten verändern die Reihenfolge, Verschachtelung oder Auswahl
gleichnamiger Inhalte. Nicht jede Kombination mit Drittanbieter-Presets oder
jede Reihenfolge ist geprüft. Priorität löst keine fachlichen Widersprüche und
ersetzt weder Review-Frische noch Evidence-, Risiko- oder Freigabe-Gates.
Prüfe im Ziel-Repository `specify preset resolve plan-template` und die erzeugte
Plan-/Tasks-Command- oder Skill-Datei deines Agenten. Suche dort nach den
iSAQB-Anweisungen und den weiterhin benötigten Beiträgen anderer Presets.

*Custom priorities change ordering, nesting, or selection of same-name content.
Not every third-party combination or ordering has been tested. Priority neither
resolves semantic conflicts nor replaces review freshness, evidence, risk, or
approval gates. In the target repository, inspect `specify preset resolve
plan-template` and your agent's generated Plan/Tasks command or skill files.
Check for iSAQB instructions and the other preset contributions you still need.*

<a id="standards"></a>

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

<a id="strategy"></a>

## Preset-Strategie / Preset Strategy

- allgemeine Architektur-Governance an `constitution-template`,
  `spec-template`, `plan-template` und `tasks-template` anhängen
- ein eigenständiges Agent-Guidance-Addendum bereitstellen
- `speckit.specify`, `speckit.plan` und `speckit.tasks` mit einem
  iSAQB/arc42-Workflow umhüllen
- Starter-Templates für Architekturvision, Kontext, Bausteine, Runtime,
  Deployment, Qualitätsszenarien, ADRs und Risiken liefern

*Append general architecture governance to the constitution, spec, plan, and
tasks templates; provide a standalone agent-guidance addendum; wrap
Specify/Plan/Tasks; and supply starters for architecture goals, views, quality
scenarios, decisions, and risks. The [manifest](preset.yml),
[Plan wrapper](commands/speckit.plan.md), and
[Tasks addendum](templates/tasks-addendum.md) define these contributions.*

<a id="templates"></a>
<a id="evidenzvorlagen--evidence-templates"></a>

## Vorlagenauswahl / Template Selection

Diese Auswahlhilfe ist eine Empfehlung für Menschen und Agenten, keine
implementierte automatische Auswahlregel. Wähle nur die relevanten Sichten;
aktualisiere vorhandene Dokumente statt parallele Wahrheiten anzulegen.
Die Zielpfade sind Beispiele im Ziel-Repository, keine Dateien dieses Presets.

*This guide is a recommendation for people and agents, not an implemented
automatic selection rule. Select relevant views only and update existing
documents instead of creating competing sources. Output paths are examples
in your target repository, not files supplied by this preset.*

| Starter / Starter | Wann verwenden? / When to use | Beispielziel / Example output |
| --- | --- | --- |
| [architecture-vision-template](templates/architecture-vision-template.md) | Neue Ziele, Stakeholder oder Randbedingungen / New goals, stakeholders, or constraints | `docs/architecture/vision.md` |
| [context-view-template](templates/context-view-template.md) | Externe Akteure oder Schnittstellen ändern sich / External actors or interfaces change | `docs/architecture/context-view.md` |
| [building-block-view-template](templates/building-block-view-template.md) | Module, Verantwortungen oder Abhängigkeiten ändern sich / Modules, responsibilities, or dependencies change | `docs/architecture/building-block-view.md` |
| [runtime-view-template](templates/runtime-view-template.md) | Interaktion, Asynchronität oder Fehlerbehandlung ändern sich / Interactions, asynchronous flow, or recovery change | `docs/architecture/runtime-view.md` |
| [deployment-view-template](templates/deployment-view-template.md) | Knoten, Umgebungen oder Betriebsabhängigkeiten ändern sich / Nodes, environments, or operational dependencies change | `docs/architecture/deployment-view.md` |
| [quality-scenarios-template](templates/quality-scenarios-template.md) | Qualitätsziele brauchen messbare Szenarien / Quality goals need measurable scenarios | `docs/architecture/quality-scenarios.md` |
| [architecture-decision-template](templates/architecture-decision-template.md) | Bedeutende Wahl mit Alternativen und Folgen / Significant choice with alternatives and consequences | `docs/architecture/adr/001-async-processing.md` |
| [architecture-risks-template](templates/architecture-risks-template.md) | Unsicherheit, Trade-offs oder technische Schulden / Uncertainty, trade-offs, or technical debt | `docs/architecture/risks.md` |

Standardort ist `docs/architecture/`, für ADRs `docs/architecture/adr/` mit
einer Datei pro Entscheidung. Nutzt dein Projekt andere Orte, benenne die
Abweichung ausdrücklich und gleiche sie mit den installierten Anweisungen ab;
das Preset bietet keine automatische Pfadumleitung. Spec, Plan und Tasks
müssen konsistente Pfade referenzieren. Sichere Architektur bleibt zusätzlich bei
`architecture-governance`, nicht ersatzweise in diesen allgemeinen Startern.

*Defaults are `docs/architecture/` and one file per decision in
`docs/architecture/adr/`. If your project uses other locations, explicitly
identify the deviation and reconcile it with the installed instructions; the
preset provides no automatic path remapping. Spec, plan, and tasks must use
consistent paths. Secure architecture remains an additional concern of
`architecture-governance`, not something these general starters replace.*

<a id="workflow"></a>

## Ablauf vom Bedarf zum Nachweis / Workflow from Need to Evidence

Die Command-Namen unten sind Agenten-Aktionen, keine Shell-Befehle. Verwende
die in deiner Integration vorhandene Slash-Command- oder Skill-Schreibweise.
Jede Phase setzt den Auftrag und die Freigaben deines Projekts voraus.

*The command names below are agent actions, not shell commands. Use the slash
command or skill spelling provided by your integration. Each phase requires
the task authority and approvals of your project.*

1. **Specify (`speckit.specify`):** Beschreibe Bedarf und Qualitätsziele.
   Erfasse Architektur-Anwendbarkeit und erwartete Evidence-Pfade in der Spec.
2. **Plan (`speckit.plan`):** Benenne relevante Starter, bestehende Dokumente,
   Zielpfade, Entscheidungen und Validierung. Dokumente können schon hier
   entworfen werden; eine bloße Planung ist noch kein fertiger Nachweis.
3. **Tasks (`speckit.tasks`):** Benenne verbleibende Erstellungs-/Update-Arbeit,
   konkrete Evidence-Dateien, Prüfmethode und Architekturreview. Bereits
   geleistete Arbeit nicht nochmals als Neuanlage planen.
4. **Umsetzung:** Fülle beziehungsweise aktualisiere die Dokumente und führe
   die geplanten Tests aus, wenn dies beauftragt ist. Dieses Preset registriert
   keinen eigenen `speckit.implement`-Wrapper.
5. **Review:** Vergleiche Spec, Plan, Tasks, reale Umsetzung und Evidence.
   Offene Punkte bleiben sichtbar; der Preset-Text ist keine Review-Abnahme.

*English workflow: (1) Specify the need, quality goals, architecture
applicability, and evidence paths. (2) Plan relevant starters, existing
documents, outputs, decisions, and validation; drafts may be produced here,
but planned work is not completed evidence. (3) Create explicit tasks for the
remaining evidence work, validation, and architecture review; do not duplicate
completed work. (4) Under execution authority, fill or update documents and run
tests; this preset supplies no `speckit.implement` wrapper. (5) Review spec,
plan, tasks, actual implementation, and evidence together; preset instructions
do not constitute review acceptance.*

<a id="async-example"></a>

## Beispiel: asynchrone Verarbeitung / Example: Asynchronous Processing

Ein Auftrag wird angenommen und später von einem Worker verarbeitet. Ein
Worker ist hier eine Komponente, die wartende Aufträge bearbeitet. Der Ablauf
ist ein Lernbeispiel, kein bereits ausgeführter Feature-Lauf und keine Vorgabe
für Queue-Technologie, Liefergarantien oder konkrete Grenzwerte.

*A request is accepted and later processed by a worker, a component handling
pending requests. This is a learning example, not an executed feature run or
a requirement for a particular queue technology, delivery guarantee, or limit.*

### 1. Bedarf beschreiben / Describe the Need

Beispieltext für Specify / Example input for Specify:

```text
DE: Ein angenommener Auftrag soll im Hintergrund verarbeitet werden.
Beschreibe sichtbaren Status, Fehler-/Wiederaufnahmeanforderungen und den
Umgang mit doppelter Zustellung. Halte ungeklaerte Garantien als Open fest.
EN: Process accepted requests in the background. Describe visible status,
failure/recovery needs, and duplicate delivery handling. Record unresolved
guarantees as Open.
```

### 2. Starter und Ziele benennen / Name Starters and Outputs

Beispieltext für Plan / Example input for Plan:

```text
DE: Verwende runtime-view-template und quality-scenarios-template als Starter.
Aktualisiere vorhandene Dokumentation; andernfalls erstelle
docs/architecture/runtime-view.md und docs/architecture/quality-scenarios.md.
Beschreibe Annahme, Verarbeitung, Status, Fehler, Retry und Wiederaufnahme.
Definiere messbare Qualitaetsszenarien und ihre Pruefung. Klaere Grenzwerte.
Pruefe, ob ein ADR sowie weitere Architektur-Sichten betroffen sind.
Verlinke Evidence-Pfade aus dem Plan; erfinde keine Testergebnisse oder Abnahme.
EN: Use runtime-view-template and quality-scenarios-template as starters.
Update existing documentation; otherwise create
docs/architecture/runtime-view.md and docs/architecture/quality-scenarios.md.
Describe acceptance, processing, status, failures, retry, and recovery.
Define measurable quality scenarios and validation. Clarify thresholds.
Assess whether an ADR and other architecture views are affected.
Link evidence paths from the plan; do not invent test results or acceptance.
```

Ein mögliches Qualitätsszenario: „Der Worker wird nach Annahme eines Auftrags
unterbrochen. Nach Neustart lässt sich sein Zustand aus dauerhaften Daten
ermitteln; Wiederholung erzeugt keine unzulässige zweite Wirkung.“ Welche
Wirkung zulässig ist, wie Dauerhaftigkeit erreicht wird und welche
Wiederherstellungszeit gilt, muss das Projekt festlegen und testen.

*One possible quality scenario: "The worker stops after a request is accepted.
After restart, its state can be reconstructed from durable data; retry causes
no prohibited duplicate effect." The project must define and test allowable
effects, persistence, and recovery time. This example does not establish those
guarantees or prove that they hold.*

### 3. Verbleibende Arbeit planen / Plan Remaining Work

Beispielhafte Tasks, noch nicht erledigt / Illustrative tasks, not completed:

```text
- [ ] DE: docs/architecture/runtime-view.md erstellen/aktualisieren:
      Ablauf, Komponenten, Fehler- und Wiederaufnahmepfade dokumentieren.
      EN: Create/update that runtime view with interactions and recovery paths.
- [ ] DE: docs/architecture/quality-scenarios.md erstellen/aktualisieren:
      QS-001 fuer Unterbrechung/Retry mit vereinbarter Messgroesse erfassen.
      EN: Create/update that quality catalogue with QS-001 and an agreed measure.
- [ ] DE: QS-001 durch einen Unterbrechungs-/Retry-Test pruefen und
      Testbefehl, Ergebnis sowie Evidence-Pfad im Qualitaetskatalog verlinken.
      EN: Validate QS-001 with interruption/retry testing; link command,
      outcome, and evidence in the quality catalogue.
- [ ] DE: Architekturreview: Spec, Plan, Tasks, Umsetzung und beide
      Evidence-Dateien abgleichen; offene Risiken mit Owner/Trigger erfassen.
      EN: Review consistency across all artefacts and implementation;
      record open risks with owner and reevaluation trigger.
```

Ergänze ein ADR mit Alternativen und Folgen, wenn die Entscheidung für
Asynchronität architektonisch bedeutend ist. Veränderte Modulgrenzen können
eine Bausteinsicht, neue Infrastruktur eine Deployment-Sicht erfordern.
Zwei gewählte Starter sind daher weder eine vollständige Architekturprüfung
noch eine Ausnahme von anderen anwendbaren Preset-Anforderungen.

*Add an ADR with alternatives and consequences if choosing asynchronous
processing is architecturally significant. Changed module boundaries may need
a building-block view; new infrastructure may need a deployment view. Two
selected starters are neither a complete architecture assessment nor an
exemption from other applicable preset requirements.*

<a id="applicability"></a>

## Vorhandene Evidence und Anwendbarkeit / Existing Evidence and Applicability

- `Applicable`: Der Aspekt betrifft den aktuellen Scope. Benenne konkrete
  Dokumente und Prüfungen; der Status selbst bedeutet nicht „bestanden“.
- `N/A`: Nicht anwendbar. Dokumentiere kurze Begründung und Trigger für eine
  erneute Prüfung statt den Punkt still wegzulassen.
- `Open`: Noch ungeklärt oder unvollständig. Halte Owner, Follow-up und
  Re-Evaluation-Trigger fest; keine Annahmen als bestandene Evidence ausgeben.

*`Applicable` means the concern is in scope and requires named evidence and
validation, not that it passed. `N/A` means not applicable, with a rationale
and reevaluation trigger rather than silent omission. `Open` means unresolved
or incomplete, with an owner, follow-up, and reevaluation trigger; assumptions
are not passing evidence.*

Lies bestehende Architektur-Evidence zuerst und prüfe ihre Gültigkeit für die
Änderung. Verlinke oder aktualisiere sie gezielt; kopiere weder alte
Testergebnisse noch Reviewer-/Freigabeangaben als neue Abnahme. Fülle relevante
Run-, Owner-, Reviewer- und Evidence-Felder sowie die Matrix aus. Ein leerer
Starter oder ein Pfad ohne Inhalt ist kein Nachweis. Das Preset bescheinigt
weder Zertifizierung noch vollständige Normkonformität.

*Read existing architecture evidence first and check whether it remains valid
for the change. Link or update it deliberately; do not copy old test results,
reviewer fields, or approvals as new acceptance. Complete relevant run, owner,
reviewer, evidence fields, and matrix rows. Empty starters and paths without
content are not evidence. The preset certifies neither compliance nor complete
conformance to a standard.*

<a id="verification"></a>

## Prüfung / Verification

Im integrierten Ziel-Repository / In the integrated target repository:

```bash
specify preset list
specify preset info isaqb-architecture-governance
specify preset resolve plan-template
specify preset resolve tasks-template
specify preset resolve runtime-view-template
specify preset resolve quality-scenarios-template
specify check
```

`list` und `info` zeigen Installation und Metadaten; `resolve` zeigt die
Quelle einer benannten Vorlage und gegebenenfalls ihre Kompositionskette.
Es erzeugt keine ausgefüllte Evidence. `specify check` prüft die vom CLI
unterstützte Werkzeugverfügbarkeit, nicht die fachliche Architekturvollständigkeit.
Prüfe zusätzlich die erzeugten Agentenflächen, konsistente Zielpfade in
Spec/Plan/Tasks, ausgefüllte Evidence und reale Validierungsergebnisse.

*`list` and `info` show installation and metadata; `resolve` shows the source
of a named template and, where applicable, its composition chain. It does not
create completed evidence. `specify check` checks tool availability supported
by the CLI, not professional architecture completeness. Also inspect generated
agent surfaces, consistent paths across spec/plan/tasks, completed evidence,
and actual validation results.*

<a id="troubleshooting"></a>

## Fehlersuche / Troubleshooting

### Starter werden nicht verwendet / Starters Are Not Used

Nenne Starter und Zielpfade ausdrücklich. Prüfe mit `resolve <template-name>`,
ob das erwartete Preset liefert, und kontrolliere die erzeugten Plan-/Tasks-
Anweisungen auf lokale Overrides oder verdrängende `replace`-Beiträge.

*Explicitly name starters and output paths. Use `resolve <template-name>` to
check the supplying preset; inspect generated Plan/Tasks instructions for
project overrides or replacing contributions.*

### Müssen alle acht Dokumente entstehen? / Must All Eight Documents Be Created?

Nein. Wähle anhand der Änderung; aktualisiere vorhandene Evidence. Begründe
nicht anwendbare Prüfpunkte. Eine automatische Acht-Dateien-Erzeugung ist
nicht Teil des Presets.

*No. Select according to the change and update existing evidence. Explain
non-applicable checkpoints. Automatic generation of eight documents is not
part of the preset.*

### Architektur bleibt task-nah / Architecture Stays Task-Level

Ergänze Kontext, Bausteine, Runtime- oder Deployment-Sicht, sobald einzelne
Tasks ohne Systembild nicht mehr sinnvoll bewertbar sind.

*Add context, building-block, runtime, or deployment views when individual
tasks can no longer be meaningfully assessed without a system model.*

### Security-Architektur fehlt / Secure Architecture Is Missing

Nutze zusätzlich `architecture-governance`, wenn Trust Boundaries, Threat
Modeling, STRIDE/CAPEC, Zero Trust oder S-ADRs relevant sind.

*Also use `architecture-governance` when trust boundaries, threat modeling,
STRIDE/CAPEC, Zero Trust, or security ADRs are relevant.*

### Diagramme fehlen / Diagrams Are Missing

Dieses Preset erzwingt keine Diagrammform. Halte Text, Tabellen oder Diagramme
so, dass Zielgruppen Entscheidungen und Struktur nachvollziehen können.

*No diagram notation is enforced. Use understandable text, tables, or diagrams
with equivalent textual explanations for the intended audience.*

<a id="versions"></a>

## Version 0.2.2 / Version 0.2.2

`v0.2.2` veröffentlicht den agentenneutralen `model-routing.json`-Vertrag für
die Komposition mit Model Routing Governance; iSAQB-Regeln bleiben unverändert.

*`v0.2.2` publishes the agent-neutral `model-routing.json` contract for
composition with Model Routing Governance; iSAQB rules are unchanged.*

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

<a id="compatibility"></a>

## Kompatibilitäts- und Sicherheitsübersicht / Compatibility and Safety Summary

- kompatibel mit Spec-Kit `>=0.8.0`
- priorisiert als Stufe `30`
- ergänzt, aber ersetzt nicht sichere Architektur-Governance
- keine automatische Diagramm-, Review-, Remote- oder Provider-Aktion
- Architekturentscheidungen bleiben projektbezogene Evidence

*Compatible with Spec Kit `>=0.8.0`, recommended priority `30`; complements
secure architecture governance without replacing it. No automatic diagrams,
reviews, remote or provider actions; decisions remain project-specific evidence.*

<a id="license"></a>

## Lizenz / License

MIT. Siehe / See [LICENSE](LICENSE).
