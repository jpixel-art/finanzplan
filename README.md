# Finanzplan

Finanzplan ist eine Finanzübersicht für den eigenen Computer: Konten, Umsätze, Budgets, Depot, Vermögen und Reports. Die App läuft vollständig lokal. Es gibt kein Benutzerkonto, keine Cloud und kein Tracking.

Dieses Repository dient nur dem Download. Es enthält die fertigen Anwendungen für Windows, macOS und Linux, aber keinen Quellcode.

## Download

Aktuelle Version: **0.1.3** · [alle Versionen](https://github.com/jpixel-art/finanzplan/releases)

| System | Datei | Größe |
|---|---|---|
| Windows 10 und 11 (64 Bit) | [Finanzplan-Windows-x64.exe](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.3/Finanzplan-Windows-x64.exe) (Installationsprogramm) | 5,2 MB |
| macOS 10.15 oder neuer, Apple Silicon (M1 und neuer) | [Finanzplan-macOS-Apple-Silicon.dmg](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.3/Finanzplan-macOS-Apple-Silicon.dmg) | 5,7 MB |
| macOS 10.15 oder neuer, Intel | [Finanzplan-macOS-Intel.dmg](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.3/Finanzplan-macOS-Intel.dmg) | 6,0 MB |
| Linux x64, alle Distributionen | [Finanzplan-Linux-x64.AppImage](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.3/Finanzplan-Linux-x64.AppImage) | 80,8 MB |
| Linux x64, Ubuntu, Debian, Linux Mint | [Finanzplan-Linux-x64.deb](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.3/Finanzplan-Linux-x64.deb) | 6,0 MB |

Welcher Mac? Im Apple-Menü › *Über diesen Mac*: Steht dort „Chip Apple M…“, nimm Apple Silicon, bei „Prozessor Intel…“ die Intel-Version.

Die Dateien sind nicht mit einem kostenpflichtigen Herstellerzertifikat signiert und für macOS nicht von Apple beglaubigt. Windows und macOS warnen deshalb beim ersten Öffnen.

## Installation und Start

### Windows

1. `Finanzplan-Windows-x64.exe` herunterladen und doppelklicken.
2. Erscheint „Der Computer wurde durch Windows geschützt“: auf **Weitere Informationen** und dann **Trotzdem ausführen** klicken.
3. Dem Installationsassistenten folgen. Administratorrechte sind nicht nötig. Die App wird nur für deinen Windows-Benutzer installiert.
4. **Finanzen** über das Startmenü starten.

Fehlt die Microsoft-WebView2-Laufzeit (in Windows 10 und 11 normalerweise vorhanden), lädt der Installer sie automatisch von Microsoft nach.

### macOS

1. Die passende `.dmg`-Datei herunterladen und öffnen.
2. **Finanzen** in den Ordner **Programme** ziehen.
3. **Finanzen** im Ordner Programme öffnen. macOS meldet, dass der Entwickler nicht überprüft werden kann. Dann *Systemeinstellungen › Datenschutz & Sicherheit* öffnen, nach unten scrollen und bei „Finanzen“ auf **Dennoch öffnen** klicken. Bis macOS 14 geht es auch per Rechtsklick auf die App › **Öffnen** › **Öffnen**.
4. Ab dann startet die App normal über das Launchpad oder den Ordner Programme.

### Linux

- **AppImage:** Datei ausführbar machen (Rechtsklick › Eigenschaften › „Als Programm ausführen“ oder `chmod +x Finanzplan-Linux-x64.AppImage`) und doppelklicken. Benötigt FUSE 2. Startet die Datei nicht, fehlt meist genau das: unter Ubuntu 22.04 `sudo apt install libfuse2` ausführen, ab Ubuntu 24.04 `sudo apt install libfuse2t64`.
- **.deb:** `sudo apt install ./Finanzplan-Linux-x64.deb` (installiert die nötigen Systembibliotheken mit). Danach erscheint **Finanzen** im Anwendungsmenü.

### Erster Start

Beim ersten Start wählst du Region und Land. Optional setzt du ein Passwort: Dann wird die Datenbank verschlüsselt, und die App sperrt sich. Ohne dieses Passwort lassen sich die Daten nicht wiederherstellen. Zum Ausprobieren gibt es **Demo-Daten laden** mit erfundenen Beispieldaten.

## Systemanforderungen

| System | Voraussetzungen |
|---|---|
| Windows | Windows 10 oder 11, 64 Bit (x64); Microsoft WebView2 (wird bei Bedarf installiert) |
| macOS | macOS 10.15 (Catalina) oder neuer |
| Linux (AppImage) | x64, glibc 2.35 oder neuer (z. B. Ubuntu 22.04, Debian 12, Fedora 36 und neuer), FUSE 2, grafische Desktop-Umgebung |
| Linux (.deb) | x64, Ubuntu 22.04 oder neuer, Debian 12 oder neuer bzw. darauf basierende Systeme (WebKitGTK 4.1) |

## Berechtigungen

- Die App braucht keine Administratorrechte. Nur die Installation des `.deb`-Pakets läuft über `sudo`.
- Sie liest und schreibt nur ihren eigenen Datenordner und Dateien, die du selbst in einem Öffnen- oder Speichern-Dialog auswählst (z. B. Kontoauszüge, Exporte, Backups).
- Ohne deine Zustimmung baut die App keine Verbindung ins Internet auf. Nur drei Funktionen tun das, und alle musst du ausdrücklich einschalten:
  - **Online-Kurse:** Wertpapierkennungen (ISIN bzw. Börsenkürzel) gehen an Yahoo Finance.
  - **Online-Händlersuche:** Für unbekannte Geschäfte gehen nur deren Name und Ort an OpenStreetMap (keine Beträge, Daten oder Kontonummern).
  - **Synchronisation** mit einem eigenen Server: Die Daten werden vorher Ende-zu-Ende-verschlüsselt.

## Deine Daten

| System | Speicherort |
|---|---|
| Windows | `%APPDATA%\local.finanzen.app\` |
| macOS | `~/Library/Application Support/local.finanzen.app/` |
| Linux | `~/.local/share/local.finanzen.app/` |

Backups liegen im Unterordner `backups`. Gespeichert wird automatisch, auch direkt vor dem Schließen. Alle Daten löschen: in der App unter *Einstellungen › Alle Daten löschen*, oder die App beenden und den Ordner löschen.

**Update:** neue Version herunterladen und über die alte installieren bzw. die alte AppImage-Datei ersetzen. Deine Daten bleiben erhalten. Beim Deinstallieren bleiben sie ebenfalls erhalten, solange du den Datenordner nicht selbst löschst.

## Teststatus von Version 0.1.3

Alle Dateien werden automatisch auf GitHub gebaut und vor der Veröffentlichung auf frisch eingerichteten Systemen installiert und gestartet:

| Datei | Geprüft |
|---|---|
| Windows | Installation, Start, Ersteinrichtung, Demo-Daten, Backup, Schließen und Neustart mit erhaltenen Daten, Verschlüsselung, Sperren und Entsperren |
| macOS Apple Silicon | Installation aus der DMG, Signaturprüfung, zweimaliger Start, Datenbank angelegt und nach Neustart wieder geöffnet |
| macOS Intel | wie Apple Silicon, aber unter Rosetta 2 auf einem Apple-Silicon-Mac. **Nicht auf einem echten Intel-Mac getestet.** |
| Linux AppImage | Start unter Ubuntu 22.04 (virtuelle Anzeige), zweimal, Datenbank angelegt und wieder geöffnet |
| Linux .deb | Installation per `apt` unter Ubuntu 22.04, Start wie beim AppImage |

Bei macOS und Linux wurde die Bedienung der Oberfläche nicht automatisch durchgeklickt. Die App ist auf allen Systemen dieselbe.

## Neu in 0.1.3

- **Private Überweisungen** an und von Freunden und Familie werden automatisch zugeordnet – auch wenn die Bank „Überweisung an/von …“ in das Empfängerfeld schreibt. Überweisungen an dich selbst, aufs Tagesgeld oder in Unterkonten (z. B. Revolut-Pockets, N26-Spaces) zählen weiterhin als Umbuchung, nicht als Ausgabe.
- **Bonuspunkte:** neue Seite für Punkte- und Meilenprogramme wie Revolut RevPoints, PAYBACK oder Miles & More – Stand, Verlauf, Einlösungen und geschätzter Gegenwert, getrennt von Einnahmen und Ausgaben. Die Punkte trägst du selbst ein (Banken liefern sie nicht im Kontoauszug).
- **PDF-Import:** weitere Spaltenformate von Neobanken (z. B. „Money out / Money in“).

## Neu in 0.1.2

- **Bessere automatische Kategorien:** erkennt Buchungstexte vieler Banken und Sprachen (z. B. „Kartenbezahlung“, „Card payment“, „PAIEMENT CB“), andere Schreibweisen bekannter Händler und Einzahlungen auf deinen eigenen Namen (dann eine Umbuchung, keine Einnahme). Jede automatische Kategorie zeigt Grund und Sicherheit; Unklares bleibt zur Prüfung, statt geraten zu werden. Buchungen ohne Kategorie werden nach dem Update einmal neu geprüft.
- **PDF-Import:** mehrseitige Auszüge, Beträge wie „1250,00“, niederländische und englische Formate; verständliche Meldungen bei gescannten oder passwortgeschützten PDFs; Zusammenfassung nach dem Import.
- **Optional:** Online-Händlersuche über OpenStreetMap (standardmäßig aus).
- Sicherheit: CSV-Exporte sind gegen Formeln in fremden Buchungstexten geschützt.

## Bekannte Einschränkungen

- Keine Herstellersignatur: Warnung beim ersten Start unter Windows und macOS (siehe oben).
- Kein automatisches Update. Neue Versionen erscheinen auf der Release-Seite.
- Linux: getestet unter Ubuntu 22.04. Andere Distributionen sind nicht getestet. Das AppImage braucht FUSE 2.

## Dateien prüfen

| Datei | SHA-256 |
|---|---|
| Finanzplan-Windows-x64.exe | `ba36a8b034ea8c854e7f71dc994a172395462f52676598986c900680f61bae02` |
| Finanzplan-macOS-Apple-Silicon.dmg | `4dda74e92ab0404a9c5ff1bed40a5288f6e832199a035cdbe1d6b504ddb387a1` |
| Finanzplan-macOS-Intel.dmg | `a15da3e3a7b02760838a5df2024056794585b793db2b37704cdf993c360ac369` |
| Finanzplan-Linux-x64.AppImage | `2a3eb72fb41ab608a8a6465b9ce34f0c09d65219d097ed4a984de66e28f0a789` |
| Finanzplan-Linux-x64.deb | `7d0f4e0de2ae329cdf52f018f7bfc2f99955e63b3bfff29e06bb8205b4ea890c` |

Prüfen unter Windows: `Get-FileHash <Datei>` (PowerShell) · macOS: `shasum -a 256 <Datei>` · Linux: `sha256sum <Datei>`
