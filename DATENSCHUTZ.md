# Datenschutzhinweise für Wortlaut

Stand: Oktober 2026

Diese Hinweise beschreiben, welche Daten die Software Wortlaut verarbeitet, wohin sie gehen und wie lange sie gespeichert werden.

## Grundsatz

Wortlaut arbeitet ohne eigenen Server des Herausgebers. Daten gehen nur an die Dienste, die du selbst eingerichtet hast, und nur, wenn du eine Funktion aktiv auslöst.

## Was wohin übertragen wird

| Funktion | Welche Daten | Empfänger |
|---|---|---|
| Diktat | Sprachaufnahme (WAV, 16 kHz mono); beim Umschreiben zusätzlich der markierte Text; dein Glossar und deine Stilvorgaben als Teil der Anweisung | der von dir eingerichtete KI-Anbieter (oneAI, OpenAI, Anthropic, Google Gemini oder Mistral), direkt von deinem PC |
| Ersatz bei Ausfall | dieselben Daten | der nächste von dir eingerichtete Anbieter in der Reihenfolge |
| Verbindungstest | nur dein API-Schlüssel zur Anmeldung, keine Inhalte | die eingerichteten KI-Anbieter |
| Update-Prüfung | technische Verbindungsdaten (z. B. IP-Adresse), Programmversion im User-Agent | GitHub (api.github.com, github.com) |
| Feedback | dein Feedbacktext, Programmversion, Rechnername, auf Wunsch eine Logdatei ohne Diktatinhalte | ClickUp (mit deinem persönlichen Token) oder dein E-Mail-Programm |
| Zeitbuchung (optional) | Sprachaufnahme, Titel des aktiven Fensters, ClickUp-Link aus der Zwischenablage | nur wenn eingerichtet |

Wortlaut fordert bei den KI-Anbietern keine Speicherung an, wo die Schnittstelle das erlaubt (z. B. bei OpenAI `store: false`). Wie lange ein Anbieter Daten dennoch vorhält – etwa zur Missbrauchserkennung – regeln dessen eigene Bedingungen. Bei oneAI wird für jede Textaufbereitung ein Chat im persönlichen Bereich angelegt und unmittelbar danach wieder gelöscht.

**Anbieter außerhalb der EU:** OpenAI, Anthropic und Google können Daten in den USA verarbeiten. Wer das vermeiden will, richtet nur Anbieter mit Verarbeitung in der EU ein.

## Was lokal gespeichert wird

Alle Dateien liegen im Benutzerprofil unter `%APPDATA%\Wortlaut`.

| Daten | Speicherort | Dauer |
|---|---|---|
| API-Schlüssel, oneAI-Adresse | Windows-Anmeldeinformationsverwaltung (`wortlaut-*`) | bis du sie löschst |
| Einstellungen | `wortlaut.json` | bis du sie löschst |
| Glossar, persönlicher Stil | `glossar.json`, `stil.json` | bis du sie löschst |
| Verlauf der letzten 10 Ergebnisse | verschlüsselt (Windows DPAPI) | 24 Stunden, abschaltbar |
| Nutzungsbilanz | `statistik.json`, nur Zahlen pro Tag, keine Texte | 90 Tage |
| Logdatei | `wortlaut.log`, ohne Diktatinhalte | bis du sie löschst, abschaltbar |
| Letzte Aufnahme nach einem Fehler | temporärer Ordner | bis zur nächsten Aufnahme |

## Verantwortlichkeit

- **Private Nutzung:** Du entscheidest selbst, welche Anbieter du nutzt. Der Herausgeber erhält keine Diktatinhalte.
- **Dienstliche Nutzung:** Verantwortlich im Sinne der DSGVO ist in der Regel dein Arbeitgeber. Kläre vorab, welche Anbieter zugelassen sind und ob ein Auftragsverarbeitungsvertrag besteht.

## Deine Möglichkeiten

- Verlauf in den Einstellungen abschalten – er wird dann sofort gelöscht.
- Logdatei abschalten oder löschen.
- Schlüssel in der Windows-Anmeldeinformationsverwaltung entfernen (Einträge `wortlaut-*`).
- Programm und den Ordner `%APPDATA%\Wortlaut` löschen: Danach bleiben auf dem PC keine Daten von Wortlaut zurück.

Fragen zum Datenschutz bei einem KI-Anbieter richtest du an diesen Anbieter. Fragen zur Software selbst über die Feedbackfunktion in der App.
