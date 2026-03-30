# SEMINARPLAN

## Der Projektordner als Wissensbasis
KI arbeitet direkt auf euren Dateien - nicht im Chatfenster daneben

- Modul: KI und Digitalisierung (3. Semester)
- Studiengang: Soziale Arbeit (B.A.) - 5 UStd. (225 Min.)
- Voraussetzung: Vibe-Coding mit Lovable (Vorsemester)
- Dozent: Christian Radden
- Stand: Maerz 2026

## 1. Leitidee

Im letzten Semester: Vibe-Coding in Lovable, ab und zu ein Text im ChatGPT-Browserfenster. Beides hatte denselben Grundmechanismus - ein Prompt rein, ein Ergebnis raus, fertig. Die KI hatte keinen Zugriff auf vorhandene Dateien. Jedes Mal bei null anfangen.

> Der Shift: Die KI arbeitet nicht mehr in einem Chatfenster neben euren Dateien. Sie arbeitet direkt IM Projektordner - liest vorhandene Dokumente, erstellt neue, und ueberarbeitet bestehende im Zusammenhang. Genau wie eine Kollegin, die Zugriff auf den gemeinsamen Projektordner hat.

Konkret: Im Codespace oeffnen die Studierenden den Copilot-Chat (oder Agent Mode), beschreiben ihren Auftrag, und die KI erstellt Dateien direkt im Ordner. Wenn sie dann sagen "Passe jetzt das Konzept an die Budgetkuerzung an und aktualisiere die Praesentation entsprechend", liest die KI die vorhandenen Dateien und aendert sie - ohne dass man irgendetwas kopieren oder hochladen muss.

Das ist die Arbeitsweise, die Claude CoWork auf dem Desktop vormacht. Im Seminar bauen wir sie kostenlos nach: mit GitHub Codespaces als Cloud-Schreibtisch und Copilot Agent Mode als KI-Assistenz, die direkt auf den Dateien arbeitet.

Die drei Fragen des Seminars:

1. Wie erkenne ich den Nutzen? Die Studierenden bauen einen Projektordner auf, der mit jeder Uebung waechst - Konzept, Praesentation, Kostentabelle, Ueberarbeitung.
2. Wie kann ich das selbst nutzen? Alles laeuft im Browser, kostenlos. GitHub-Account reicht. Fuer Fortgeschrittene: Claude Code als Option.
3. Worauf muss ich achten? Kompakter Datenschutz-Impuls mit Faustregeln fuer den Berufsalltag.

## 2. Technisches Setup: So funktioniert es

### 2.1 Was passiert im Codespace?

Der Codespace ist ein VS Code im Browser - mit einem vollstaendigen Dateisystem. Die Studierenden sehen links ihre Ordnerstruktur, in der Mitte den Editor, und rechts (oder unten) den Copilot-Chat. Wenn sie Copilot einen Auftrag geben, kann dieser:

- Neue Dateien erstellen (Markdown, aber auch Skripte, die .docx/.pptx/.xlsx erzeugen)
- Bestehende Dateien lesen und als Kontext fuer neue Auftraege nutzen
- Mehrere Dateien gleichzeitig aendern (Agent Mode)
- Terminal-Befehle ausfuehren (z. B. zum Generieren von Office-Dateien)

### 2.2 Budget: 50 Premium Requests pro Monat

Im Free Tier hat jede/r Studierende 50 Premium Requests pro Monat. Jeder Prompt im Copilot-Chat oder Agent Mode verbraucht 1 Request. Die autonomen Zwischenschritte der KI (Dateien lesen, Terminal-Befehle) zaehlen nicht.

Fuer die drei Uebungen rechnen wir mit ca. 8-15 Prompts pro Person. Das passt - aber die Studierenden sollten nicht endlos rumprobieren, sondern ihre Auftraege ueberlegt formulieren. Das ist didaktisch sogar erwuenscht: Praezise Auftragsformulierung ist eine Kernkompetenz.

> Tipp fuer den Dozenten: Kommunizieren Sie das Budget offen: "Ihr habt heute ca. 15 Versuche - das reicht, aber ueberlegt euch eure Auftraege, bevor ihr sie abschickt. Das ist wie im echten Beruf: Je klarer der Auftrag, desto besser das Ergebnis."

**Wichtig: Wenn das Free-Tier-Limit erreicht ist**, kann die zweite Person im Team das Repo pullen und im eigenen Codespace weiterarbeiten (siehe Block 3).

### 2.3 Dateiformate und Tokenkosten

Nicht alle Dateiformate sind gleich effizient fuer KI-Agenten:

| Format | Tokenkosten | KI-Lesbarkeit | Empfehlung |
|---|---|---|---|
| .md (Markdown) | Sehr niedrig | Direkt lesbar, kein Overhead | Bevorzugt |
| .txt | Sehr niedrig | Direkt lesbar | Gut |
| .docx / .pptx / .xlsx | Hoch | Muss erst konvertiert werden, viel XML-Overhead | Vermeiden |
| .pdf | Hoch | Schwer zu parsen, oft Layoutrauschen | Vermeiden |

> Faustregel: Im Projektordner bevorzugt mit .md-Dateien arbeiten. Markdown ist fuer die KI am billigsten zu lesen und zu schreiben, rendern auf GitHub automatisch schoen, und lassen sich bei Bedarf spaeter in andere Formate konvertieren. Jedes Token, das in XML-Overhead einer .docx-Datei steckt, fehlt fuer den eigentlichen Inhalt.

### 2.4 Fuer Technik-Affine: Claude Code im Terminal

Studierende, die mehr wollen, koennen Claude Code direkt im Codespace-Terminal installieren. Claude Code ist ein Kommandozeilen-Tool, das - wie CoWork - direkt auf dem Dateisystem arbeitet und dabei gezielt Claude-Modelle nutzt.

Voraussetzung: Mindestens Claude Pro (20 USD/Monat) oder die kostenlose 30-Tage-Testphase. Im Codespace-Terminal einfach:

```sh
npm install -g @anthropic-ai/claude-code
claude
```

Das ist ein optionales Angebot fuer die Neugierigen - der Hauptweg fuer alle bleibt Copilot Agent Mode.

## 3. Das durchgaengige Szenario

Alle Uebungen arbeiten am selben Projekt. Die Zweierteams bearbeiten alle vier Szenarien in einem gemeinsamen Repo:

| Szenario | Kontext |
|---|---|
| A | Streetwork-Projekt: Traeger plant neues Projekt. Stadtrat erwartet Konzept, Praesentation, Kostenuebersicht. Budget: 80.000 EUR. |
| B | Suchtpraevention: Praeventionszentrum gestaltet Elternabend zu Mediensucht. Schultraeger braucht Unterlagen. |
| C | Inklusionsprojekt: Einrichtung beantragt Foerderprogramm. Konzept, Praesentation fuer den Foerdergeber, Finanzplan. |
| D | Jahresbericht: Beratungsstelle erstellt Jahresbericht fuer Traeger. Bericht, Vorstandspraesentation, Statistik. |

### Repo-Struktur

Jedes 2er-Team eroeffnet ein eigenes GitHub-Repository mit vier Ordnern:

```
Mein-Projekt/
  A Streetwork-Projekt/
  B Suchtpraevention/
  C Inklusionsprojekt/
  D Jahresbericht/
  README.md
```

Die Teams arbeiten alle Szenarien nacheinander durch: Konzept, Praesentation, Kostentabelle - jeweils als .md-Dateien. Nach jeder fertigen Uebung wird committet und gepusht. Die Ergebnisse sind dann direkt auf GitHub in der Markdown-Ansicht sichtbar und praesentierbar.

## 4. Seminarverlauf

### Block 1: Einstieg + KI-Standortbestimmung (50 Min.)

| Zeit | Abschnitt |
|---|---|
| 0:00-0:15 | Abfragen: KI-Nutzung und Entwicklungen 2026 |

- Methode: Moderierte Abfrage im Plenum (Tafel / digitales Board)
- Inhalt: Zwei Leitfragen:

1. "Wie nutzt ihr aktuell KI im Arbeitsalltag, im Alltag?"
2. "Welche Entwicklungen in der KI seit letztem Semester bzw. in 2026 habt ihr mitbekommen? Was hat euch beeindruckt?"

Der Dozent sammelt die Antworten sichtbar und clustert:
- Alltag: ChatGPT, Copilot, Bilderzeugung, Uebersetzung, ...
- Arbeitsalltag: Berichte, Recherche, Mails, ...
- Entwicklungen 2026: Neue Modelle, Agenten, Computer Use, ...

Erwartung/Hoffnung: Nennung von OpenClaw / Clawdbot, Anthropic-Neuigkeiten, NotebookLM-Features. Falls nicht genannt, steuert der Dozent nach: "Kennt jemand Clawdbot? Was hat Anthropic in 2026 veroeffentlicht?"

Ueberleitung: "Vier dieser Themen schauen wir uns jetzt kurz genauer an - in Kleingruppen."

- Material: Tafel/Whiteboard oder digitales Board
- Didaktik: Advance Organizer. Die Abfrage aktiviert Vorwissen und macht den Wissensstand sichtbar. Die Ueberleitung zu den Kurzpraesentationen schliesst Wissenslücken gezielt.

| Zeit | Abschnitt |
|---|---|
| 0:15-0:30 | Kleingruppen: Kurzpraesentationen vorbereiten |

- Methode: Gruppenarbeit in 4 Kleingruppen (je 3-5 Personen)
- Inhalt: Jede Gruppe erhaelt ein Thema und recherchiert 10-15 Minuten (Smartphones, Laptops):

| Gruppe | Thema | Leitfrage |
|---|---|---|
| 1 | Clawdbot (OpenClaw) | Was ist Clawdbot? Was kann er? Wofuer ist er gedacht? |
| 2 | Anthropic | Wer ist Anthropic? Welche Modelle und Produkte gibt es 2026? Was ist neu? |
| 3 | Claude Code | Was ist Claude Code? Wie funktioniert es? Wie unterscheidet es sich von ChatGPT? |
| 4 | NotebookLM (neueste Features) | Was kann NotebookLM aktuell? Welche neuen Features gibt es 2026? |

Hinweis: Keine Folien noetig - 2-3 Minuten freier Vortrag mit Stichpunkten reicht.

- Material: Smartphones/Laptops fuer Recherche, Themenkarten fuer die Gruppen
- Didaktik: Peer-Teaching. Die Studierenden erschliessen sich aktuelle KI-Entwicklungen selbst und vermitteln sie. Das verankert Wissen besser als ein Dozentenvortrag.

| Zeit | Abschnitt |
|---|---|
| 0:30-0:50 | Kurzpraesentationen im Plenum |

- Methode: 4 Kurzvortraege (je 3-4 Min.) + kurze Rueckfragen
- Inhalt: Jede Gruppe stellt ihr Thema vor. Dozent ergaenzt bei Bedarf und ordnet ein:

- Nach Gruppe 1 (Clawdbot): "Agentic Tools werden immer mehr - die Frage ist: Wie steuern wir sie sinnvoll?"
- Nach Gruppe 2 (Anthropic): "Anthropic ist der Hersteller hinter Claude - und damit auch hinter Claude Code und CoWork."
- Nach Gruppe 3 (Claude Code): "Genau so arbeiten wir heute auch - nur mit Copilot Agent Mode, der aehnlich funktioniert."
- Nach Gruppe 4 (NotebookLM): "NotebookLM zeigt, was passiert, wenn KI auf einer Wissensbasis arbeitet. Unser Projektordner ist im Prinzip dasselbe."

Ueberleitung: "Jetzt melden wir uns alle bei GitHub an und legen selbst los."

- Material: Beamer fuer optionale Bildschirmfreigabe
- Didaktik: Aktivierung und gemeinsame Wissensbasis. Die Dozenten-Kommentare verbinden die Themen mit dem heutigen Seminarinhalt.

### Block 2: GitHub-Setup + Grundlagen (35 Min.)

| Zeit | Abschnitt |
|---|---|
| 0:50-1:00 | GitHub-Anmeldung fuer alle |

- Methode: Guided Onboarding am Beamer + Buddy-System
- Inhalt: Der Dozent zeigt jeden Schritt live:

1. github.com oeffnen -> Sign up
2. E-Mail, Username, Passwort vergeben
3. E-Mail-Verifizierung
4. Copilot ist im Free Tier automatisch enthalten

Buddy-System: Wer schon einen Account hat, hilft Nachbar*innen.

- Material: Beamer, Smartphones/Laptops
- Didaktik: Alle auf denselben Stand bringen. Kein Studierender bleibt zurueck.

| Zeit | Abschnitt |
|---|---|
| 1:00-1:10 | Kurzinfo: Dateiformate und Tokenkosten |

- Methode: Kurzimpuls (10 Min.)
- Inhalt: Warum arbeiten wir mit .md-Dateien?

| Format | Tokenkosten | KI-Lesbarkeit | Empfehlung |
|---|---|---|---|
| .md (Markdown) | Sehr niedrig | Direkt lesbar | Bevorzugt |
| .txt | Sehr niedrig | Direkt lesbar | Gut |
| .docx / .pptx | Hoch | Viel XML-Overhead | Vermeiden |
| .pdf | Hoch | Schwer zu parsen | Vermeiden |

Faustregel: "Jedes Token, das in XML-Overhead einer .docx-Datei steckt, fehlt fuer den eigentlichen Inhalt. Markdown ist fuer die KI am billigsten - und rendert auf GitHub automatisch schoen."

Kurze Live-Demo: Eine .md-Datei auf GitHub oeffnen -> gerenderte Ansicht zeigen.

- Material: Beamer, Beispiel-.md auf GitHub
- Didaktik: Praktisches Wissen, das sofort anwendbar ist. Begruendet die Entscheidung fuer das Dateiformat im gesamten Seminar.

| Zeit | Abschnitt |
|---|---|
| 1:10-1:25 | Live-Demo: Copilot Agent Mode auf dem Projektordner |

- Methode: Live-Demonstration am Beamer (Think-Aloud, gekuerzt)
- Inhalt: Der Dozent zeigt den Kernworkflow kompakt:

1. Codespace oeffnen, Agent Mode aktivieren
2. "Erstelle konzept.md: Streetwork-Projekt, Budget 80.000 EUR..." -> Datei entsteht im Ordner
3. "Lies konzept.md und erstelle praesentation.md" -> KI liest und baut darauf auf
4. "Budget auf 55.000 EUR gekuerzt - passe alle Dateien an" -> KI aendert konsistent

Explizit machen: "Nichts kopiert, nichts hochgeladen. Die KI arbeitet direkt auf dem Projektordner. Das macht ihr jetzt gleich selbst."

- Material: Codespace mit vorbereitetem Repo, Beamer, Fallback: Screenrecording
- Didaktik: Cognitive Apprenticeship. Kompakte Demo fokussiert auf den Aha-Moment: KI arbeitet auf bestehenden Dateien weiter.

### Pause (15 Min.)

### Block 3: Hands-on - Repo aufbauen + Szenarien erarbeiten (70 Min.)

| Zeit | Abschnitt |
|---|---|
| 1:40-1:55 | Repo eroeffnen, Ordnerstruktur anlegen, Codespace starten |

- Methode: Guided Onboarding in 2er-Teams
- Inhalt: Jedes 2er-Team erstellt ein eigenes Repository:

1. GitHub -> "+" -> New repository -> Name waehlen (z. B. "KI-Projektordner")
2. README.md anlegen (Haken setzen)
3. Im Repo: 4 Ordner anlegen (ueber "Add file" -> "Create new file" -> Ordnername + "/" + README.md):
   - `A Streetwork-Projekt/`
   - `B Suchtpraevention/`
   - `C Inklusionsprojekt/`
   - `D Jahresbericht/`
4. Codespace starten: Gruener "Code"-Button -> Codespaces -> Create codespace on main
5. Copilot-Chat oeffnen (Ctrl+Alt+I), Agent Mode aktivieren

Framing: "Ihr habt jetzt euren eigenen Projektordner mit vier Szenarien. Die KI arbeitet ab jetzt direkt darin."

- Material: Beamer, Repository-Anleitung als Handout oder im Chat
- Didaktik: Ownership durch eigenes Repo. Die Ordnerstruktur macht die vier Szenarien sichtbar und gibt Orientierung.

| Zeit | Abschnitt |
|---|---|
| 1:55-2:25 | Uebung 1+2: Konzept, Praesentation, Kosten erstellen |

- Methode: Scaffolded Practice in Zweierteams
- Inhalt: Die Teams arbeiten alle vier Szenarien durch - pro Szenario:

1. Konzept erstellen: "Erstelle im Ordner 'A Streetwork-Projekt' eine Datei Konzept.md: ..."
2. Praesentation ableiten: "Lies Konzept.md und erstelle daraus Praesentation.md: 10 Folien-Gliederung fuer den Stadtrat."
3. Kosten ableiten: "Lies Konzept und Praesentation und erstelle kosten.md: Kostentabelle mit allen Positionen."

Je nach Geschwindigkeit schaffen die Teams 2-4 Szenarien. Qualitaet vor Quantitaet: "Prueft nach jedem Schritt, ob die Dateien inhaltlich zusammenpassen."

Budget-Hinweis: Ca. 8-12 Prompts fuer diese Phase. Auftraege ueberlegt formulieren.

- Material: Beispiel-Prompts im Repo (vorlagen/beispiel-prompts.md), Szenario-Beschreibungen
- Didaktik: Aufbauendes Lernen. Jedes Szenario wiederholt den Workflow - aber mit neuem Inhalt. Die Wiederholung festigt das Muster: erstellen -> ableiten -> pruefen.

| Zeit | Abschnitt |
|---|---|
| 2:25-2:45 | Commit + Push ueben, Markdown-Ansicht auf GitHub |

- Methode: Guided Practice am Beamer + Eigenarbeit
- Inhalt: Der Dozent zeigt live:

1. Im Codespace links: Source Control (Ctrl+Shift+G)
2. Alle Aenderungen stagen: "+" neben "Changes"
3. Commit-Message schreiben (z. B. "Szenario A fertig")
4. "Commit" klicken, dann "Sync Changes" (= Push)
5. Auf github.com das Repo oeffnen -> Ordner durchklicken -> Markdown wird gerendert angezeigt

Die Teams committen und pushen ihre bisherigen Ergebnisse. Danach: Auf GitHub das eigene Repo oeffnen und die gerenderte Markdown-Ansicht bewundern.

"Das ist euer Projektordner - sichtbar fuer euch, euer Team, und wenn ihr wollt fuer die ganze Welt. Ohne Word, ohne PowerPoint. Einfach Markdown auf GitHub."

- Material: Beamer, Codespace
- Didaktik: Versionierung als Grundkompetenz. Commit/Push ist fuer viele neu - die einfache Erklaerung "Speichern und Hochladen" reicht als Einstieg. Die GitHub-Ansicht liefert den Belohnungsmoment.

| Zeit | Abschnitt |
|---|---|
| 2:45-3:00 | Free-Tier-Limit erreicht? Pull-Workflow fuer das Team |

- Methode: Erklaerung + Praxisuebung
- Inhalt: Das kostenlose Tier (50 Requests/Monat) wird wahrscheinlich bei einigen Teams zur Neige gehen. Loesung: Die zweite Person im Team uebernimmt.

Der Dozent zeigt den Workflow:

1. Person A hat committed und gepusht - alle Dateien sind auf GitHub
2. Person B oeffnet das gleiche Repository auf GitHub (Link teilen oder im eigenen Account forken)
3. Person B startet einen eigenen Codespace auf dem Repo
4. Alternativ, falls Person B Collaborator ist: Einfach "Code" -> "Codespaces" -> "Create codespace"
5. Person B hat jetzt alle Dateien und eigene 50 Requests

So verdoppelt sich das effektive Budget auf 100 Requests pro Team.

> Wichtig: Immer erst committen und pushen, bevor die andere Person uebernimmt. Sonst fehlen die neuesten Dateien.

Falls noch Requests uebrig: Uebung 3 (Aenderung einarbeiten) starten:

- Szenario A: Budget wird von 80.000 EUR auf 55.000 EUR gekuerzt.
- Szenario B: Statt eines Elternabends soll es eine ganze Projektwoche werden.
- Szenario C: Der Foerdergeber verlangt zusaetzlich eine Wirkungsmessung.
- Szenario D: Der Traeger moechte den Bericht zusaetzlich auf Englisch.

"Lies alle Dateien im Ordner [Szenario]. [Aenderung beschreiben]. Passe alle Dokumente entsprechend an."

- Material: Beamer, Aenderungs-Kaertchen
- Didaktik: Problemloesung statt Frust. Das Limit wird als Teamwork-Moment genutzt. Der Pull-Workflow vermittelt nebenbei eine zentrale Git-Kompetenz.

### Block 4: Reflexion + Ergebnissicherung (25 Min.)

| Zeit | Abschnitt |
|---|---|
| 3:00-3:15 | Gallery Walk + Plenumsdiskussion |

- Methode: Gallery Walk mit Feedback-Zetteln + Diskussion
- Inhalt:

Gallery Walk (8 Min.): Die Teams zeigen ihre Repos auf GitHub (gerenderte Markdown-Ansicht). Alle gehen durch:

- Gruen: Wuerde ich so in der Praxis nutzen.
- Rot: Hier hat die KI danebengegriffen.

Plenumsdiskussion (7 Min.): Dozent sammelt die Rot-Punkte:

- Wo waren die Dokumente inhaltlich falsch?
- Wurden die Aenderungen konsistent ueber alle Dateien uebernommen?
- Was bedeutet das fuer eure Qualitaetskontrolle im Beruf?

"Die KI ist schnell, aber nicht fehlerfrei. Euer Fachwissen bleibt die Qualitaetskontrolle."

- Material: Post-Its in Gruen und Rot, Timer
- Didaktik: Assessment as Learning. Peer-Feedback auf konkrete Arbeitsergebnisse. Die GitHub-Ansicht macht die Ergebnisse teilbar und sichtbar.

| Zeit | Abschnitt |
|---|---|
| 3:15-3:25 | Datenschutz-Impuls: pragmatische Faustregeln |

- Methode: Kurzimpuls (10 Min.)
- Inhalt: Fuenf Faustregeln:

1. Keine echten Namen, Geburtsdaten, Aktenzeichen eingeben.
2. Immer mit fiktiven Faellen oder anonymisierten Daten arbeiten.
3. Im Zweifel beim Traeger nachfragen - viele haben noch keine KI-Richtlinie.
4. Copilot Free / Claude Free koennen Eingaben fuers Training nutzen. Fuer sensible Inhalte: kostenpflichtige Plaene mit Opt-out.
5. Postkarten-Regel: "Wuerde ich das auf einer Postkarte schreiben? Nein? Dann nicht in die KI."

- Material: 2-3 Folien, optional ein Einseiter als Handout
- Didaktik: Pragmatisch statt juristisch. Postkarten-Regel als leicht merkbare Faustregel.

### Block 5: GitHub Student Account + Abschluss (20 Min.)

| Zeit | Abschnitt |
|---|---|
| 3:25-3:35 | GitHub Student Developer Pack beantragen |

- Methode: Guided Onboarding am Beamer
- Inhalt: Der Dozent zeigt den Antragsprozess:

1. education.github.com/pack oeffnen
2. "Get your pack" klicken
3. Mit dem soeben erstellten GitHub-Account einloggen
4. Hochschul-E-Mail-Adresse angeben (oder Immatrikulationsbescheinigung hochladen)
5. Kurze Begruendung: "Student of Social Work, using GitHub for coursework"
6. Absenden - Freischaltung dauert meist wenige Tage

Was bringt der Student Account?

- GitHub Pro (kostenlos): Unlimitierte private Repos, mehr Codespace-Stunden
- Copilot Pro (kostenlos fuer Studierende): 300 statt 50 Premium Requests/Monat
- Weitere Tools: Domains, Cloud-Credits, Lernressourcen

"Damit habt ihr ab naechster Woche 300 Requests pro Monat - genug fuer das ganze Semester."

- Material: Beamer, education.github.com/pack
- Didaktik: Nachhaltigkeit. Der Student Account macht den Workflow ueber das Seminar hinaus nutzbar. Die Beantragung im Seminar stellt sicher, dass es wirklich passiert.

| Zeit | Abschnitt |
|---|---|
| 3:35-3:45 | Abschluss: One-Minute-Paper + Ausblick |

- Methode: One-Minute-Paper + Kurzvortrag + Blitzlicht
- Inhalt:

One-Minute-Paper (3 Min.):

1. Was war meine wichtigste Erkenntnis heute?
2. Welches Dokument werde ich als naechstes mit KI erstellen?

Ausblick (5 Min.):

- Fuer die Abschlussarbeit: Gliederung, Expose, Literatur-Uebersichten - alles im Projektordner
- Upgrade-Optionen: Claude Pro (20 USD/Monat fuer Claude Code), 30-Tage-Testphasen
- Fuer Technik-Affine: Claude Code im Terminal als Einstieg in professionelles agentic working
- Ressourcen: Anthropic Academy, Claude-Doku, GitHub Skills

Abschluss-Blitzlicht (2 Min.):

"Was veraendert sich, wenn die KI nicht nur einzelne Texte schreibt, sondern auf eurem ganzen Projektordner weiterarbeitet?"

- Material: Papier/digitales Formular, Ressourcen-Link-Sammlung im Repo
- Didaktik: Transfer-Sicherung. Frage 2 erzwingt konkreten Transfer. Abschluss-Blitzlicht greift die Eroeffnung auf.

## 5. Zeitplan auf einen Blick

| Zeit | Inhalt | Methode | Sozialform |
|---|---|---|---|
| 0:00-0:15 | Abfragen: KI-Nutzung + Entwicklungen 2026 | Moderierte Abfrage | Plenum |
| 0:15-0:30 | Kurzpraesentationen vorbereiten | Gruppenarbeit | 4 Kleingruppen |
| 0:30-0:50 | Kurzpraesentationen: Clawdbot, Anthropic, Claude Code, NotebookLM | Peer-Teaching | Plenum |
| 0:50-1:00 | GitHub-Anmeldung fuer alle | Guided Onboarding | Einzeln + Buddies |
| 1:00-1:10 | Dateiformate und Tokenkosten | Kurzimpuls | Plenum |
| 1:10-1:25 | Live-Demo: Copilot Agent Mode | Live-Demo | Plenum |
| 1:25-1:40 | Pause |  | - |
| 1:40-1:55 | Repo eroeffnen, 4 Ordner, Codespace starten | Guided Onboarding | Zweierteams |
| 1:55-2:25 | Uebung 1+2: Konzept, Praesentation, Kosten | Scaffolded Practice | Zweierteams |
| 2:25-2:45 | Commit + Push ueben, Markdown auf GitHub | Guided Practice | Zweierteams |
| 2:45-3:00 | Pull-Workflow bei Free-Tier-Limit + Uebung 3 | Problembasiert | Zweierteams |
| 3:00-3:15 | Gallery Walk + Diskussion | Peer-Feedback | Alle |
| 3:15-3:25 | Datenschutz-Impuls | Kurzimpuls | Plenum |
| 3:25-3:35 | GitHub Student Developer Pack beantragen | Guided Onboarding | Einzeln |
| 3:35-3:45 | Abschluss + Ausblick | OMP + Blitzlicht | Einzeln -> Plenum |

Hands-on-Anteil: ca. 120 Min. (~53 Prozent). Gesamtes Budget pro Person: ca. 8-15 von 50 Premium Requests (effektiv 100 pro Team durch Pull-Workflow).

## 6. Der Projektordner waechst

| Phase | Aktion | KI liest... | KI erstellt... |
|---|---|---|---|
| Uebung 1 | Konzept erstellen | - (Auftrag reicht) | konzept.md |
| Uebung 2a | Praesentation ableiten | konzept.md | praesentation.md |
| Uebung 2b | Kosten ableiten | konzept.md + praesentation.md | kosten.md |
| Uebung 3 | Aenderung einarbeiten | Alle 3 Dateien | konzept-v2.md, praesentation-v2.md, kosten-v2.md |

> Kernbotschaft: Die KI arbeitet nicht im Chatfenster neben euren Dateien - sie arbeitet direkt auf dem Projektordner. Je mehr Kontext im Ordner liegt, desto besser werden die Ergebnisse. Und genau das spart die Zeit, die Fachkraefte am Menschen verbringen koennen.