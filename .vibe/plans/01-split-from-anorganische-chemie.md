---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Keep all four keys.
# Archetype as in the app's first plan; set it when you start. Never changes.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit. Change the value line below, never this comment.
phase: commit
# prePushFailures: failed pre-push runs of this increment, written by the hook. Never change it.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks. Never change it.
failedChecks: { app-content-guide: 1 }
---

# Plan: chemie-reaktionen aus anorganische-chemie

*Begonnen 2026-11-03. Explore, Plan, Code, Commit.*

## Goal

Die App anorganische-chemie hatte zwei Stränge der Lernlandkarte Chemie (`stoffe-und-teilchen` und
`chemische-reaktion`). Eine App hat genau einen Strang (KD-07, KD-20 in lernapps/apps). Diese App übernimmt die Seiten
`reaktionen` und `reaktionsgleichungen` und steht im Strang `chemie/chemische-reaktion`.

## Key decisions

- Explainer Format 2: `format: 2`, `strand: chemie/chemische-reaktion`. Seite `reaktionen`:
  `kennzeichen-chemischer-reaktionen`, `reaktion-oder-zustandsaenderung`. Seite `reaktionsgleichungen`:
  `reaktionsgleichung-aufstellen`, `massenerhaltung`. Alle ids gegen `map/chemie.yaml` geprüft, alle im Strang.
- Kapitel- und Seiten-ids bleiben (`reaktionen/<seite>/`); die Adresse ist neu: <https://lernapps.net/chemie-reaktionen/>.
- Voraussetzungen aus `stoffe-und-teilchen`, die die App nicht übt, bekommen Wiederholungsseiten (`recap`) im Kapitel
  `vorwissen`, vor den Seiten, die sie brauchen: `stoffeigenschaften-beschreiben`, `aggregatzustaende-beschreiben`
  (für `reaktionen`), `teilchenmodell`, `formeln-von-verbindungen` (für `reaktionsgleichungen`). `wortgleichung` und
  `daltonsches-atommodell` werden im Text von `reaktionsgleichungen` zur Karte verlinkt.
- Keine Komponenten und keine Daten: beide Seiten brauchen sie nicht.
- Selbsteinschätzung im Kapitel `reaktionen` (je 3 Übungen der beiden Seiten); `vorwissen` hat keine, weil
  Wiederholungsseiten keine Übung haben.
- `@lernapps/app-templates` auf 38c63dc, `@lernapps/tooling` auf d3d2a35 gepinnt: Wiederholungsseiten gibt es erst ab
  e5a1195 (app-templates). `vite-plus` 1.4.0 wie in den anderen Format-2-Apps.

## Explore

### Completed

- [x] Vertrag und Karte gelesen; Kompetenz-ids und `requires` gegen `map/chemie.yaml` geprüft.

## Plan

### Completed

- [x] Seiten, Daten und Komponenten bestimmt (keine); Wiederholungsseiten nach den `requires` der Bausteine.

## Code

### Completed

- [x] Seiten aus anorganische-chemie übernommen, `competencies` gesetzt, Wiederholungsseiten, Selbsteinschätzung.
- [x] `package.json`, `npm install`, README, Inhaltsleitfaden `.agents/skills/app-content/`.
- [x] `npm run build`, `npx lernapps check`.

## Commit

### Tasks

- [ ] Push des Branches `claude/vibrant-faraday-5qg8eu`; Pull Request und Veröffentlichung erst nach dem Merge von
      Format 2 in lernapps/app-templates.
- [ ] Repo-Einstellungen (GitHub Pages aus `gh-pages`) und Eintrag im Katalog mit `strand: chemie/chemische-reaktion`.

### Completed

## Retrospective

### Where I had to guess

- Titel der App „Chemie – Chemische Reaktionen“, die Einleitung und die Texte der Wiederholungsseiten
  `stoffeigenschaften` (neu geschrieben); die anderen drei stammen aus anorganische-chemie.
- `massenerhaltung` auf `reaktionsgleichungen`: die Seite übt nur den Atomaspekt (gleich viele Atome je Sorte).
