# Änderungen

Alle veröffentlichten Versionen von Wortlaut. Die jeweils neueste steht oben.

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
