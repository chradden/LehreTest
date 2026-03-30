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

### 2.3 Fuer Technik-Affine: Claude Code im Terminal

Studierende, die mehr wollen, koennen Claude Code direkt im Codespace-Terminal installieren. Claude Code ist ein Kommandozeilen-Tool, das - wie CoWork - direkt auf dem Dateisystem arbeitet und dabei gezielt Claude-Modelle nutzt.

Voraussetzung: Mindestens Claude Pro (20 USD/Monat) oder die kostenlose 30-Tage-Testphase. Im Codespace-Terminal einfach:

```sh
npm install -g @anthropic-ai/claude-code
claude
```

Das ist ein optionales Angebot fuer die Neugierigen - der Hauptweg fuer alle bleibt Copilot Agent Mode.

## 3. Das durchgaengige Szenario

Alle Uebungen arbeiten am selben Projekt. Die Zweierteams waehlen zu Beginn:

| Szenario | Kontext |
|---|---|
| A | Streetwork-Projekt: Traeger plant neues Projekt. Stadtrat erwartet Konzept, Praesentation, Kostenuebersicht. Budget: 80.000 EUR. |
| B | Suchtpraevention: Praeventionszentrum gestaltet Elternabend zu Mediensucht. Schultraeger braucht Unterlagen. |
| C | Inklusionsprojekt: Einrichtung beantragt Foerderprogramm. Konzept, Praesentation fuer den Foerdergeber, Finanzplan. |
| D | Jahresbericht: Beratungsstelle erstellt Jahresbericht fuer Traeger. Bericht, Vorstandspraesentation, Statistik. |

## 4. Seminarverlauf

### Block 1: Einstieg + Demo (40 Min.)

| Zeit | Abschnitt |
|---|---|
| 0:00-0:10 | Blitzlicht: "Wo nervt Dokumentation am meisten?" |

- Methode: Blitzlicht-Runde
- Inhalt: Jede/r antwortet in einem Satz. Dozent sammelt sichtbar an der Tafel. Typische Antworten: Hilfeplaene, Berichte fuer den Traeger, Foerderantraege, Praesentationen. Ueberleitung: "Genau darum geht es heute. Und zwar nicht so, dass ihr einen Text im ChatGPT-Fenster erzeugt und dann rueberkopiert - sondern so, dass die KI direkt in eurem Projektordner arbeitet. Sie liest, was schon da ist, und baut darauf auf."
- Material: Tafel/Whiteboard
- Didaktik: Advance Organizer. Der Schmerzpunkt Dokumentation motiviert. Die Ueberleitung macht den entscheidenden Unterschied sofort klar: nicht Copy-Paste, sondern direkte Arbeit auf Dateien.

| Zeit | Abschnitt |
|---|---|
| 0:10-0:40 | Live-Demo: Copilot Agent Mode auf dem Projektordner |

- Methode: Live-Demonstration am Beamer (Think-Aloud)
- Inhalt:

Phase 1 - Erstellen:

1. Im Copilot-Chat (Agent Mode): "Erstelle in meinem Ordner /projekt eine Datei konzept.md: Ein Konzeptpapier fuer ein Streetwork-Projekt im Stadtteil Nord. Zielgruppe: Jugendliche 14-18, Traeger: AWO, Budget: 80.000 EUR/Jahr. Gliederung: Ausgangslage, Ziele, Massnahmen, Personal, Zeitplan, Kosten."
2. Copilot erstellt konzept.md direkt im Ordner. Sichtbar im Dateibaum links.
3. "Lies das Konzept in /projekt/konzept.md und erstelle daraus /projekt/praesentation.md: Eine Kurzpraesentation (10 Folien-Gliederung) fuer den Stadtrat."
4. Copilot liest das Konzept, erstellt die Praesentation. Inhalte sind konsistent.
5. "Lies Konzept und Praesentation und erstelle /projekt/kosten.md: Eine Kostentabelle mit allen im Konzept genannten Positionen."
6. Der Ordner hat jetzt drei zusammenhaengende Dateien.

Phase 2 - Weiterarbeiten (der Aha-Moment):

1. "Das Budget wurde auf 55.000 EUR gekuerzt. Lies alle drei Dateien in /projekt/ und passe sie entsprechend an. Kuerze Massnahmen, aktualisiere Praesentation und Kostentabelle."
2. Copilot aendert alle drei Dateien. Der Dozent zeigt den Diff.

Explizit machen:

"Schaut: Ich habe nichts kopiert, nichts hochgeladen. Die KI hat den Ordner gelesen und alle Dateien konsistent geaendert. Genau so funktioniert Claude CoWork auf dem Desktop - und genau das koennt ihr hier kostenlos machen."

- Material: Codespace mit vorbereitetem Repo, Copilot (Dozent: mindestens Free, besser Pro fuer zuverlaessigere Ergebnisse), Beamer, Fallback: Screenrecording der Demo
- Didaktik: Cognitive Apprenticeship. Think-Aloud macht den Denkprozess beim Formulieren sichtbar. Phase 2 ist der Schluesselmoment - die Studierenden sehen, dass Weiterarbeiten auf bestehenden Dateien funktioniert. Der explizite Vergleich zu ChatGPT-Copy-Paste verankert den Shift.

### Block 2: Hands-on I - Projektordner aufbauen (50 Min.)

| Zeit | Abschnitt |
|---|---|
| 0:40-0:55 | Setup: Codespace starten + Copilot aktivieren |

- Methode: Guided Onboarding + Buddy-System
- Inhalt: Der Dozent zeigt jeden Schritt live am Beamer:

1. Repository-Link oeffnen (QR-Code / Chat)
2. Gruener Code-Button -> Codespaces -> Create codespace on main
3. Warten (1-2 Min.) bis VS Code im Browser geladen ist
4. Copilot-Chat oeffnen: Klick auf das Copilot-Symbol in der Seitenleiste (oder Ctrl+Alt+I)
5. Agent Mode aktivieren: Im Chat-Dropdown Agent statt Ask oder Edit waehlen

Buddy-System: Technik-affine Studis helfen Nachbar*innen.

Framing: "Links seht ihr euren Projektordner. Rechts den Copilot-Chat. Wenn ihr dem Chat einen Auftrag gebt, erstellt er Dateien direkt in eurem Ordner - ihr seht sie sofort links erscheinen."

Szenariowahl: Jedes Zweierteam waehlt Szenario A, B, C oder D.

- Material: Repository-Link / QR-Code, GitHub-Accounts (vorab angelegt), Szenario-Kaertchen
- Didaktik: Peer-Instruction durch Buddy-System. Entscheidend: Den Codespace als Projektordner mit eingebauter KI framen - nicht als Programmierumgebung. Die Szenariowahl gibt Ownership.

| Zeit | Abschnitt |
|---|---|
| 0:55-1:25 | Uebung 1: Konzeptpapier erstellen lassen |

- Methode: Scaffolded Practice in Zweierteams
- Inhalt: Aufgabe: Gebt Copilot (Agent Mode) den Auftrag, ein Konzeptpapier als Markdown-Datei in eurem Projektordner zu erstellen.

Beispiel-Prompt (auf dem Handout / im Repo):

"Erstelle in /projekt/ eine Datei konzept.md: Ein Konzeptpapier fuer [Szenario]. Gliederung: Ausgangslage, Ziele, Zielgruppe, Massnahmen, Personalplan, Zeitplan, Kostenrahmen. Umfang: ca. 2-3 Seiten."

Die Studierenden duerfen den Prompt anpassen und ergaenzen. Je konkreter der Auftrag, desto besser das Ergebnis. Wenn Copilot fragt, ob er die Datei erstellen darf: Accept klicken.

Nach dem Erstellen: Datei oeffnen, lesen, stichprobenartig pruefen.

Kurzer Zwischenstopp (3 Min.): 2-3 Teams zeigen ihr Ergebnis am Beamer.

Dozent: "Gut - ihr habt jetzt eine Datei im Ordner. Gleich zeige ich euch, was passiert, wenn die KI auf dieser Datei weiterarbeitet."

Budget-Hinweis: Ca. 2-3 Prompts fuer diese Uebung einplanen.

- Material: Beispiel-Prompt im Repo (vorlagen/beispiel-prompts.md), Szenario-Kaertchen mit Hintergrund-Infos, Copilot Free (Agent Mode)
- Didaktik: Scaffolding durch Beispiel-Prompt. Die Studierenden sehen die Struktur eines guten Auftrags, koennen aber frei anpassen. Der Zwischenstopp normalisiert unterschiedliche Geschwindigkeiten.

### Pause (15 Min.)

### Block 3: Hands-on II - Ableiten + Weiterarbeiten (55 Min.)

| Zeit | Abschnitt |
|---|---|
| 1:40-2:10 | Uebung 2: Praesentation + Kostentabelle aus dem Konzept ableiten |

- Methode: Aufbauende Praxisuebung in Zweierteams
- Inhalt: Jetzt kommt der entscheidende Schritt - die KI arbeitet auf der vorhandenen Datei weiter:

Schritt 1 - Praesentation:

"Lies /projekt/konzept.md und erstelle daraus /projekt/praesentation.md: Eine Kurzpraesentation (8-10 Folien als Gliederung mit Stichpunkten) fuer [Stadtrat / Schulleitung / Foerdergeber / Traegervorstand]."

Schritt 2 - Kostentabelle:

"Lies /projekt/konzept.md und /projekt/praesentation.md und erstelle /projekt/kosten.md: Eine Kostentabelle im Markdown-Format mit allen genannten Positionen, Einzelpreisen und Gesamtsumme."

Wichtiger Dozenten-Hinweis an die Studierenden:

"Schaut euch an, ob die Praesentation wirklich zum Konzept passt. Stimmen die Zahlen in der Kostentabelle mit dem Konzept ueberein? Das ist eure Qualitaetskontrolle."

Budget-Hinweis: Ca. 3-5 Prompts fuer diese Uebung.

- Material: Konzept aus Uebung 1 (liegt im Ordner), Copilot (Agent Mode), Beispiel-Prompts im Repo
- Didaktik: Aufbauendes Lernen. Hier wird der Shift erlebbar. Die Studierenden muessen nichts kopieren - sie verweisen einfach auf die Datei, und die KI liest sie. Der Qualitaetscheck schult die kritische Bewertungskompetenz.

| Zeit | Abschnitt |
|---|---|
| 2:10-2:35 | Uebung 3: Aenderung einarbeiten - der Stresstest |

- Methode: Problembasierte Uebung in Zweierteams
- Inhalt: Eine realistische Aenderung kommt rein (Dozent verteilt Aenderungs-Kaertchen):

- Szenario A: Budget wird von 80.000 EUR auf 55.000 EUR gekuerzt.
- Szenario B: Statt eines Elternabends soll es eine ganze Projektwoche werden.
- Szenario C: Der Foerdergeber verlangt zusaetzlich eine Wirkungsmessung.
- Szenario D: Der Traeger moechte den Bericht zusaetzlich auf Englisch.

Aufgabe: Ein einziger Prompt, der alles aktualisiert:

"Lies alle Dateien in /projekt/. [Die Aenderung beschreiben]. Passe alle drei Dokumente entsprechend an und speichere sie als konzept-v2.md, praesentation-v2.md und kosten-v2.md."

Reflexionsfrage (auf dem Kaertchen): "Wie lange haettet ihr dafuer ohne KI gebraucht?"

Budget-Hinweis: Ca. 2-4 Prompts fuer diese Uebung.

- Material: Aenderungs-Kaertchen (pro Szenario), Projektordner mit 3 Dateien aus Uebung 1+2, Copilot (Agent Mode)
- Didaktik: Problembasiertes Lernen. Die Aenderung ist realistisch - Budgetkuerzungen und Scope-Aenderungen sind Alltag. Hier wird der Ordner-Vorteil am deutlichsten: Ein Prompt aendert alle Dateien konsistent. Die Reflexionsfrage macht den Zeitgewinn bewusst.

### Block 4: Reflexion + Ergebnissicherung (35 Min.)

| Zeit | Abschnitt |
|---|---|
| 2:35-2:55 | Gallery Walk + Plenumsdiskussion |

- Methode: Gallery Walk mit Feedback-Zetteln + Diskussion
- Inhalt:

Gallery Walk (10 Min.): Die Teams zeigen ihre Projektordner (6 Dateien) am Bildschirm. Alle gehen durch:

- Gruen: Wuerde ich so in der Praxis nutzen.
- Rot: Hier hat die KI danebengegriffen.

Plenumsdiskussion (10 Min.): Dozent sammelt die Rot-Punkte:

- Wo waren die Dokumente inhaltlich falsch?
- Wurden die Aenderungen konsistent ueber alle Dateien uebernommen?
- Was bedeutet das fuer eure Qualitaetskontrolle im Beruf?

"Die KI ist schnell, aber nicht fehlerfrei. Euer Fachwissen bleibt die Qualitaetskontrolle."

- Material: Post-Its in Gruen und Rot, Timer
- Didaktik: Assessment as Learning. Peer-Feedback auf konkrete Arbeitsergebnisse. Die Rot-Punkte liefern Material fuer die Diskussion ueber Grenzen.

| Zeit | Abschnitt |
|---|---|
| 2:55-3:10 | Think-Pair-Share: Wo spart mir das Zeit - und wofuer? |

- Methode: Think-Pair-Share
- Inhalt:

Think (2 Min.): "In welcher Situation meiner Arbeit wuerde mir ein Projektordner-Workflow am meisten helfen?"

Pair (3 Min.): Austausch zu zweit.

Share (10 Min.): Sammlung im Plenum. Dozent clustert:

- Dokumentation: Hilfeplaene, Berichte, Konzepte, Stellungnahmen
- Kommunikation: Praesentationen, Elternbriefe, Antraege
- Auswertung: Statistiken, Jahresberichte, Foerdernachweise

Abschlussfrage: "Wenn KI euch 3 Stunden Dokumentation pro Woche abnimmt - was macht ihr mit der gewonnenen Zeit?"

Erwartete Pointe: Mehr Zeit am Menschen.

- Material: ggf. digitales Board
- Didaktik: Praxistransfer. Die Abschlussfrage verdichtet die Kernbotschaft des Seminars.

### Block 5: Datenschutz + Abschluss (20 Min.)

| Zeit | Abschnitt |
|---|---|
| 3:10-3:20 | Impuls: Datenschutz - pragmatische Faustregeln |

- Methode: Kurzimpuls (10 Min.)
- Inhalt: Fuenf Faustregeln:

1. Keine echten Namen, Geburtsdaten, Aktenzeichen eingeben.
2. Immer mit fiktiven Faellen oder anonymisierten Daten arbeiten.
3. Im Zweifel beim Traeger nachfragen - viele haben noch keine KI-Richtlinie.
4. Copilot Free / Claude Free koennen Eingaben fuers Training nutzen. Fuer sensible Inhalte: kostenpflichtige Plaene mit Opt-out.
5. Postkarten-Regel: "Wuerde ich das auf einer Postkarte schreiben? Nein? Dann nicht in die KI."

- Material: 2-3 Folien, optional ein Einseiter als Handout
- Didaktik: Pragmatisch statt juristisch. Postkarten-Regel als leicht merkbare Faustregel.

| Zeit | Abschnitt |
|---|---|
| 3:20-3:45 | Abschluss: One-Minute-Paper + Ausblick |

- Methode: One-Minute-Paper + Kurzvortrag + Blitzlicht
- Inhalt:

One-Minute-Paper (5 Min.):

1. Was war meine wichtigste Erkenntnis heute?
2. Welches Dokument werde ich als naechstes mit KI erstellen?

Ausblick (10 Min.):

- Fuer die Abschlussarbeit: Gliederung, Expose, Literatur-Uebersichten - alles im Projektordner
- Kostenlose Tools: GitHub Codespaces + Copilot Free (reicht fuer Studium)
- Upgrade-Optionen: Copilot Pro (10 USD/Monat, 300 Requests), Claude Pro (20 USD/Monat fuer Claude Code), 30-Tage-Testphasen
- Fuer Technik-Affine: Claude Code im Terminal als Einstieg in professionelles agentic working
- Ressourcen: Anthropic Academy, Claude-Doku, GitHub Skills
- Ueberleitung: Von individueller KI-Assistenz zu organisationalen Arbeitsstrukturen

Abschluss-Blitzlicht (5 Min.):

"Was veraendert sich, wenn die KI nicht nur einzelne Texte schreibt, sondern auf eurem ganzen Projektordner weiterarbeitet?"

- Material: Papier/digitales Formular, Ressourcen-Link-Sammlung im Repo
- Didaktik: Transfer-Sicherung. Frage 2 erzwingt konkreten Transfer. Abschluss-Blitzlicht greift die Eroeffnung auf.

## 5. Zeitplan auf einen Blick

| Zeit | Inhalt | Methode | Sozialform |
|---|---|---|---|
| 0:00-0:10 | Blitzlicht: Dokumentation | Blitzlicht | Plenum |
| 0:10-0:40 | Demo: Copilot Agent Mode | Live-Demo | Plenum |
| 0:40-0:55 | Setup + Szenariowahl | Guided Onboarding | Einzeln + Buddies |
| 0:55-1:25 | Uebung 1: Konzept erstellen | Scaffolded Practice | Zweierteams |
| 1:25-1:40 | Pause |  | - |
| 1:40-2:10 | Uebung 2: Ableiten (PPTX + XLSX) | Aufbauuebung | Zweierteams |
| 2:10-2:35 | Uebung 3: Aenderung einarbeiten | Problembasiert | Zweierteams |
| 2:35-2:55 | Gallery Walk + Diskussion | Peer-Feedback | Alle |
| 2:55-3:10 | Think-Pair-Share: Transfer | Reflexion | Paare -> Plenum |
| 3:10-3:20 | Datenschutz-Impuls | Kurzimpuls | Plenum |
| 3:20-3:45 | Abschluss + Ausblick | OMP + Blitzlicht | Einzeln -> Plenum |

Gruen hinterlegt = Hands-on (ca. 120 Min. ~= 53 Prozent). Gesamtes Budget pro Person: ca. 8-15 von 50 Premium Requests.

## 6. Der Projektordner waechst

| Phase | Aktion | KI liest... | KI erstellt... |
|---|---|---|---|
| Uebung 1 | Konzept erstellen | - (Auftrag reicht) | konzept.md |
| Uebung 2a | Praesentation ableiten | konzept.md | praesentation.md |
| Uebung 2b | Kosten ableiten | konzept.md + praesentation.md | kosten.md |
| Uebung 3 | Aenderung einarbeiten | Alle 3 Dateien | konzept-v2.md, praesentation-v2.md, kosten-v2.md |

> Kernbotschaft: Die KI arbeitet nicht im Chatfenster neben euren Dateien - sie arbeitet direkt auf dem Projektordner. Je mehr Kontext im Ordner liegt, desto besser werden die Ergebnisse. Und genau das spart die Zeit, die Fachkraefte am Menschen verbringen koennen.