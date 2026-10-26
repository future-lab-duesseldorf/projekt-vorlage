# Arbeitsablauf – so arbeiten wir in diesem Repository

Diese Anleitung ist für Einsteigerinnen und Einsteiger geschrieben. Ihr braucht **GitHub Desktop** und **VS Code** (siehe Starter-Leitfaden). Wer lieber die Kommandozeile benutzt, findet die Befehle jeweils darunter.

---

## Die drei Regeln

1. **Nie direkt auf `main` arbeiten.** `main` ist die „saubere“ Fassung. Jede Änderung entsteht auf einem eigenen **Branch** (Arbeitszweig).
2. **Jede Änderung kommt per Pull Request.** Ein Teammitglied schaut drüber (**Review**), bevor sie übernommen wird.
3. **Erst selbst denken – dann KI nutzen.** Wenn KI geholfen hat, steht es im Pull Request.

---

## Einmalig: das Repository auf den eigenen Rechner holen

1. GitHub Desktop öffnen.
2. **File → Clone repository** wählen.
3. Im Reiter **GitHub.com** dieses Repository auswählen.
4. Bei **Local path** einen Ordner wählen, den ihr wiederfindet, z. B. `Dokumente\GitHub`.
5. **Clone** klicken.
6. **Open in Visual Studio Code** klicken.

Kommandozeile:
```
git clone https://github.com/future-lab-duesseldorf/REPOSITORY-NAME.git
```

**Wichtig – einmalig prüfen:** Damit eure Arbeit im eigenen GitHub-Profil zählt, muss Git dieselbe E-Mail-Adresse benutzen wie euer GitHub-Konto.
In GitHub Desktop: **File → Options → Git** (Mac: **GitHub Desktop → Settings → Git**) → bei **Email** die Adresse aus eurem GitHub-Konto auswählen.

---

## Jedes Mal: eine Aufgabe erledigen (7 Schritte)

### Schritt 1 · Aktuellen Stand holen
In GitHub Desktop oben **Current branch: main** auswählen, dann **Fetch origin** und danach **Pull origin** klicken.
*Warum?* So arbeitet ihr auf dem neuesten Stand und vermeidet Konflikte.

### Schritt 2 · Branch anlegen
**Current branch → New branch**. Name klein, mit Bindestrichen, und so, dass man versteht, worum es geht:
- `anforderungsliste`
- `datenbank-tabellen`
- `fehler-login-behoben`

**Create branch** klicken.

Kommandozeile:
```
git switch -c anforderungsliste
```

### Schritt 3 · Arbeiten
In VS Code Dateien anlegen oder ändern und speichern (**Strg+S**).
Code gehört in den Ordner `src/`. Dokumentation gehört in den Ordner der passenden Phase, z. B. `docs/1-analyse/` – die Übersicht steht in [docs/README.md](docs/README.md).

### Schritt 4 · Commit – einen Zwischenstand speichern
In GitHub Desktop seht ihr links alle geänderten Dateien.
1. Unten bei **Summary** eine kurze Beschreibung im Befehlston schreiben:
   - gut: „Anforderungsliste mit Muss-Kriterien ergänzt“
   - schlecht: „Änderungen“, „asdf“, „fertig“
2. **Commit to [branch-name]** klicken.

Lieber viele kleine Commits als einen riesigen.

Kommandozeile:
```
git add .
git commit -m "Anforderungsliste mit Muss-Kriterien ergänzt"
```

### Schritt 5 · Push – den Branch zu GitHub hochladen
Oben **Publish branch** (beim ersten Mal) bzw. **Push origin** klicken.

Kommandozeile:
```
git push -u origin anforderungsliste
```

### Schritt 6 · Pull Request stellen
1. In GitHub Desktop **Create Pull Request** klicken – der Browser öffnet sich.
2. Die Vorlage ausfüllen: Was, warum, wie getestet, KI-Einsatz.
3. Rechts bei **Reviewers** ein Teammitglied auswählen.
4. **Create pull request** klicken.

### Schritt 7 · Review und Merge
**Die Person, die prüft:**
1. Auf GitHub den Pull Request öffnen → Reiter **Files changed**.
2. Bei Fragen auf das **+** neben einer Zeile klicken und kommentieren.
3. Oben rechts **Review changes** → **Approve** (in Ordnung) oder **Request changes** (bitte noch ändern).

**Danach:** **Merge pull request** → **Confirm merge** → **Delete branch** klicken.
Zum Schluss in GitHub Desktop wieder auf `main` wechseln und **Pull origin** klicken.

---

## Gemeinsam am selben Code arbeiten (Live Share)

Für Pair-Programming am Samstag:
1. In VS Code links unten auf **Live Share** klicken und mit GitHub anmelden.
2. Den Einladungslink an das Teammitglied schicken.
3. Beide sehen und bearbeiten denselben Code gleichzeitig.
4. Committen tut nur die Person, die die Sitzung gestartet hat. Im Commit-Text beide nennen, z. B. „Login-Formular gebaut (mit @partnername)“.

Damit die zweite Person auch im eigenen Profil auftaucht, ans Ende der Commit-Beschreibung (im Feld **Description**) schreiben:
```
Co-authored-by: Vorname Nachname <email-des-github-kontos@example.com>
```

---

## Aufgaben planen: Issues und Board

- **Issue anlegen:** Reiter **Issues → New issue** → Vorlage wählen (Aufgabe, Fehler oder Idee).
- **Issue zuweisen:** rechts bei **Assignees** die verantwortliche Person eintragen.
- **Issue mit Pull Request verbinden:** im Pull Request schreiben „Schließt #12“ – dann wird Issue 12 beim Merge automatisch geschlossen.
- **Board:** Reiter **Projects** → Board mit den Spalten *Offen · In Arbeit · Fertig*.

---

## Wenn es hakt

| Meldung / Problem | Was ihr tut |
|---|---|
| „rejected“ beim Push | Erst **Fetch origin → Pull origin**, dann erneut pushen |
| Merge-Konflikt | GitHub Desktop zeigt die Dateien. In VS Code die markierten Stellen ansehen, gemeinsam entscheiden, was bleibt, speichern, committen |
| Aus Versehen auf `main` gearbeitet | Noch nicht committet? Einfach **New branch** anlegen – die Änderungen wandern mit |
| Keine Schreibrechte | Lernbegleiter fragen – ihr müsst Mitglied der Organisation sein |
| Commit erscheint nicht im eigenen Profil | E-Mail in Git prüfen (siehe oben) |

Fehler gehören dazu. Jede gelöste Git-Panne ist eine Geschichte für das Vorstellungsgespräch.
