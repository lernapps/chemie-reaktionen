---
name: app-content
description: Use for any content work in this app - researching, writing, extending, correcting or reviewing its competencies, chapters, pages, rounds, questions, exercises, figures, terms or sources. This app's own content decisions; they take precedence over the generic lernapps content skills. Load it before you change any content.
---

# Content guide of this app

Explainer "Chemie – Chemische Reaktionen" (de, en) for Klasse 7/8 (assumption of the creator, not fixed by a Lehrplan).
Plan: `.vibe/plans/01-split-from-anorganische-chemie.md`.

## Curriculum

- Schulform, Land: none. Jahrgang: Klasse 7/8 (assumption).
- Orientation: KMK, Bildungsstandards im Fach Chemie für den Mittleren Schulabschluss (Jahrgangsstufe 10), Beschluss
  vom 16.12.2004, https://www.kmk.org/fileadmin/Dateien/veroeffentlichungen_beschluesse/2004/2004_12_16-Bildungsstandards-Chemie.pdf.
  Used: F 3.1, F 3.4. Order and depth for Klasse 7/8 are derived by us, not quoted from a Lehrplan.
- Die App gehört zum Strang `chemie/chemische-reaktion` der Lernlandkarte (`strand` in `src/app.yaml`, Format 2). Jede
  Übungsseite nennt in `competencies` die Bausteine, die sie übt: ids aus `map/chemie.yaml` in lernapps/apps, nur aus
  diesem Strang. Fehlt ein Baustein, wird er dem Katalog vorgeschlagen, nicht in der App erfunden.
- Die App entstand aus der Seite `reaktionen` der App anorganische-chemie (Entscheidung KD-20: eine App, ein Strang).
  Seiten-ids und Adressen (`reaktionen/<seite>/`) sind von dort übernommen.

## Competencies

Je Seite die Bausteine der Karte (Strang `chemische-reaktion`), Datei `src/<kapitel>/<seite>.yaml`.

- Kapitel `reaktionen` (Chemische Reaktionen), vier Seiten, je ein Baustein, in der Reihenfolge der `requires`:
  - `reaktionen`: `kennzeichen-chemischer-reaktionen`. Übungen: `beobachtung-hinweis`, `gas-beweis`, `sicheres-zeichen`.
  - `zustandsaenderung`: `reaktion-oder-zustandsaenderung`. Übungen: `vorgang-art`, `kerzenwachs`, `zucker-braun`.
  - `massenerhaltung`: `massenerhaltung` (Versuch mit der Waage, offen und geschlossen, dazu die Atome). Übungen:
    `waage-geschlossen`, `stahlwolle-offen`, `masse-magnesium`, `atome-entstehen`.
  - `reaktionsgleichungen`: `reaktionsgleichung-aufstellen`. Übungen: `koeffizient-wasser`, `koeffizient-magnesium`,
    `koeffizient-ammoniak`, `koeffizient-methan`, `gleichung-schritte`.
  - Neue Seite: 1 bis 3 ihrer Übungen in `selfAssessment` aufnehmen, wie Skill `lernapps-explainer-self-assessment` sagt.
- Kapitel `vorwissen` (Wiederholungsseiten, `recap`): Voraussetzungen dieser Bausteine aus dem Strang
  `stoffe-und-teilchen`, die die App nicht übt.
  - `stoffeigenschaften` (`chemie/stoffeigenschaften-beschreiben`), `aggregatzustaende`
    (`chemie/aggregatzustaende-beschreiben`) vor `reaktionen/reaktionen`;
  - `teilchenmodell` (`chemie/teilchenmodell`), `formeln` (`chemie/formeln-von-verbindungen`) vor
    `reaktionen/reaktionsgleichungen`.
- Nicht wiederholt, nur im Text von `reaktionsgleichungen` zur Karte verlinkt: `wortgleichung` (eigener Strang, noch
  nicht geübt) und `daltonsches-atommodell`. Wird eine davon eine Seite der App, den Link durch die Seite ersetzen.

## Content structure

- Chapter folder `src/<chapter>/` with `chapter.yaml` (title, summary, pages), listed in `src/app.yaml`. Chapters
  `vorwissen` (recaps first) and `reaktionen`.
- Übungsseiten: the sections in this order and with these ids: `warum`, `regel`, `beispiel` (a box `example`), `uebung`.
  Titles: Warum, Regel, Beispiel, Übung (English: Why, Rule, Example, Practice). Every page has at least one exercise in
  `uebung`.
- Wiederholungsseiten: `recap: chemie/<id>` instead of `competencies`, only descriptive blocks (`regel`, `beispiel`),
  no exercise, one competency each; title "… – kurz wiederholt". The content comes from the page of the app
  anorganische-chemie that teaches the competency; correct it there as well.
- A page explains one competency group in about 150–250 words in plain German plus exercises.
- Ids short and stable; never reuse a removed id (`explainer-stable-ids`).

## Languages

- `languages: [de, en]`, German first. Every learner text is a map `{ de, en }`; ids, numbers, formulas, symbols are the
  same.
- English terms: Reaktionsgleichung = reaction equation, Koeffizient = coefficient, Zustandsänderung = change of
  state, Ausgangsstoff = starting substance, Produkt = product.

## Terminology

- Learners are addressed with "du". Short sentences, active voice, technical terms explained at first use and as a
  `definition` block (glossary).
- Terms: chemische Reaktion, Zustandsänderung, Reaktionsgleichung, Koeffizient, Index, Ausgangsstoff, Produkt, Atom,
  Formel.
- Avoid "Ion", "Bindung", "Elektronegativität", "Stoffmenge" (other strands, not taught here).
- Chemistry notation in `formula` blocks and in text with `\ce{…}`; in questions of quiz type plain Unicode (see below).

## Exercise patterns

- Auswählen: `multiple-choice` where several options are right, every option with `info` (`vorgang-art`).
- Urteilen: `true-false` with the reason in `explanation` (`atome-entstehen`).
- Ausgleichen: a `number` question with the equation and a blank `x` in its text (`x H₂ + O₂ → 2H₂O`, plain Unicode),
  the typical mistake per exercise with its message. The equations are fixed in the YAML; every equation was checked
  against a Wikipedia article (water, magnesium oxide, ammonia, methane).
- Ordnen: `ordering` for a fixed order (`gleichung-schritte`).
- Self-assessment: one in the chapter `reaktionen` (3 exercises on each of its two pages). The chapter `vorwissen` has
  none: recap pages have no exercise. New exercises: add 1 to 3 of them to `selfAssessment`, as skill
  `lernapps-explainer-self-assessment` says.

## Figures

- No figures so far: no images, no components. A figure would need `alt`, a caption and a look at 360 px.

## Sources

- KMK Bildungsstandards (above).
- Serlo Chemie (CC BY-SA 4.0), linked only, no sentences copied: `https://de.serlo.org/chemie/18885/chemische-reaktionen`,
  `https://de.serlo.org/chemie/155738/chemische-zeichensprache`.
- Reaktionsgleichung (de.wikipedia.org, CC BY-SA): facts taken, no sentences copied; exercises link to the article.

## Adding a chapter or round

1. Write the competency ("Ich kann …") with its id from `map/chemie.yaml` (strand `chemische-reaktion`) into
   "Competencies" above.
2. Create `src/<chapter>/chapter.yaml` and list the folder in `chapters` of `src/app.yaml`.
3. One page file per competency with the sections `warum`, `regel`, `beispiel`, `uebung`; list the pages in
   `chapter.yaml` in reading order.
4. A prerequisite of another strand or outside the app's scope: a recap page before it, or a link to its page on the
   map in the page's text.
5. `npx lernapps check`, then commit.

## Rules learned from mistakes

- Texts of quiz-type exercises (`number`, `single-choice`, …) may contain `$…$` formulas, but the end-to-end test "one
  <math> per formula" does not count them yet (issue lernapps/app-templates#47) and fails the check. Until that is fixed:
  write formulas in the question text with Unicode subscripts and an arrow (`x H₂ + O₂ → 2H₂O`). A `formula` block above
  the question is not used: on a phone it scrolls out of sight.
