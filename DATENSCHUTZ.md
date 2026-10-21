# Datenschutzhinweise für Wortlaut

Stand: 21. Oktober 2026 (ab Version 2.2.1)

Diese Hinweise beschreiben, welche Daten die Software Wortlaut verarbeitet, wohin sie gehen und wie lange sie gespeichert werden. Sie gelten für alle Vertriebswege: die Programmdatei und die Archive von GitHub (Einzeldatei und Ordner-Variante) sowie die Version aus dem Microsoft Store.

## Herausgeber und Kontakt

Herausgeber der Software ist Thomas Oesterle, Kontakt feedback@oesterle.cloud, Anschrift im Impressum auf https://oesterle.cloud/impressum/. Der Herausgeber betreibt für Wortlaut keinen Server und erhält keine Diktatinhalte. Verantwortlicher im Sinne der DSGVO ist er nur für Nachrichten, die du ihm selbst schickst (Feedback, siehe unten).

## Grundsatz

Wortlaut arbeitet ohne eigenen Server des Herausgebers. Daten gehen nur an die Dienste, die du selbst eingerichtet hast, und nur, wenn du eine Funktion aktiv auslöst oder ausdrücklich eingeschaltet hast. Standardmäßig nutzt Wortlaut nur Anbieter mit Sitz in Deutschland bzw. der EU (oneAI, Mistral).

## Was wohin übertragen wird

| Funktion | Welche Daten | Empfänger |
|---|---|---|
| Diktat | Sprachaufnahme (WAV 16 kHz mono, optional als MP3 komprimiert); beim Umschreiben zusätzlich der markierte Text; dein Glossar und deine Stilvorgaben als Teil der Anweisung | der von dir eingerichtete KI-Anbieter, direkt von deinem PC: standardmäßig oneAI oder Mistral; hat der Autopilot es so gesetzt, für die Spracherkennung zuerst das oneAI Gateway deiner Organisation (gleiche oneAI-Adresse, gleicher Schlüssel) oder Mistral; OpenAI oder Google Gemini nur, wenn du US-Anbieter ausdrücklich freigeschaltet hast |
| Ersatz bei Ausfall | dieselben Daten | der nächste von dir eingerichtete Anbieter in der Reihenfolge oneAI, Mistral, danach freigeschaltete US-Anbieter; ein Anbieter, der gerade ausgefallen oder zu langsam war, rückt für 3 Minuten ans Ende |
| KI fragen im Verlauf (optional, standardmäßig aus, nur auf Knopfdruck) | deine Frage und höchstens 12 vorher auf deinem PC ausgewählte, gekürzte Gedächtnis-Einträge mit Datum, Modus, Programm und, falls gespeichert, Fenstertitel | der von dir eingerichtete KI-Anbieter in derselben Reihenfolge wie beim Diktat |
| Pre-Check (nur auf Knopfdruck oder, wenn du „Täglich prüfen“ einschaltest, einmal am Tag) | ein fester, in Wortlaut eingebauter Beispieltext und eine Testaufnahme, die Windows auf deinem PC aus einem festen Satz spricht; keine Inhalte von dir | oneAI (je getestetem Textmodell drei Anfragen, Spracherkennung und Sprachmodelle im oneAI Gateway je zwei) sowie Mistral, falls eingerichtet (zwei Anfragen) |
| Verbindungstest und Verfügbarkeitsanzeige (Ampel) | nur dein API-Schlüssel zur Anmeldung, keine Inhalte; die Ampel prüft alle 60 Sekunden, solange die Seite Technik offen ist | die eingerichteten und freigeschalteten KI-Anbieter |
| Modelllisten (nur oneAI) | dein API-Schlüssel, keine Inhalte | oneAI, um die für dich freigegebenen Modelle anzuzeigen; beim Pre-Check zusätzlich das oneAI Gateway, um dort angebotene Sprachmodelle zu finden |
| Update-Prüfung (GitHub-Version) | technische Verbindungsdaten (z. B. IP-Adresse), Programmversion im User-Agent | GitHub (api.github.com, github.com) |
| Installation und Updates (Store-Version) | was der Microsoft Store dafür verarbeitet, z. B. dein Microsoft-Konto und Gerätedaten | Microsoft, nach der Datenschutzerklärung von Microsoft; Wortlaut selbst sendet hier nichts |
| Feedback per E-Mail | nur was du selbst absendest: dein Text, Programmversion, Windows-Version, auf Wunsch eine Logdatei ohne Diktatinhalte | feedback@oesterle.cloud, über dein eigenes E-Mail-Programm |
| Feedback auf GitHub (optional) | dein Text und die Programmversion, keine Logdatei | GitHub, öffentlich sichtbar im Repository wortlaut-releases |
| Zeitbuchung (optional) | Sprachaufnahme, Titel des aktiven Fensters, ClickUp-Link aus der Zwischenablage | nur wenn eingerichtet |

Für das Gedächtnis (Speichern, Suchen, Sicherung) wird nichts übertragen. Nur „KI fragen“ schickt auf deinen Knopfdruck ausgewählte Einträge hinaus (siehe Tabelle); vor der ersten Nutzung fragt Wortlaut nach deinem Einverständnis. Frage und Antwort speichert Wortlaut nicht.

Wortlaut fordert bei den KI-Anbietern keine Speicherung an, wo die Schnittstelle das erlaubt (z. B. bei OpenAI `store: false`). Wie lange ein Anbieter Daten dennoch vorhält, etwa zur Missbrauchserkennung, regeln dessen eigene Bedingungen. Bei oneAI wird für jede Textaufbereitung, jede Frage und jeden Testlauf ein Chat im persönlichen Bereich angelegt und unmittelbar danach wieder gelöscht. Laut oneAI wird außerdem jede Anfrage im Audit-Log der Organisation protokolliert (u. a. Nutzer, Modell, Regel und Risikostufe); deine Organisation kann diese Einträge einsehen.

**US-Anbieter (standardmäßig aus):** OpenAI und Google sind US-Unternehmen. Wortlaut nutzt sie nur, wenn du sie unter Verbindung oder „Meine Schlüssel“ nach einem Risikohinweis ausdrücklich freischaltest und bestätigst, dass deine Daten in den USA verarbeitet und gespeichert werden können. Sie unterliegen dann US-Recht; US-Behörden können unter Umständen Zugriff verlangen. Wie lange die Anbieter Daten speichern und ob sie sie zum Training oder zur Verbesserung ihrer Dienste nutzen, regeln deren Tarife und Bedingungen. In Unternehmen ist das in der Regel nur mit Freigabe des Arbeitgebers zulässig. Abschalten kannst du die Freischaltung jederzeit. Anthropic (Claude) unterstützt Wortlaut ab 2.1.2 nicht mehr als direkten Anbieter. Der Pre-Check prüft keine US-Anbieter.

**Feedback an den Herausgeber:** Schickst du Feedback per E-Mail, verarbeitet der Herausgeber deine E-Mail-Adresse und den Inhalt, um dein Anliegen zu bearbeiten (Art. 6 Abs. 1 lit. f DSGVO, berechtigtes Interesse an Fehlerbehebung und Weiterentwicklung). Die Nachricht wird gelöscht, sobald sie erledigt ist und keine Aufbewahrungspflicht besteht.

## Was lokal gespeichert wird

Bei der GitHub-Version liegen alle Dateien im Benutzerprofil unter `%APPDATA%\Wortlaut`. Bei der Store-Version leitet Windows diesen Ordner in den Paketbereich der App um (`%LOCALAPPDATA%\Packages\<Paket>\LocalCache\Roaming\Wortlaut`); beim Deinstallieren entfernt Windows ihn mit.

| Daten | Speicherort | Dauer |
|---|---|---|
| API-Schlüssel, oneAI-Adresse | Windows-Anmeldeinformationsverwaltung (`wortlaut-*`), für beide Versionen gemeinsam | bis du sie löschst, auch nach einer Deinstallation |
| Einstellungen (inkl. Freischaltung der US-Anbieter, oneAI-Modelle, Zuordnung des Autopiloten je Modus und Zustimmung zu „KI fragen“) | `wortlaut.json` | bis du sie löschst |
| Glossar, persönlicher Stil | `glossar.json`, `stil.json` | bis du sie löschst |
| Verlauf der letzten 10 Ergebnisse | verschlüsselt (Windows DPAPI) | 24 Stunden, abschaltbar |
| Gedächtnis (optional, standardmäßig aus) | `gedaechtnis\JJJJ-MM.dat`, verschlüsselt (Windows DPAPI): eingefügte Ergebnisse mit Datum, Modus, Programm und, abschaltbar, Fenstertitel | gewählte Frist (7 Tage bis unbegrenzt, Standard 90 Tage); angeheftete Einträge, bis du sie löschst |
| Sicherung des Gedächtnisses (optional) | `.wlg`-Datei an einem Ort deiner Wahl, verschlüsselt mit deinem Kennwort (AES-256-GCM) | bis du sie löschst |
| Nutzungsbilanz | `statistik.json`, nur Zahlen pro Tag und Verarbeitungsdauer je Anbieter und oneAI-Modell, keine Texte | 90 Tage bzw. die letzten 50 Messungen |
| Ergebnisse des Pre-Checks | `modelltest.json` und `precheck.json`, nur Modell- bzw. Anbietername, Zeiten, Punktzahl, Wortfehlerrate und Kurzbefunde, keine Texte | bis du sie löschst; jeder Pre-Check aktualisiert sie |
| Logdatei | `wortlaut.log`, ohne Diktatinhalte und ohne Fenstertitel | bis du sie löschst, abschaltbar |
| Letzte Aufnahme nach einem Fehler | temporärer Ordner | bis zur nächsten Aufnahme |

Im Gedächtnis nicht gespeichert werden Aufnahmen, markierte Ausgangstexte beim Umschreiben, Zeitbuchungen sowie Fragen und Antworten von „KI fragen“. Die Testaufnahme des Pre-Checks entsteht nur im Arbeitsspeicher und wird nicht abgelegt. Auf Firmen-PCs können Domänen-Administratoren mit DPAPI verschlüsselte Dateien technisch grundsätzlich entschlüsseln; Wortlaut sammelt aber nichts zentral.

## Verantwortlichkeit

- **Private Nutzung:** Du entscheidest selbst, welche Anbieter du nutzt. Der Herausgeber erhält keine Diktatinhalte.
- **Dienstliche Nutzung:** Verantwortlich im Sinne der DSGVO ist in der Regel dein Arbeitgeber. Kläre vorab, welche Anbieter zugelassen sind und ob ein Auftragsverarbeitungsvertrag besteht. Das gilt auch für „KI fragen“, weil dabei frühere Ergebnisse erneut an den Anbieter gehen.

## Deine Möglichkeiten und Rechte

- Verlauf in den Einstellungen abschalten, er wird dann sofort gelöscht.
- Gedächtnis abschalten, die Frist verkürzen, einzelne Einträge im Verlauf löschen oder mit „Alles löschen“ den kompletten Ordner `gedaechtnis` entfernen.
- „KI fragen“ unter Einstellungen › Gedächtnis wieder abschalten.
- Autopilot unter Einstellungen › Technik zurücksetzen und „Täglich prüfen und übernehmen“ abschalten.
- US-Anbieter unter Verbindung oder „Meine Schlüssel“ wieder abschalten.
- Logdatei abschalten oder löschen.
- Schlüssel mit „Alle löschen“ unter „Meine Schlüssel“ oder in der Windows-Anmeldeinformationsverwaltung entfernen (Einträge `wortlaut-*`).
- GitHub-Version: Programm bzw. Programmordner und den Ordner `%APPDATA%\Wortlaut` löschen. Store-Version: deinstallieren. Danach bleiben auf dem PC keine Daten von Wortlaut zurück, außer den Schlüsseln und Sicherungen, die du selbst an anderer Stelle abgelegt hast.

Gegenüber dem Herausgeber hast du, soweit er Daten von dir verarbeitet (Feedback), die Rechte auf Auskunft, Berichtigung, Löschung, Einschränkung, Datenübertragbarkeit und Widerspruch (Art. 15 bis 21 DSGVO) sowie das Recht, dich bei einer Datenschutz-Aufsichtsbehörde zu beschweren. Fragen zum Datenschutz bei einem KI-Anbieter oder bei Microsoft richtest du an diesen. Fragen zur Software selbst über die Feedbackfunktion in der App oder an feedback@oesterle.cloud.
