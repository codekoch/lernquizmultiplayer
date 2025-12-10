# <a href=https://codekoch.github.io/lernquizmultiplayer/lernquizmultiplayer_with_QR_Code.html> Lernquiz - Multiplayer </a>

Ein einfaches, browserbasiertes Multiplayer-Quiz (ähnlich wie Kahoot!), das komplett ohne Server-Installation funktioniert. Es läuft direkt im Browser und nutzt Peer-to-Peer-Technologie (PeerJS) zur Kommunikation zwischen Lehrer (Host) und Schülern (Clients).

<b><a href=https://codekoch.github.io/lernquizmultiplayer/lernquizmultiplayer_with_QR_Code.html> Variante mit QR-Code. Klicke hier, um es zu testen! </a></b>

<b><a href=https://codekoch.github.io/lernquizmultiplayer/lernquizmultiplayer.html> Variante ohne QR-Code. Klicke hier, um es zu testen! </a></b>

<b><a href=https://codekoch.github.io/lernquizmultiplayer/QuizVorlage_ElektrostatikQ1.json>Nutze für den Test z.B. diese json-Vorlage (einfach per Copy & Paste als JSON Text einfügen)</a>

## 🚀 Funktionen

-   **Kein Server nötig:** Einfach die HTML-Datei öffnen.
-   **Echtzeit-Multiplayer:** Lehrer steuert das Spiel, Schüler antworten auf ihren Geräten.
-   **Plattformunabhängig:** Läuft auf PC, Tablet und Smartphone.
-   **LaTeX-Unterstützung:** Formeln können mit MathJax dargestellt werden.
-   **Sofortiges Feedback:** Schüler sehen sofort, ob sie richtig lagen und erhalten Punkte.

## 📖 Anleitung

### Für den Lehrer (Host)
1.  Öffne die Datei `lernquizmultiplayer.html` in einem modernen Browser (Chrome, Firefox, Edge).
2.  Klicke auf **"🎓 Spiel hosten"**.
3.  Lade eine **JSON-Quizdatei** hoch oder füge den JSON-Code direkt ein.
4.  Gib den Schülern den angezeigten **GAME PIN** (oben auf dem Bildschirm) oder den **QR-Code**.
5.  Warte, bis alle Schüler in der Lobby erschienen sind.
6.  (Optional) Wähle "Fragen mischen" oder "Antworten mischen".
7.  Klicke auf **"🚀 Quiz starten"**.

### Für die Schüler (Teilnehmer)
1.  Scanne den den **QR-Code** oder öffne die Datei `lernquizmultiplayer.html` (oder die URL, wo sie liegt).
2.  Klicke auf **"📱 Teilnehmen"**.
3.  Gib den **GAME PIN** des Lehrers und deinen **Namen** ein.
4.  Warte, bis das Spiel startet.

## 📝 Quiz-Erstellung (JSON-Format)

Die Fragen werden in einer einfachen Textdatei im JSON-Format gespeichert (Endung `.json`).

### Struktur

-   `title`: Der Titel des Quiz.
-   `questions`: Eine Liste von Fragen.
    -   `text`: Der Fragetext (HTML erlaubt).
    -   `options`: Eine Liste von Antwortmöglichkeiten.
        -   `id`: Eine eindeutige ID (z.B. "a", "b").
        -   `text`: Die Antworte.
        -   `correct`: `true` für die richtige Antwort, `false` für falsche.
        -   `feedback`: Text, der nach der Antwort angezeigt wird (z.B. Erklärung).

### Vorlage (Beispiel)

Kopiere diesen Code in eine Textdatei und speichere sie als `quiz.json`:

```json
{
  "title": "Allgemeinwissen Quiz",
  "questions": [
    {
      "text": "Was ist die Hauptstadt von Deutschland?",
      "options": [
        { "id": "a", "text": "Berlin", "correct": true, "feedback": "Richtig! Berlin ist seit 1990 wieder die Hauptstadt." },
        { "id": "b", "text": "München", "correct": false, "feedback": "München ist die Hauptstadt von Bayern." },
        { "id": "c", "text": "Hamburg", "correct": false, "feedback": "Hamburg ist eine Hansestadt." },
        { "id": "d", "text": "Köln", "correct": false, "feedback": "Knapp daneben." }
      ]
    },
    {
      "text": "Wie viel ist 2 + 2?",
      "options": [
        { "id": "1", "text": "3", "correct": false, "feedback": "Falsch." },
        { "id": "2", "text": "4", "correct": true, "feedback": "Korrekt!" },
        { "id": "3", "text": "5", "correct": false, "feedback": "Zu viel." },
        { "id": "4", "text": "22", "correct": false, "feedback": "Das wäre ein String-Concat in JavaScript :P" }
      ]
    }
  ]
}
```

## 💡 Hinweise

-   Da das Spiel Peer-to-Peer läuft, müssen sich Host und Clients idealerweise im **gleichen Netzwerk** befinden oder eine direkte Internetverbindung ohne strikte Firewalls haben.
-   Die Datei muss nicht auf einem Webserver liegen, sie kann auch einfach vom USB-Stick oder Netzlaufwerk gestartet werden (sofern Internetzugriff für PeerJS vorhanden ist).
-   Spieler können auch später zum Quiz hinzukommen, wenn sie die GAME PIN kennen.
-   Unter moodle kann mit dem Parameter <b>moodleUser</b> Namen übergeben, so dass die Quizteilnehmernamen festgelegt sind und nicht von den Teilnehmern nachträglich geändert werden können. Unter moodle sollte allerdings nicht die Version mti dem QR-Code verwendet werden.
-   Bei Problemen helfen evtl. diese zwei Testseiten <b><a href=https://codekoch.github.io/lernquizmultiplayer/Netzwerkcheck.html> Netzwerkcheck.html </a></b> und <b><a href=https://codekoch.github.io/lernquizmultiplayer/Netzwerkcheck_ClientIsolation.html>Netzwerkcheck_ClientIsolation.html </a></b>

