# Wortlaut

**Sprechen statt tippen.** Wortlaut ist eine Windows-App für Diktate: Du sprichst, eine KI bereitet den Text auf, und er landet direkt in dem Programm, in dem du gerade schreibst – E-Mail, Chat, Dokument, Ticket oder KI-Prompt.

> Dieses Repository ist der **öffentliche Release-Kanal**. Es enthält ausschließlich die fertigen Programmdateien und Prüfsummen, keinen Quellcode.

---

## Inhalt

- [Funktionen](#funktionen)
- [Voraussetzungen](#voraussetzungen)
- [Installation](#installation)
- [Download prüfen](#download-prüfen)
- [Einrichtung](#einrichtung)
- [Updates](#updates)
- [Datenschutz](#datenschutz)
- [Lizenz und Nutzungsbedingungen](#lizenz-und-nutzungsbedingungen)
- [Haftungsausschluss](#haftungsausschluss)
- [Marken](#marken)
- [Kontakt](#kontakt)
- [English summary](#english-summary)

---

## Funktionen

| Modus | Was passiert |
|---|---|
| **Diktat** | Gesprochenes wird zu sauberem Text: Füllwörter raus, Satzzeichen rein, Selbstkorrekturen berücksichtigt. |
| **Englisch** | Wie Diktat, Ergebnis in US-Englisch. |
| **Prompt** | Formuliert eine gesprochene Anweisung als klaren Prompt für KI-Chats. |
| **Nachricht / Mail** | Kurze Chatnachricht oder E-Mail mit Anrede und Gruß. |
| **Stichpunkte / Task** | Zusammenfassung als Stichpunkte oder als Aufgabenbeschreibung. |
| **Umschreiben** | Markierten Text per Sprachanweisung umformulieren. |

Dazu: persönliches Glossar für Fachbegriffe und Namen, persönlicher Stil (Anrede, Gruß, Länge), lokaler Verlauf der letzten Ergebnisse, frei belegbare Tastenkürzel.

**KI-Anbieter nach Wahl:** oneAI, OpenAI, Anthropic (Claude), Google Gemini und Mistral. Fällt der erste Anbieter aus oder antwortet zu langsam, übernimmt automatisch der nächste eingerichtete.

---

## Voraussetzungen

| | |
|---|---|
| Betriebssystem | Windows 10 oder 11, 64 Bit |
| Laufzeit | keine zusätzliche Installation nötig – die .NET-Laufzeit ist in der Programmdatei enthalten |
| KI-Zugang | Ein eigener API-Schlüssel bei mindestens einem Anbieter, der Sprache erkennt (oneAI, OpenAI, Gemini oder Mistral) |
| Mikrofon | beliebig, Headset empfohlen |

Für Claude (Anthropic) gilt: Der Anbieter verarbeitet nur Text. Er eignet sich daher als Ersatz für die Textaufbereitung, nicht für die Spracherkennung.

---

## Installation

1. Unter [**Releases**](../../releases/latest) die Datei `Wortlaut.exe` herunterladen.
2. Einen eigenen Ordner anlegen, in dem du Schreibrechte hast, z. B. `%LOCALAPPDATA%\Programs\Wortlaut`, und die Datei dorthin verschieben. In diesem Ordner kann sich Wortlaut später selbst aktualisieren.
3. `Wortlaut.exe` starten. Das Symbol erscheint im Infobereich der Taskleiste. Der erste Start kann einige Sekunden dauern, weil die eingebaute Laufzeit vorbereitet wird.

**Hinweis zu Windows SmartScreen:** Die Programmdatei ist derzeit nicht digital signiert. Windows kann deshalb beim ersten Start „Der Computer wurde durch Windows geschützt“ anzeigen. Prüfe zuerst die Prüfsumme (siehe unten) und wähle dann *Weitere Informationen → Trotzdem ausführen*.

---

## Download prüfen

Zu jeder Version gehört die Datei `Wortlaut.exe.sha256` mit der SHA-256-Prüfsumme. So prüfst du sie in PowerShell:

```powershell
(Get-FileHash .\Wortlaut.exe -Algorithm SHA256).Hash.ToLower()
Get-Content .\Wortlaut.exe.sha256
```

Beide Werte müssen übereinstimmen. Weichen sie ab, die Datei nicht starten und löschen.

---

## Einrichtung

Beim ersten Start öffnet sich **Meine Schlüssel**:

1. Schlüssel für mindestens einen KI-Anbieter eintragen. Bei oneAI zusätzlich die Adresse der eigenen oneAI-Instanz.
2. **Prüfen und speichern**. Wortlaut testet danach jeden eingerichteten Anbieter einmal.
3. Diktieren: Standardkürzel ist **Num /** auf dem Ziffernblock (Start und Stopp). Alle Kürzel lassen sich in den Einstellungen ändern.

Die Schlüssel liegen ausschließlich in der Windows-Anmeldeinformationsverwaltung des angemeldeten Benutzers.

---

## Updates

Wortlaut prüft beim Start und danach alle drei Stunden, ob in diesem Repository eine neuere Version vorliegt. Ein Update wird nur nach Rückfrage installiert. Vor der Installation vergleicht Wortlaut die SHA-256-Prüfsumme; stimmt sie nicht, wird das Update verworfen.

Die Versionshistorie steht in [CHANGELOG.md](CHANGELOG.md) und bei den einzelnen [Releases](../../releases).

---

## Datenschutz

Kurz gefasst – ausführlich in [DATENSCHUTZ.md](DATENSCHUTZ.md):

- Aufnahme und Text gehen **nur während eines Diktats** und **direkt** an den KI-Anbieter, den du selbst eingerichtet hast. Ein Server des Herausgebers ist nicht dazwischengeschaltet.
- Glossar, Stil, Einstellungen und Verlauf liegen **nur lokal** auf deinem PC. Der Verlauf ist verschlüsselt und wird nach 24 Stunden gelöscht; er lässt sich abschalten.
- Die Logdatei enthält keine Diktatinhalte.
- Für die Update-Prüfung ruft Wortlaut die öffentliche Schnittstelle von GitHub auf.

Für die Verarbeitung durch den gewählten KI-Anbieter gelten dessen Bedingungen. Bei dienstlicher Nutzung kläre vorab, welche Anbieter dein Arbeitgeber zulässt.

---

## Lizenz und Nutzungsbedingungen

Wortlaut ist **kein Open-Source-Projekt**. Die Nutzung ist kostenlos; es gelten die [Nutzungsbedingungen](LICENSE.md).

Wortlaut enthält Komponenten Dritter unter eigenen Lizenzen (u. a. die Schriften Inter und Instrument Serif unter der SIL Open Font License, NAudio unter der MIT-Lizenz). Details: [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

---

## Haftungsausschluss

Wortlaut wird unentgeltlich und **ohne Gewähr** bereitgestellt. KI-Ergebnisse können Fehler enthalten: Lies den Text vor dem Absenden, du bleibst für ihn verantwortlich. Diktiere keine besonders sensiblen Daten (z. B. Gesundheitsdaten), wenn es nicht nötig ist, und nimm nur deine eigene Stimme auf. Die vollständige Regelung steht in den [Nutzungsbedingungen](LICENSE.md).

---

## Marken

oneAI, OpenAI, Anthropic, Claude, Google, Gemini, Mistral, ClickUp, Windows und .NET sind Marken oder eingetragene Marken ihrer jeweiligen Inhaber. Wortlaut steht in keiner Verbindung zu diesen Unternehmen und wird von ihnen weder unterstützt noch geprüft.

---

## Kontakt

- **Feedback und Fehler:** direkt in der App über *Tray → Feedback senden*
- **Sicherheitslücken:** bitte nicht öffentlich melden, sondern wie in [SECURITY.md](SECURITY.md) beschrieben
- **Herausgeber:** Thomas Oesterle

---

## English summary

**Wortlaut** is a Windows dictation app: speak, an AI cleans up the text, and it is pasted into the app you are working in. This repository is the **public release channel** and contains only signed-off binaries and SHA-256 checksums, no source code.

- **Requirements:** Windows 10/11 x64 (no separate .NET installation needed, the runtime is built in), your own API key for at least one speech-capable provider (oneAI, OpenAI, Gemini or Mistral).
- **Privacy:** audio and text are sent only while dictating and directly to the provider you configured. Glossary, style, settings and history stay on your PC.
- **Updates:** checked against this repository at start-up and every three hours, installed only after confirmation and checksum verification.
- **License:** freeware, not open source – see [LICENSE.md](LICENSE.md) (German). Third-party components: [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
- **Disclaimer:** provided free of charge and without warranty. AI output may contain errors; review before sending.

© 2026 Thomas Oesterle. Alle Rechte vorbehalten.
