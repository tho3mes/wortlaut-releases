# Änderungen

Alle veröffentlichten Versionen von Wortlaut. Die jeweils neueste steht oben.

## 2.1.3 – 19.10.2026

> Updates hängen nicht mehr in einer Schleife, und die Einstellungen sind neu gestaltet: klarer, kontrastreicher, alles auf einen Blick.

**Geändert**
- Einstellungen neu gestaltet: Jede Seite hat eine kurze Erklärung, die Optionen stehen in klar abgegrenzten Karten, je Zeile Beschriftung und Hinweis links, Bedienelement rechts. Schalter statt Häkchen, Auswahlfelder und Eingaben mit deutlichem Rand und runden Ecken, schmale Scrollbalken.
- Mehr Kontrast und bessere Tastaturbedienung: größere Hinweistexte, dunklere Ränder, gut sichtbarer Fokusrahmen, Screenreader lesen zu jedem Schalter auch den Hinweis vor. Strg+S speichert.
- Alle Seiten sind immer sichtbar, „Technik anzeigen“ entfällt. Mikrofon und Aufnahme sind eine Seite, „Ausgabe“ heißt jetzt „Einfügen“. Modusleiste und „Modus nach Programm vorwählen“ stehen jetzt unter Modi, direkt bei der Erklärung.
- Verbindung zeigt jeden Schlüssel in einer eigenen Zeile mit Ort (Deutschland, EU, USA).

**Behoben**
- Das Update von 2.1.1 auf 2.1.2 konnte in einer Schleife hängen: Wortlaut meldete das Update, startete danach aber wieder in der alten Version und bot es erneut an. Das passierte, wenn sich die alte Version nicht rechtzeitig beendete oder ihre Programmdatei noch gesperrt war. Jetzt wartet die neue Version auf alle alten Wortlaut-Prozesse aus demselben Ordner, schließt hängende, ersetzt die Programmdatei notfalls über Umbenennen und startet nie wieder die alte Version.
- Wortlaut beendet sich beim Beenden und vor einem Update vollständig.

**Hinweis**
- Wer noch 2.1.1 hat, bekommt 2.1.3 direkt. Das Ersetzen übernimmt bereits die neue Version, deshalb greift die Korrektur schon bei diesem Update.

## 2.1.2 – 19.10.2026

> EU zuerst, oneAI mit dem Standardmodell deiner Organisation, Verfügbarkeit als Ampel, und der Text landet immer dort, wo du angefangen hast.

**Neu**
- Technik zeigt die Verfügbarkeit jedes KI-Anbieters live als Ampel (grün, gelb, rot), solange die Seite offen ist, mit Antwortzeit und Uhrzeit der letzten Prüfung. Geprüft wird nur die Anmeldung: keine Inhalte, keine Kosten. Dieselbe Ampel steht auf der Seite Verbindung.
- Technik zeigt die tatsächliche Reihenfolge der Anbieter mit deinen Schlüsseln, z. B. „oneAI → Mistral“, und sagt, was fehlt, wenn keiner bereit ist.
- Neue Auswahl „Nur Mistral (EU)“ neben „Automatisch“ und „Nur oneAI“. „Nur OpenAI“ erscheint erst nach der Freischaltung der US-Anbieter.
- oneAI-Modell wählbar (Technik): Wortlaut zeigt die Modelle, die deine oneAI-Organisation für dich freigegeben hat, etwa die Mistral-Modelle, die in der EU laufen. Standard ist das Standardmodell deiner Organisation.

**Geändert**
- oneAI nutzt für die Textaufbereitung nicht mehr fest Gemini Flash, sondern das Standardmodell deiner Organisation. Ein gewähltes Modell, das nicht (mehr) für dich freigegeben ist, überspringt Wortlaut. Die Spracherkennung wählt oneAI wie bisher selbst.
- EU zuerst: Standardmäßig nutzt Wortlaut nur oneAI und Mistral. OpenAI und Google (Gemini) laufen erst, wenn du sie ausdrücklich freischaltest. Vorher nennt Wortlaut die Risiken und fragt einmal nach deinem Einverständnis: Verarbeitung und Speicherung in den USA und US-Recht, Speicherung und Training nach den Bedingungen des Anbieters, Zulässigkeit in Unternehmen.
- Seite Verbindung und „Meine Schlüssel“ neu sortiert: oneAI (Deutschland) und Mistral (EU) oben, US-Anbieter in einem eigenen Bereich, dessen Schlüssel erst nach der Freischaltung sichtbar sind. Der Hinweis auf oneAI ist kleiner und schlichter.
- Wer schon Schlüssel für US-Anbieter eingetragen hat, wird beim ersten Start einmal gefragt. Ohne ausdrückliches Ja bleiben sie aus; die Schlüssel bleiben gespeichert.
- Reihenfolge der Ersatzkette: oneAI, dann Mistral, erst danach freigeschaltete US-Anbieter.
- Barrierefreiheit: Hinweistexte, Rahmen und Akzente mit mehr Kontrast (WCAG 2.1 AA), Knöpfe und Seitenleiste per Tab, Enter und Leertaste bedienbar, mit sichtbarem Fokusrahmen und Namen für Screenreader. Die Ampel zeigt den Zustand immer auch als Text.
- Updates laden die ZIP (rund 66 statt 157 MB) und prüfen die enthaltene Programmdatei wie bisher per Prüfsumme und digitaler Signatur. Klappt das nicht, lädt Wortlaut die EXE.
- Datenschutzhinweis angepasst; er wird einmal neu bestätigt.

**Entfernt**
- Anthropic (Claude) als direkter Anbieter. Ein gespeicherter Claude-Schlüssel wird nicht mehr genutzt; du kannst ihn in der Windows-Anmeldeinformationsverwaltung entfernen (Einträge `wortlaut-*`).
- Zeitbuchung (ClickUp) aus den Einstellungen und aus „Meine Schlüssel“.

**Behoben**
- Mit oneAI scheiterte die Textaufbereitung, wenn deine Organisation Gemini Flash nicht freigegeben hat.
- Wer während der Aufbereitung in ein anderes Fenster wechselte, bekam den Text dort oder in einem anderen Feld eingefügt. Jetzt landet er im Fenster und Eingabefeld, in dem das Diktat begonnen hat, auch wenn dieses Fenster minimiert ist. Danach springt Wortlaut zurück in das Fenster, in dem du gerade arbeitest, und wartet dabei, bis du kurz nicht tippst. Geht das Zielfenster nicht nach vorn oder wurde es geschlossen, bleibt der Text in der Zwischenablage, statt irgendwo zu landen. Danke für das Feedback!
- Updates konnten bei langsamer Verbindung nach fünf Minuten abbrechen.

**Bekannt**
- Das Update von 2.1.1 auf 2.1.2 kann in einer Schleife hängen (behoben in 2.1.3).
- Wechselst du im Browser während der Aufbereitung den Tab, landet der Text im dann sichtbaren Tab. Wortlaut kann Tabs nicht unterscheiden.

## 2.1.1 – 18.10.2026

> Download jetzt auch als ZIP, damit Browser und Defender die Datei nicht mehr festhalten.

**Neu**
- Download als ZIP: `Wortlaut.zip` enthält die Programmdatei, Prüfsumme, Signatur und eine kurze Anleitung. Browser und Windows Defender halten eine ZIP beim Herunterladen seltener fest als eine einzelne EXE. Die EXE gibt es weiterhin einzeln.
- VirusTotal-Bericht: Die Release-Notes verlinken den Prüfbericht der Programmdatei.

**Bekannt**
- Beim ersten Start kann Windows SmartScreen weiterhin warnen, auch wenn die EXE aus der ZIP kommt. Wortlaut hat noch kein Windows-Zertifikat; eine Store-Version ist in Vorbereitung.

## 2.1.0 – 18.10.2026

**Neu**
- Gedächtnis (Einstellungen › Gedächtnis, standardmäßig aus): Jedes eingefügte Ergebnis wird lokal und verschlüsselt abgelegt, mit Datum, Modus, Programm und auf Wunsch dem Fenstertitel. Aufbewahrung frei wählbar von 7 Tagen bis unbegrenzt (Standard 90 Tage), angeheftete Einträge bleiben. Für Speichern und Suchen verlässt nichts den PC.
- Verlauf (Num +) mit Suche: Wortanfang reicht, Umlaute sind egal, mehrere Wörter grenzen ein, Text in Anführungszeichen sucht die genaue Wortfolge. Filter nach Zeitraum, Programm und Modus, Treffer markiert, Anheften und Löschen, Bedienung komplett per Tastatur.
- Sicherung mit eigenem Kennwort (Export und Import), damit das Gedächtnis einen PC- oder Profilwechsel übersteht.
- Aufnahmefenster mit Pegelbalken wie ein Mikrofonkanal; beim Aufbereiten läuft eine ruhige Welle.
- Empfehlung für oneAI auf der Seite Verbindung und in „Meine Schlüssel“, mit Link zu oneai.eu. Transparenz: Der Entwickler arbeitet bei der relyon AG, die oneAI anbietet; Wortlaut ist ein privat entwickeltes, unabhängiges Projekt.
- Signierte Updates: Jede Version hat zusätzlich zur Prüfsumme eine digitale Signatur (`Wortlaut.exe.sig`). Ab 2.1.0 installiert Wortlaut ein Update nur, wenn beides stimmt; die Update-Quelle ist fest eingebaut. Von Hand prüfen: siehe [SECURITY.md](SECURITY.md).
- „Alle löschen“ unter „Meine Schlüssel“ entfernt alle gespeicherten Schlüssel auf einmal, etwa vor einer Deinstallation.

**Geändert**
- Ende der Beta.
- Einstellungen mit neu geordneter Seitenleiste: Gruppen, deutlich markierter aktiver Punkt, nichts überlappt mehr.
- Hinweise zum Verarbeitungsort je Anbieter: OpenAI, Claude und Gemini können Daten in den USA verarbeiten, Mistral hat seinen Sitz in der EU.
- Weniger Fehlalarme bei Virenscannern: Die Tastenkürzel laufen über die normale Windows-Anmeldung statt über einen dauerhaften Tastatur-Hook, die Programmdatei ist nicht mehr komprimiert (dadurch größer), und Updates kommen ohne Hilfsskript aus (ab dem nächsten Update nach 2.1.0).
- Feedback geht per E-Mail an feedback@oesterle.cloud oder auf Wunsch öffentlich als Beitrag auf GitHub, nicht mehr nach ClickUp. Neu: Knopf „Kopieren“ für alle, die im Browser mailen.
- Datenschutzhinweis um das Gedächtnis und das Löschen der Schlüssel ergänzt; er wird einmal neu bestätigt.
- Wird Wortlaut ein zweites Mal gestartet, erscheint ein Hinweis, statt dass scheinbar nichts passiert.

**Behoben**
- Nach einem automatischen Stopp (Stille, Höchstdauer, Taste losgelassen) stand der Stopp-Grund doppelt im Log.
- Der Info-Text zu 2.0.15 nannte für „Audio komprimieren“ den falschen Ort in den Einstellungen.

## 2.0.15 (beta.15) – 16.10.2026

**Neu**
- Option „Audio vor dem Senden komprimieren“ (Einstellungen › Technik anzeigen › Aufnahme): Die Aufnahme geht als MP3 statt WAV hinaus, etwa 8-mal kleiner. Spürbar vor allem bei langen Diktaten und langsamer Verbindung. Klappt die Umwandlung nicht, sendet Wortlaut automatisch wie bisher.

## 2.0.14 (beta.14) – 15.10.2026

**Geändert**
- Tray aufgeräumt: „Zugang anfragen“ entfernt, „Zeit buchen“ erscheint nur noch, wenn eine Zeitbuchung eingerichtet ist (dann auch erst das Kürzel).
- Feedback-Dialog und Glossar mit passenden Texten: Feedback geht direkt an den Entwickler, das Glossar liegt nur auf deinem PC.
- Klarere Meldungen, wenn kein KI-Anbieter bereit ist oder die Aufbereitung scheitert.

**Neu**
- Tray → „Wortlaut unterstützen“ führt zur Projektseite.

## 2.0.13 (beta.13) – 15.10.2026

**Neu**
- Keine separate .NET-Installation mehr nötig: Die Laufzeit ist in der Programmdatei enthalten (Datei dadurch größer, erster Start etwas langsamer).
- Bilanz zeigt die durchschnittliche Verarbeitungsdauer pro Diktat und je Anbieter und Modell (letzte 50 Messungen).

**Geändert**
- Standardeinstellung „Automatisch“: Wortlaut funktioniert jetzt auch ohne oneAI-Zugang mit jedem eingerichteten Anbieter. Der frühere Standard „Nur oneAI“ wird einmalig umgestellt.
- Bilanz kompakter, ohne Scrollbalken.
- Release-Texte und Dokumente werden automatisch veröffentlicht.

## 2.0.12 (beta.12) – 15.10.2026

**Geändert**
- Herausgeber und Copyright: Thomas Oesterle (auch in den Dateieigenschaften der EXE).
- Neuer Datenschutzhinweis in der App; er wird einmal neu bestätigt.
- Info-Seite mit Links zu Nutzungsbedingungen, Lizenzen Dritter und Release-Seite.
- Verbindungsseite zeigt alle KI-Anbieter und testet sie einzeln.

**Entfernt**
- „Zugang anfragen“ und die Anzeige der alten Server-Adressen.

**Bekannt**
- Benötigt noch die separat installierte .NET 8 Desktop Runtime (behoben in 2.0.13).

## 2.0.11 (beta.11) – 15.10.2026

**Neu**
- KI direkt aus der App: oneAI, OpenAI, Anthropic (Claude), Google Gemini und Mistral. Fällt ein Anbieter aus oder antwortet zu langsam, übernimmt automatisch der nächste eingerichtete.
- „Meine Schlüssel“ mit Feldern für alle Anbieter und die oneAI-Adresse; nach dem Speichern werden alle Anbieter einmal getestet.
- Glossar und persönlicher Stil liegen lokal auf dem PC.
- Updates kommen über dieses Repository, mit Prüfsummenkontrolle vor der Installation.
- Feedback direkt aus der App nach ClickUp, ersatzweise per E-Mail.

**Entfernt**
- Abhängigkeit von einem zentralen Server für Diktat, Glossar, Stil und Updates.
- Zugangsanfrage aus der App.

**Bekannt**
- Die Zeitbuchung per Sprache ist in dieser Version noch nicht ohne Server nutzbar.
- Die Programmdatei ist noch nicht digital signiert (Windows-SmartScreen-Hinweis beim ersten Start).
