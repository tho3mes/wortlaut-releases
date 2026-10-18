# Änderungen

Alle veröffentlichten Versionen von Wortlaut. Die jeweils neueste steht oben.

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
