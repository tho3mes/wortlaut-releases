# Datenschutzhinweise für Wortlaut

Stand: 17. Oktober 2026 (ab Version 2.1.0)

Diese Hinweise beschreiben, welche Daten die Software Wortlaut verarbeitet, wohin sie gehen und wie lange sie gespeichert werden.

## Grundsatz

Wortlaut arbeitet ohne eigenen Server des Herausgebers. Daten gehen nur an die Dienste, die du selbst eingerichtet hast, und nur, wenn du eine Funktion aktiv auslöst.

## Was wohin übertragen wird

| Funktion | Welche Daten | Empfänger |
|---|---|---|
| Diktat | Sprachaufnahme (WAV 16 kHz mono, optional als MP3 komprimiert); beim Umschreiben zusätzlich der markierte Text; dein Glossar und deine Stilvorgaben als Teil der Anweisung | der von dir eingerichtete KI-Anbieter (oneAI, OpenAI, Anthropic, Google Gemini oder Mistral), direkt von deinem PC |
| Ersatz bei Ausfall | dieselben Daten | der nächste von dir eingerichtete Anbieter in der Reihenfolge |
| Verbindungstest | nur dein API-Schlüssel zur Anmeldung, keine Inhalte | die eingerichteten KI-Anbieter |
| Update-Prüfung | technische Verbindungsdaten (z. B. IP-Adresse), Programmversion im User-Agent | GitHub (api.github.com, github.com) |
| Feedback per E-Mail | nur was du selbst absendest: dein Text, Programmversion, Windows-Version, auf Wunsch eine Logdatei ohne Diktatinhalte | feedback@oesterle.cloud, über dein eigenes E-Mail-Programm |
| Feedback auf GitHub (optional) | dein Text und die Programmversion, keine Logdatei | GitHub, öffentlich sichtbar im Repository wortlaut-releases |
| Zeitbuchung (optional) | Sprachaufnahme, Titel des aktiven Fensters, ClickUp-Link aus der Zwischenablage | nur wenn eingerichtet |

Für das Gedächtnis (Speichern, Suchen, Sicherung) wird nichts übertragen.

Wortlaut fordert bei den KI-Anbietern keine Speicherung an, wo die Schnittstelle das erlaubt (z. B. bei OpenAI `store: false`). Wie lange ein Anbieter Daten dennoch vorhält, etwa zur Missbrauchserkennung, regeln dessen eigene Bedingungen. Bei oneAI wird für jede Textaufbereitung ein Chat im persönlichen Bereich angelegt und unmittelbar danach wieder gelöscht. Laut oneAI wird außerdem jede Anfrage im Audit-Log der Organisation protokolliert (u. a. Nutzer, Modell, Regel und Risikostufe); deine Organisation kann diese Einträge einsehen.

**Anbieter außerhalb der EU:** OpenAI, Anthropic und Google können Daten in den USA verarbeiten. Wer das vermeiden will, richtet nur Anbieter mit Verarbeitung in der EU ein.

## Was lokal gespeichert wird

Alle Dateien liegen im Benutzerprofil unter `%APPDATA%\Wortlaut`.

| Daten | Speicherort | Dauer |
|---|---|---|
| API-Schlüssel, oneAI-Adresse | Windows-Anmeldeinformationsverwaltung (`wortlaut-*`) | bis du sie löschst |
| Einstellungen | `wortlaut.json` | bis du sie löschst |
| Glossar, persönlicher Stil | `glossar.json`, `stil.json` | bis du sie löschst |
| Verlauf der letzten 10 Ergebnisse | verschlüsselt (Windows DPAPI) | 24 Stunden, abschaltbar |
| Gedächtnis (optional, standardmäßig aus) | `gedaechtnis\JJJJ-MM.dat`, verschlüsselt (Windows DPAPI): eingefügte Ergebnisse mit Datum, Modus, Programm und, abschaltbar, Fenstertitel | gewählte Frist (7 Tage bis unbegrenzt, Standard 90 Tage); angeheftete Einträge, bis du sie löschst |
| Sicherung des Gedächtnisses (optional) | `.wlg`-Datei an einem Ort deiner Wahl, verschlüsselt mit deinem Kennwort (AES-256-GCM) | bis du sie löschst |
| Nutzungsbilanz | `statistik.json`, nur Zahlen pro Tag, keine Texte | 90 Tage |
| Logdatei | `wortlaut.log`, ohne Diktatinhalte und ohne Fenstertitel | bis du sie löschst, abschaltbar |
| Letzte Aufnahme nach einem Fehler | temporärer Ordner | bis zur nächsten Aufnahme |

Im Gedächtnis nicht gespeichert werden Aufnahmen, markierte Ausgangstexte beim Umschreiben und Zeitbuchungen. Auf Firmen-PCs können Domänen-Administratoren mit DPAPI verschlüsselte Dateien technisch grundsätzlich entschlüsseln; Wortlaut sammelt aber nichts zentral.

## Verantwortlichkeit

- **Private Nutzung:** Du entscheidest selbst, welche Anbieter du nutzt. Der Herausgeber erhält keine Diktatinhalte.
- **Dienstliche Nutzung:** Verantwortlich im Sinne der DSGVO ist in der Regel dein Arbeitgeber. Kläre vorab, welche Anbieter zugelassen sind und ob ein Auftragsverarbeitungsvertrag besteht.

## Deine Möglichkeiten

- Verlauf in den Einstellungen abschalten, er wird dann sofort gelöscht.
- Gedächtnis abschalten, die Frist verkürzen, einzelne Einträge im Verlauf löschen oder mit „Alles löschen“ den kompletten Ordner `gedaechtnis` entfernen.
- Logdatei abschalten oder löschen.
- Schlüssel in der Windows-Anmeldeinformationsverwaltung entfernen (Einträge `wortlaut-*`).
- Programm und den Ordner `%APPDATA%\Wortlaut` löschen: Danach bleiben auf dem PC keine Daten von Wortlaut zurück, außer Sicherungen, die du selbst an anderer Stelle abgelegt hast.

Fragen zum Datenschutz bei einem KI-Anbieter richtest du an diesen Anbieter. Fragen zur Software selbst über die Feedbackfunktion in der App oder an feedback@oesterle.cloud.
