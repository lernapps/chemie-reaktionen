# Chemie: Chemische Reaktionen

Chemische Reaktionen erkennen und einfache Reaktionsgleichungen aufstellen, für Klasse 7 und 8: <https://lernapps.net/chemie-reaktionen/>. Teil von [lernapps.net](https://lernapps.net/).

Die App gehört zum Strang **Chemische Reaktion** der Lernlandkarte Chemie (`strand: chemie/chemische-reaktion`) und
soll entlang dieses Strangs wachsen. Bisher hat sie zwei Übungsseiten im Kapitel `reaktionen` (Chemische Reaktionen;
Reaktionsgleichungen) und das Kapitel `vorwissen` mit vier kurzen Wiederholungsseiten (Stoffeigenschaften,
Aggregatzustände, Teilchenmodell, Symbole und Formeln), die Voraussetzungen aus dem Strang Stoffe und Teilchen
wiederholen. Jede Übungsseite nennt die Bausteine der Lernlandkarte, die sie übt (`competencies`), jede
Wiederholungsseite den, den sie wiederholt (`recap`).

Jede Seite erklärt eine Sache mit Regel und Beispiel; die Übungsseiten enden mit Aufgaben, die sofort sagen, ob das
Ergebnis stimmt. Jede Seite ist ohne JavaScript lesbar. Kein Server, kein Tracking, keine Anfrage an fremde Server.
Deutsch und Englisch.

Die App entstand aus der App [anorganische-chemie](https://github.com/lernapps/anorganische-chemie), die zwei Stränge
der Lernlandkarte in einer App hatte (Entscheidung KD-20: eine App, ein Strang). Die Seiten haben dieselben Adressen wie
dort (`reaktionen/<seite>/`), nur unter `https://lernapps.net/chemie-reaktionen/`.

Die Seiten sind ein _explainer_ von lernapps.net ([`@lernapps/app-templates`](https://github.com/lernapps/app-templates)),
Format 2: Der Inhalt steht als YAML in [`src/`](src/).

```bash
npm ci                 # Abhängigkeiten installieren (lernapps-Pakete von GitHub, auf einen Commit gepinnt)
npm run build          # _site/ bauen; bricht bei Regelverstößen ab
npm run dev            # explainer lokal ansehen
npx lernapps check     # alle Prüfungen von lernapps.net samt Browser-Tests
```

## Architektur

Die App hat keine eigene Architektur. Für jeden explainer gilt die gemeinsame Architektur von lernapps.net:
[arc42 des explainers](https://github.com/lernapps/app-templates/tree/main/explainer/docs/arc42) in
`lernapps/app-templates`, dazu die Regeln von [lernapps.net](https://lernapps.net/tooling/rules/).

Geprüft und veröffentlicht wird mit dem Werkzeug von lernapps.net, wie bei jeder App aus dem Generator:
`.github/workflows/pages.yml` führt `lernapps check` bei jedem Push und Pull Request aus, stellt jeden Pull Request
als Vorschau unter `…/chemie-reaktionen/pr-preview/pr-<Nummer>/` bereit und veröffentlicht `main` auf dem Branch `gh-pages`.

Wie man eine Seite oder ein Kapitel anlegt, steht im Inhaltsleitfaden
[`.agents/skills/app-content/`](.agents/skills/app-content/SKILL.md).

## Lizenz

[MIT](LICENSE), für den Code und die Texte in diesem Repo. Inhalte Dritter (z. B. Zitate aus Lehrplänen) behalten ihre eigene Lizenz.
