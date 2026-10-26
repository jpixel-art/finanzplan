# Finanzplan

Finanzplan ist eine Finanzübersicht für den eigenen Computer: Konten, Umsätze, Budgets, Depot, Vermögen und Reports. Die App läuft vollständig lokal. Es gibt kein Benutzerkonto, keine Cloud und kein Tracking.

Dieses Repository dient nur dem Download. Es enthält die fertigen Anwendungen für Windows, macOS und Linux, aber keinen Quellcode.

## Download

Aktuelle Version: **0.1.1** · [alle Versionen](https://github.com/jpixel-art/finanzplan/releases)

| System | Datei | Größe |
|---|---|---|
| Windows 10 und 11 (64 Bit) | [Finanzplan-Windows-x64.exe](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.1/Finanzplan-Windows-x64.exe) (Installationsprogramm) | 5,2 MB |
| macOS 10.15 oder neuer, Apple Silicon (M1 und neuer) | [Finanzplan-macOS-Apple-Silicon.dmg](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.1/Finanzplan-macOS-Apple-Silicon.dmg) | 5,7 MB |
| macOS 10.15 oder neuer, Intel | [Finanzplan-macOS-Intel.dmg](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.1/Finanzplan-macOS-Intel.dmg) | 6,0 MB |
| Linux x64, alle Distributionen | [Finanzplan-Linux-x64.AppImage](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.1/Finanzplan-Linux-x64.AppImage) | 80,8 MB |
| Linux x64, Ubuntu, Debian, Linux Mint | [Finanzplan-Linux-x64.deb](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.1/Finanzplan-Linux-x64.deb) | 6,0 MB |

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
- Ohne deine Zustimmung baut die App keine Verbindung ins Internet auf. Nur zwei Funktionen tun das, und beide musst du ausdrücklich einschalten:
  - **Online-Kurse:** Wertpapierkennungen (ISIN bzw. Börsenkürzel) gehen an Yahoo Finance.
  - **Synchronisation** mit einem eigenen Server: Die Daten werden vorher Ende-zu-Ende-verschlüsselt.

## Deine Daten

| System | Speicherort |
|---|---|
| Windows | `%APPDATA%\local.finanzen.app\` |
| macOS | `~/Library/Application Support/local.finanzen.app/` |
| Linux | `~/.local/share/local.finanzen.app/` |

Backups liegen im Unterordner `backups`. Gespeichert wird automatisch, auch direkt vor dem Schließen. Alle Daten löschen: in der App unter *Einstellungen › Alle Daten löschen*, oder die App beenden und den Ordner löschen.

**Update:** neue Version herunterladen und über die alte installieren bzw. die alte AppImage-Datei ersetzen. Deine Daten bleiben erhalten. Beim Deinstallieren bleiben sie ebenfalls erhalten, solange du den Datenordner nicht selbst löschst.

## Teststatus von Version 0.1.1

Alle Dateien werden automatisch auf GitHub gebaut und vor der Veröffentlichung auf frisch eingerichteten Systemen installiert und gestartet:

| Datei | Geprüft |
|---|---|
| Windows | Installation, Start, Ersteinrichtung, Demo-Daten, Backup, Schließen und Neustart mit erhaltenen Daten, Verschlüsselung, Sperren und Entsperren |
| macOS Apple Silicon | Installation aus der DMG, Signaturprüfung, zweimaliger Start, Datenbank angelegt und nach Neustart wieder geöffnet |
| macOS Intel | wie Apple Silicon, aber unter Rosetta 2 auf einem Apple-Silicon-Mac. **Nicht auf einem echten Intel-Mac getestet.** |
| Linux AppImage | Start unter Ubuntu 22.04 (virtuelle Anzeige), zweimal, Datenbank angelegt und wieder geöffnet |
| Linux .deb | Installation per `apt` unter Ubuntu 22.04, Start wie beim AppImage |

Bei macOS und Linux wurde die Bedienung der Oberfläche nicht automatisch durchgeklickt. Die App ist auf allen Systemen dieselbe.

## Bekannte Einschränkungen

- Keine Herstellersignatur: Warnung beim ersten Start unter Windows und macOS (siehe oben).
- Kein automatisches Update. Neue Versionen erscheinen auf der Release-Seite.
- Linux: getestet unter Ubuntu 22.04. Andere Distributionen sind nicht getestet. Das AppImage braucht FUSE 2.

## Dateien prüfen

| Datei | SHA-256 |
|---|---|
| Finanzplan-Windows-x64.exe | `e1731aaa995fd2fdb70a1597bb1a76ee34dceb13b85765ddb47b5df7efec153b` |
| Finanzplan-macOS-Apple-Silicon.dmg | `bb76acc32ec61e7789a2e6e483e36210617ea7015ef45f0a5ad10f9288c27767` |
| Finanzplan-macOS-Intel.dmg | `fafa28a178d03b02fdc0fa8c5b0d15f1b834e2c47bff9df182bbd4e0656bcd34` |
| Finanzplan-Linux-x64.AppImage | `53d441ed876b0c60931785d91673b5561a721ff56e7dda821711c73e2db8baf4` |
| Finanzplan-Linux-x64.deb | `84da3983830a92c421cc4f24b333cbee1cbea0236f117cb7957e76ffbaead4aa` |

Prüfen unter Windows: `Get-FileHash <Datei>` (PowerShell) · macOS: `shasum -a 256 <Datei>` · Linux: `sha256sum <Datei>`
