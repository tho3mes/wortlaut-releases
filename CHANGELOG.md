# Änderungen

Alle veröffentlichten Versionen von Wortlaut. Die jeweils neueste steht oben.

## 2.2.2 – 21.10.2026

> Der Text landet jetzt auch in Desktop-Apps wie ClickUp und BrainMax direkt am Cursor, statt nur im Verlauf.

**Behoben**
- In Desktop-Apps auf Chromium- oder Electron-Basis (z. B. ClickUp, BrainMax) kam der Text nicht an, obwohl der Cursor im Feld stand; er musste aus dem Verlauf kopiert werden. Wortlaut sendet Strg+V jetzt wie ein echter Tastendruck (mit Scancode und kurzen Pausen zwischen Strg und V), erkennt solche Apps selbst und wartet, bis ihr Eingabefeld bereit ist.
- Noch gedrückte Umschalt-, Alt- oder Win-Tasten stören das Einfügen nicht mehr.

**Neu**
- „Tippen statt Einfügen“ (Einfügen): Für Programme, die das Einfügen weiter verweigern, tippt Wortlaut den Text Zeichen für Zeichen, ganz ohne Zwischenablage. Programmnamen eintragen, z. B. `brainmax`. Zeilenumbrüche kommen als Umschalt+Enter, damit Chats nicht vorzeitig senden. Wechselt währenddessen das Fenster, bricht Wortlaut ab und legt den Text in die Zwischenablage.

**Hinweis**
- Das Log nennt beim Einfügen jetzt Programm, Fensterklasse und Eingabefeld. Klappt es in einer App weiterhin nicht, hilft diese Zeile bei der Analyse.

## 2.2.1 – 21.10.2026

> Service-Update für oneAI: Pre-Check und Autopilot wählen je Modus das schnellste verlässliche Modell und die beste Spracherkennung, Störungen kosten deutlich weniger Wartezeit.

**Neu**
- Pre-Check (Technik): misst auf Knopfdruck alle für dich freigegebenen oneAI-Textmodelle (bis zu 8, fester Beispieltext, Tempo, Antwortverhalten und Qualität) und jede eingerichtete Spracherkennung: oneAI, die Sprachmodelle im oneAI Gateway und Mistral. Für die Spracherkennung spricht Windows einen festen Satz als Testaufnahme, Wortlaut misst Dauer, Ausfälle und Wortfehlerrate. Nie mit deinen Diktaten.
- Autopilot: empfiehlt aus Pre-Check und deinen echten Messwerten je Modus ein Modell (Diktat, Nachricht, Stichpunkte: schnellstes gutes Modell unter 6 s; Englisch mit höherer Qualitätsschwelle; Mail, Prompt, Task, Umschreiben und KI fragen: beste Qualität unter 7 s; Gleichstand EU zuerst) und die schnellste verlässliche Spracherkennung. „Mit Autopilot übernehmen“ setzt alles mit einem Klick, „Zurücksetzen“ nimmt es zurück.
- „Täglich prüfen und übernehmen“ (standardmäßig aus): Pre-Check einmal am Tag im Hintergrund, danach übernimmt der Autopilot die Empfehlung.

**Geändert**
- Störungssperre: Fällt ein Anbieter aus oder antwortet zu langsam, rückt er für 3 Minuten ans Ende der Kette, getrennt für Spracherkennung und Textaufbereitung. Die folgenden Diktate warten nicht erneut auf ihn. Ein Erfolg hebt die Sperre auf, die Live-Ampel zeigt sie an.
- Zeitgrenze der Spracherkennung nach Länge der Aufnahme: Mit Ersatz dahinter 10 s plus Aufnahmedauer (15 bis 60 s) statt pauschal 60 s, der letzte Anbieter bekommt mehr Zeit (60 bis 180 s). Fällt oneAI aus, springt Wortlaut bei kurzen Diktaten so nach Sekunden statt nach einer Minute auf Mistral.
- „Modelle testen“ ist im Pre-Check aufgegangen. Eine von Hand geänderte Modellauswahl ersetzt beim Speichern die Zuordnung des Autopiloten je Modus.
- Datenschutzhinweis um Pre-Check, oneAI Gateway und Störungssperre ergänzt, ohne erneute Bestätigung.

**Hinweis**
- Die oneAI-Spracherkennung (`/api/transcribe`) wählt ihr Modell selbst. Ein bestimmtes Sprachmodell geht nur über das oneAI Gateway (OpenAI-kompatibel, gleiche Adresse und gleicher Schlüssel). Ob deine Organisation dort Sprachmodelle anbietet, prüft der Pre-Check; ohne Gateway bleibt es bei oneAI und Mistral.
- Ohne deutsche Windows-Stimme bewertet der Pre-Check die Spracherkennung nur nach Tempo und Zuverlässigkeit. Die Stimme kommt mit dem Sprachpaket Deutsch inklusive Sprachausgabe (Windows-Einstellungen › Zeit und Sprache).
- Ein fester Wert `grenze_sprache` in `settings.ini` geht der neuen Zeitgrenze weiter vor.

## 2.2.0 – 20.10.2026

> Frag dein Gedächtnis, gib jedem Modus deine eigene Handschrift, sieh auf einen Blick, welches oneAI-Modell wofür taugt, und gib Virenscannern weniger Anlass zum Alarm. Der größere Schritt vor einer längeren Pause.

**Neu**
- KI fragen im Verlauf (Num +): Frage ins Suchfeld schreiben, dann „KI fragen“ oder Strg+Enter, z. B. „Was habe ich Brandt zum Angebot geschrieben?“. Wortlaut sucht zuerst auf diesem PC die passendsten Einträge (seltene Wörter zählen mehr, Neueres leicht vorn, „gestern“, „letzte Woche“ oder „diesen Monat“ grenzen den Zeitraum ein) und schickt nur diese, höchstens 12 und gekürzt, mit der Frage an deinen KI-Anbieter, EU zuerst. Die Antwort nennt ihre Quellen als [1], [2] …, links stehen die Einträge dazu. Nur auf Knopfdruck, beim ersten Mal mit Einverständnis, abschaltbar unter Gedächtnis. Frage und Antwort werden nicht gespeichert.
- Mein Stil je Modus: Für Mail, Nachricht, Diktat, Englisch, Prompt, Task, Stichpunkte und Umschreiben gibt es je ein großes Feld für eigene Anweisungen, z. B. für Mails „Ton stets persönlich, eloquent und nicht zu fordernd“. Die Anweisung geht den eingebauten Vorgaben zu Ton, Form, Länge und Aufbau vor, ändert aber nie Inhalt, Fakten, Zahlen oder Namen. Leer bleibt der eingebaute Standard. Beim Umschreiben geht deine gesprochene Anweisung vor.
- Kürzel per Tastendruck (Tasten): Feld anklicken und das gewünschte Kürzel einfach drücken, z. B. Num / oder Strg+Alt+D, Wortlaut trägt es selbst ein. Entf löscht, Tab springt weiter. Solange ein Feld aktiv ist, ruhen die Wortlaut-Kürzel, damit nicht versehentlich ein Diktat startet. Doppelt belegte und ungeeignete Tasten (z. B. ein einzelner Buchstabe) meldet die Seite sofort.
- oneAI-Modelle transparent (Technik): Jedes für dich freigegebene Modell mit Einordnung schnell, ausgewogen oder gründlich, Hinweis EU und „denkt mit“, wofür es sich eignet, der durchschnittlichen Dauer deiner echten Aufbereitungen und dem letzten Testergebnis. Die Kennzeichnung steht auch direkt in den Auswahlfeldern.
- „Modelle testen“: Ein fester Beispieltext (nie eines deiner Diktate) geht an bis zu 8 Modelle. Gemessen werden Tempo, Antwortverhalten (Einleitung, Markdown, Rückfragen, beantwortet die KI das Diktat, statt es aufzubereiten) und Qualität (Selbstkorrektur, Zahlen, Namen, Füllwörter, Wiederholungen, Form einer Mail), als Punktzahl bis 100. Modelle über 7 Sekunden werden markiert, weil Wortlaut ab 8 Sekunden auf den Ersatz springt.
- Zwei Modelle wählbar: eins für kurze Modi (Diktat, Nachricht, Stichpunkte, Englisch), eins für anspruchsvolle (Mail, Prompt, Task, Umschreiben, KI fragen). „Empfehlung übernehmen“ setzt beide, nach Test oder, ohne Test, nach Modellname mit EU zuerst.
- Ordner-Variante zum Download (`Wortlaut-Ordner.zip`): gleicher Inhalt, aber die Bibliotheken liegen neben der Programmdatei, statt beim Start in den Temp-Ordner entpackt zu werden. Gedacht für PCs mit strengem Virenschutz oder EDR-System. Die Ordner-Variante aktualisiert sich als signiertes Ordner-Paket.

**Geändert**
- Mein Stil neu aufgebaut: oben kompakt Anrede, Länge und Grußformel, darunter „Für alle Texte“ (bisher „Weitere Vorliebe“, jetzt mehrzeilig und bis 1000 statt 300 Zeichen) und die Felder je Modus. Mein Stil speichert jetzt mit allen anderen Einstellungen (Speichern oder Strg+S), die eigenen Knöpfe „Stil speichern“ und „Neu laden“ entfallen.
- Während der Aufnahme fängt Wortlaut Esc und die Modusbuchstaben nicht mehr über einen Tastatur-Hook ab, sondern meldet genau diese Tasten nur für die Dauer der Aufnahme bei Windows an und gibt sie danach sofort frei. Tastatur-Hooks gelten Virenscannern und EDR-Systemen als Keylogger-Merkmal. Großbuchstaben und Kürzel mit Strg, Alt oder Win gehen während der Aufnahme normal durch.
- Tasten warnt, wenn ein Kürzel von Windows reserviert oder schon belegt ist (z. B. Win+Alt+D). Solche Kürzel gehen nur über einen Tastatur-Hook.
- Die Bilanz misst die Verarbeitungsdauer zusätzlich je oneAI-Modell (nur Zahlen).
- Datenschutzhinweis um „KI fragen“ und den Modelltest ergänzt.

**Hinweis**
- Die Einordnung nach Modellname ist eine Schätzung. Messwerte und Test zeigen, wie ein Modell bei dir tatsächlich läuft. Ob ein Modell in der EU läuft, zeigt oneAI verbindlich.
- Mein Stil liegt weiter nur auf diesem PC (`stil.json`). Eigene Fassungen ganzer Prompts über `%APPDATA%\Wortlaut\modi\<name>.txt` funktionieren wie bisher, die Anweisungen je Modus kommen zusätzlich dazu.
- Von Windows reservierte Kürzel wie Win+Alt+D erreichen das Einstellungsfenster nicht und lassen sich daher nicht per Tastendruck aufnehmen. Einfügen per Strg+V ins Feld geht weiterhin.
- Mit 2.2 ruht die Weiterentwicklung vorerst; geplante Punkte stehen in der Roadmap auf der Projektseite.

## 2.1.4 – 19.10.2026

> Wärmer und ruhiger: neue Farben, gut lesbare Auswahl, und die Vorschau zeigt das Statusfenster so, wie du es gerade einstellst.

**Geändert**
- Wärmere Farben: Sandtöne statt kaltem Grau, Karten in warmem Elfenbein statt Weiß, Schrift in dunklem Espresso statt Schwarz, aktive Schalter in Terrakotta. Alle Texte bleiben bei mindestens 4,5:1 Kontrast (WCAG 2.1 AA).
- Die ausgewählte Zeile in Listen (z. B. Mikrofon) ist ein zarter Pfirsichton mit Akzentstrich und dunkler, halbfetter Schrift.
- Die Live-Ampel steht nur noch unter Technik. Verbindung zeigt Schlüssel und Freischaltung und verweist auf die Ampel.
- „Farbe“ heißt jetzt „Farbe des Statusfensters“ und nennt, ob Windows gerade hell oder dunkel ist. „Wie Windows“ folgt dem App-Modus von Windows, die Einstellungen selbst bleiben hell.

**Behoben**
- Das ausgewählte Mikrofon erschien als schwarzer Balken ohne lesbaren Namen.
- Die Vorschau zeigte das Statusfenster immer in der gespeicherten Farbe, egal was gerade gewählt war. Jetzt zeigt sie Farbe, Position und Modusleiste sofort beim Ändern, auch vor dem Speichern.

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
