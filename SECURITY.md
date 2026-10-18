# Sicherheit

## Unterstützte Versionen

Sicherheitskorrekturen gibt es nur für die jeweils **neueste** Version unter [Releases](../../releases/latest). Wortlaut aktualisiert sich nach Rückfrage selbst.

## Echtheit einer Datei prüfen

Jede Version wird automatisiert gebaut und doppelt abgesichert veröffentlicht:

- **Prüfsumme** `Wortlaut.exe.sha256` (SHA-256): erkennt beschädigte oder vertauschte Downloads (siehe [README](README.md#download-prüfen)).
- **Signatur** `Wortlaut.exe.sig` (ECDSA P-256 über SHA-256, ab Version 2.1.0): erkennt Manipulation. Der passende öffentliche Schlüssel liegt hier im Repository ([signatur.pub.pem](signatur.pub.pem)) und ist zusätzlich fest in Wortlaut eingebaut. Der private Schlüssel verlässt die automatische Veröffentlichung nie.

Lade Wortlaut ausschließlich aus diesem Repository oder über die Projektseite herunter. Beim automatischen Update prüft Wortlaut Prüfsumme **und** Signatur selbst und verwirft jede Datei, die nicht passt. Die Update-Quelle ist fest eingebaut und lässt sich nicht umstellen.

Von Hand prüfen, zum Beispiel mit OpenSSL aus Git für Windows (alle drei Dateien im selben Ordner):

```
openssl dgst -sha256 -verify signatur.pub.pem -signature Wortlaut.exe.sig Wortlaut.exe
```

Erwartet wird `Verified OK`.

Hinweis: Diese Signatur ist kein Windows-Codesignaturzertifikat. Beim ersten Start der EXE kann Windows SmartScreen daher weiterhin warnen. Ohne diese Warnung installiert sich Wortlaut über den Microsoft Store, sobald die Store-Version verfügbar ist.

## Sicherheitslücke melden

Bitte melde vermutete Sicherheitslücken **nicht öffentlich** (kein Issue, kein Kommentar), sondern vertraulich:

- über GitHub: Reiter **Security → Report a vulnerability** (sofern aktiviert), oder
- per E-Mail an den Herausgeber über die Feedbackfunktion der App mit dem Hinweis „Sicherheit“.

Hilfreich sind: betroffene Version, Schritte zum Nachvollziehen und mögliche Auswirkungen. Bitte schicke **keine API-Schlüssel** oder Diktatinhalte mit.
