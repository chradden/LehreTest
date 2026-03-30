# Der Projektordner als Wissensbasis
## KI arbeitet direkt auf euren Dateien

Modul: KI und Digitalisierung (3. Semester) | Soziale Arbeit (B.A.) | 5 UStd.

Dozent: Christian Radden | Stand: Maerz 2026

---

## Folie 1 - Einstieg: Wo steht ihr?

**Zwei Fragen an euch:**

1. Wie nutzt ihr aktuell KI im Arbeitsalltag, im Alltag?
2. Welche Entwicklungen in der KI seit letztem Semester bzw. in 2026 habt ihr mitbekommen? Was hat euch beeindruckt?

Sammlung an der Tafel / digitalem Board

---

## Folie 2 - Kurzpraesentationen: 4 Themen, 4 Gruppen

| Gruppe | Thema | Leitfrage |
|---|---|---|
| 1 | Clawdbot (OpenClaw) | Was ist Clawdbot? Was kann er? |
| 2 | Anthropic | Wer ist Anthropic? Modelle und Produkte 2026? |
| 3 | Claude CoWork | Was ist Claude CoWork? Unterschied zu ChatGPT? |
| 4 | NotebookLM | Neueste Features 2026? |

- 10-15 Min. Recherche in Kleingruppen
- Je 3-4 Min. Kurzvortrag im Plenum

---

## Folie 3 - Der Shift: Vom Chatfenster zum Projektordner

**Letztes Semester:**
- Prompt rein -> Ergebnis raus -> Kopieren -> Fertig
- KI hatte keinen Zugriff auf eure Dateien

**Heute:**
- KI arbeitet direkt IM Projektordner
- Liest vorhandene Dokumente
- Erstellt neue Dateien im Zusammenhang
- Aendert mehrere Dateien gleichzeitig

> Wie eine Kollegin, die Zugriff auf den gemeinsamen Projektordner hat.

---

## Folie 4 - Die Werkzeuge

| Tool | Funktion |
|---|---|
| GitHub | Projektordner in der Cloud |
| Codespace | VS Code im Browser (kostenlos) |
| Copilot Agent Mode | KI-Assistenz direkt auf den Dateien |
| Markdown (.md) | Bevorzugtes Dateiformat |

- Alles laeuft im Browser
- GitHub Free Account reicht
- 50 Premium Requests / Monat (100 pro Team)

---

## Folie 5 - Warum Markdown?

| Format | Tokenkosten | KI-Lesbarkeit | Empfehlung |
|---|---|---|---|
| .md | Sehr niedrig | Direkt lesbar | **Bevorzugt** |
| .txt | Sehr niedrig | Direkt lesbar | Gut |
| .docx / .pptx | Hoch | Viel XML-Overhead | Vermeiden |
| .pdf | Hoch | Schwer zu parsen | Vermeiden |

> Jedes Token im XML-Overhead einer .docx fehlt fuer den eigentlichen Inhalt.

Markdown rendert auf GitHub automatisch schoen - ohne Word, ohne PowerPoint.

---

## Folie 6 - Die vier Szenarien

Jedes 2er-Team bearbeitet alle vier Szenarien in einem eigenen Repo:

| Szenario | Kontext |
|---|---|
| A | Streetwork-Projekt (Budget 80.000 EUR, Stadtrat) |
| B | Suchtpraevention (Elternabend Mediensucht, Schultraeger) |
| C | Inklusionsprojekt (Foerderprogramm, Foerdergeber) |
| D | Jahresbericht (Beratungsstelle, Traegervorstand) |

```
Mein-Projekt/
  A Streetwork-Projekt/
  B Suchtpraevention/
  C Inklusionsprojekt/
  D Jahresbericht/
  README.md
```

---

## Folie 7 - Live-Demo: So funktioniert der Workflow

**Phase 1 - Erstellen:**
1. "Erstelle Konzept.md: Streetwork-Projekt, Budget 80.000 EUR..."
2. "Lies Konzept.md und erstelle Praesentation.md: 10 Folien fuer den Stadtrat"
3. "Lies Konzept und Praesentation, erstelle kosten.md"

**Phase 2 - Weiterarbeiten (der Aha-Moment):**
4. "Budget auf 55.000 EUR gekuerzt - passe alle Dateien an"

> Nichts kopiert, nichts hochgeladen. Die KI liest den Ordner und aendert alles konsistent.

---

## Folie 8 - Euer Workflow heute

```
Konzept.md  -->  Praesentation.md  -->  kosten.md
     \                |                    /
      \               |                   /
       v              v                  v
    Aenderung einarbeiten -> v2-Dateien
```

| Phase | KI liest... | KI erstellt... |
|---|---|---|
| Konzept | - (Auftrag reicht) | Konzept.md |
| Praesentation | Konzept.md | Praesentation.md |
| Kosten | Konzept + Praesentation | kosten.md |
| Aenderung | Alle 3 Dateien | v2-Versionen |

---

## Folie 9 - GitHub-Basics: Repo, Commit, Push

**Repo erstellen:**
1. GitHub -> "+" -> New repository
2. 4 Ordner anlegen (A-D)
3. Codespace starten

**Speichern und teilen:**
1. Source Control (Ctrl+Shift+G)
2. Aenderungen stagen (+)
3. Commit-Message schreiben
4. "Sync Changes" (= Push)

Ergebnis: Gerenderte Markdown-Ansicht auf GitHub

---

## Folie 10 - Free-Tier-Limit? Pull-Workflow!

**Problem:** 50 Requests aufgebraucht?

**Loesung:** Teamwork!

1. Person A committet und pusht
2. Person B oeffnet das Repo auf GitHub
3. Person B startet eigenen Codespace
4. Person B hat eigene 50 Requests

> Immer erst committen + pushen, bevor die andere Person uebernimmt!

Effektives Budget: **100 Requests pro Team**

---

## Folie 11 - Datenschutz: 5 Faustregeln

1. **Keine echten Namen**, Geburtsdaten, Aktenzeichen eingeben
2. Immer mit **fiktiven Faellen** oder anonymisierten Daten arbeiten
3. Im Zweifel **beim Traeger nachfragen**
4. Free-Tier kann Eingaben fuers Training nutzen - fuer Sensibles: **kostenpflichtige Plaene**
5. **Postkarten-Regel:** "Wuerde ich das auf einer Postkarte schreiben? Nein? Dann nicht in die KI."

---

## Folie 12 - GitHub Student Developer Pack

**So geht's:**
1. education.github.com/pack oeffnen
2. "Get your pack" klicken
3. Hochschul-E-Mail oder Immatrikulationsbescheinigung
4. Begruendung: "Student of Social Work, using GitHub for coursework"

**Das bekommt ihr:**
- GitHub Pro (kostenlos)
- **Copilot Pro: 300 statt 50 Requests/Monat**
- Mehr Codespace-Stunden
- Cloud-Credits, Domains, Lernressourcen

---

## Folie 13 - Zeitplan auf einen Blick

| Zeit | Was passiert? |
|---|---|
| 0:00-0:15 | Abfragen: KI-Nutzung + Entwicklungen 2026 |
| 0:15-0:50 | Kurzpraesentationen (Clawdbot, Anthropic, Claude CoWork, NotebookLM) |
| 0:50-1:10 | GitHub-Anmeldung + Dateiformate/Tokenkosten |
| 1:10-1:25 | Live-Demo: Copilot Agent Mode |
| 1:25-1:40 | **Pause** |
| 1:40-1:55 | Repo + 4 Ordner + Codespace starten |
| 1:55-2:25 | Uebung: Konzept, Praesentation, Kosten erstellen |
| 2:25-2:45 | Commit + Push ueben |
| 2:45-3:00 | Pull-Workflow + ggf. Uebung 3 |
| 3:00-3:15 | Gallery Walk + Diskussion |
| 3:15-3:25 | Datenschutz-Impuls |
| 3:25-3:35 | GitHub Student Pack beantragen |
| 3:35-3:45 | Abschluss + Ausblick |

---

## Folie 14 - Was ihr heute mitnehmt

- Euer eigenes GitHub-Repo mit Projektdokumenten
- Den Workflow: Konzept -> Praesentation -> Kosten -> Aenderung
- Git-Grundlagen: Commit, Push, Pull
- Dateiformate: Warum Markdown die beste Wahl ist
- GitHub Student Pack fuer 300 Requests/Monat
- 5 Datenschutz-Faustregeln fuer den Berufsalltag

> **Kernbotschaft:** Die KI arbeitet nicht im Chatfenster neben euren Dateien - sie arbeitet direkt auf dem Projektordner. Das spart die Zeit, die Fachkraefte am Menschen verbringen koennen.

---

## Folie 15 - One-Minute-Paper

**Zwei Fragen zum Mitnehmen:**

1. Was war meine wichtigste Erkenntnis heute?
2. Welches Dokument werde ich als naechstes mit KI erstellen?

**Ausblick:**
- Abschlussarbeit: Gliederung, Expose, Literatur - alles im Projektordner
- Claude Code im Terminal fuer Technik-Affine
- Ressourcen: Anthropic Academy, Claude-Doku, GitHub Skills

**Abschluss-Blitzlicht:**
"Was veraendert sich, wenn die KI nicht nur einzelne Texte schreibt, sondern auf eurem ganzen Projektordner weiterarbeitet?"
