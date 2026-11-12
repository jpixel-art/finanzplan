# Finanzplan

Finanzplan ist eine Finanzübersicht für den eigenen Computer: Konten, Umsätze, Budgets, Depot, Vermögen und Reports. Die App läuft vollständig lokal. Es gibt kein Benutzerkonto, keine Cloud und kein Tracking.

Dieses Repository dient nur dem Download. Es enthält die fertigen Anwendungen für Windows, macOS und Linux, aber keinen Quellcode.

## Download

Aktuelle Version: **0.2.0** · [alle Versionen](https://github.com/jpixel-art/finanzplan/releases)

| System | Datei | Größe |
|---|---|---|
| Windows 10 und 11 (64 Bit) | [Finanzplan-Windows-x64.exe](https://github.com/jpixel-art/finanzplan/releases/download/v0.2.0/Finanzplan-Windows-x64.exe) (Installationsprogramm) | 5,3 MB |
| macOS 10.15 oder neuer, Apple Silicon (M1 und neuer) | [Finanzplan-macOS-Apple-Silicon.dmg](https://github.com/jpixel-art/finanzplan/releases/download/v0.2.0/Finanzplan-macOS-Apple-Silicon.dmg) | 5,8 MB |
| macOS 10.15 oder neuer, Intel | [Finanzplan-macOS-Intel.dmg](https://github.com/jpixel-art/finanzplan/releases/download/v0.2.0/Finanzplan-macOS-Intel.dmg) | 6,1 MB |
| Linux x64, alle Distributionen | [Finanzplan-Linux-x64.AppImage](https://github.com/jpixel-art/finanzplan/releases/download/v0.2.0/Finanzplan-Linux-x64.AppImage) | 80,9 MB |
| Linux x64, Ubuntu, Debian, Linux Mint | [Finanzplan-Linux-x64.deb](https://github.com/jpixel-art/finanzplan/releases/download/v0.2.0/Finanzplan-Linux-x64.deb) | 6,0 MB |

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
- Ohne deine Zustimmung baut die App keine Verbindung ins Internet auf. Nur vier Funktionen tun das, und alle musst du ausdrücklich einschalten:
  - **Online-Kurse:** Wertpapierkennungen (ISIN bzw. Börsenkürzel) gehen an Yahoo Finance.
  - **Online-Händlersuche:** Für unbekannte Geschäfte gehen nur deren Name und Ort an OpenStreetMap (keine Beträge, Daten oder Kontonummern).
  - **Karte:** Für den Kartenhintergrund werden Kartenbilder von OpenStreetMap geladen. Der Server sieht die angesehenen Kartenausschnitte, aber keine Buchungen, Beträge oder Namen.
  - **Synchronisation** mit einem eigenen Server: Die Daten werden vorher Ende-zu-Ende-verschlüsselt.

## Deine Daten

| System | Speicherort |
|---|---|
| Windows | `%APPDATA%\local.finanzen.app\` |
| macOS | `~/Library/Application Support/local.finanzen.app/` |
| Linux | `~/.local/share/local.finanzen.app/` |

Backups liegen im Unterordner `backups`. Gespeichert wird automatisch, auch direkt vor dem Schließen. Alle Daten löschen: in der App unter *Einstellungen › Alle Daten löschen*, oder die App beenden und den Ordner löschen.

**Update:** neue Version herunterladen und über die alte installieren bzw. die alte AppImage-Datei ersetzen. Deine Daten bleiben erhalten. Beim Deinstallieren bleiben sie ebenfalls erhalten, solange du den Datenordner nicht selbst löschst.

## Teststatus von Version 0.2.0

Alle Dateien werden automatisch auf GitHub gebaut und vor der Veröffentlichung auf frisch eingerichteten Systemen installiert und gestartet:

| Datei | Geprüft |
|---|---|
| Windows | Installation, Start, Ersteinrichtung, Demo-Daten, Backup, Schließen und Neustart mit erhaltenen Daten, Verschlüsselung, Sperren und Entsperren |
| macOS Apple Silicon | Installation aus der DMG, Signaturprüfung, zweimaliger Start, Datenbank angelegt und nach Neustart wieder geöffnet |
| macOS Intel | wie Apple Silicon, aber unter Rosetta 2 auf einem Apple-Silicon-Mac. **Nicht auf einem echten Intel-Mac getestet.** |
| Linux AppImage | Start unter Ubuntu 22.04 (virtuelle Anzeige), zweimal, Datenbank angelegt und wieder geöffnet |
| Linux .deb | Installation per `apt` unter Ubuntu 22.04, Start wie beim AppImage |

Bei macOS und Linux wurde die Bedienung der Oberfläche nicht automatisch durchgeklickt. Die App ist auf allen Systemen dieselbe. Online-Kurse und die Karte wurden mit nachgebildeten Antworten getestet, nicht gegen die echten Dienste.

## Neu in 0.2.0

- **Depot:** Ein Klick auf eine Position zeigt den Kursverlauf mit Markern für jeden Kauf und Verkauf, dem Durchschnittskaufkurs und der Kaufhistorie. Mit eingeschalteten Online-Kursen von 1 Tag bis Gesamt, sonst aus den gespeicherten Kursen. Neu ist außerdem die Entwicklung des Depotwerts gegenüber dem eingesetzten Geld. Online-Kurse können je nach Börse verzögert sein; die Abrufzeit steht dabei.
- **Karte:** zeigt, wo du Geld ausgegeben hast – für Geschäfte, deren Standort die Online-Händlersuche eindeutig findet. Bei mehreren Treffern wählst du den richtigen Ort. Händlersuche und Kartenbilder sind getrennt einzuschalten und standardmäßig aus.
- **Neues Erscheinungsbild:** durchscheinende Flächen, weichere Formen, sanfte Übergänge und animierte Kennzahlen, hell und dunkel. Die Systemeinstellungen „Bewegung reduzieren“ und „Transparenz reduzieren“ werden beachtet.

## Neu in 0.1.4

- **Sicherere Passwörter:** Neue Passwörter für die verschlüsselte Datenbank dürfen nicht mehr leicht zu erraten sein (z. B. „passwort123“, „1234567890“, „abcdefghij“). Am besten mehrere zufällige Wörter. Bestehende Passwörter gelten weiter.
- **Synchronisations-Server:** Wer einen eigenen Server betreibt, sieht fehlgeschlagene Anmeldungen und Sperren jetzt im Protokoll – ohne IP-Adressen oder Kontodaten.

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
| Finanzplan-Windows-x64.exe | `871db2b2b45a3955a7189a875f6a9a235f43882bf6f896ed0329955c97187c05` |
| Finanzplan-macOS-Apple-Silicon.dmg | `a99c70fca34c4fd6b3c675270c1b9ec7ae765546d7a675890c1c78b75e253319` |
| Finanzplan-macOS-Intel.dmg | `f4731e99977d16244733023be8fbbe0e7c32b814e0ad186c0ad86bd92cb46bfe` |
| Finanzplan-Linux-x64.AppImage | `e3106db04bddb44abb48444d500476ff47a3e06939923fa80cc47b70d9857f38` |
| Finanzplan-Linux-x64.deb | `cc6fa7cb202b9a1c823e264df4f3d6a6967433ca4a362cb648113013df8bf86a` |

Prüfen unter Windows: `Get-FileHash <Datei>` (PowerShell) · macOS: `shasum -a 256 <Datei>` · Linux: `sha256sum <Datei>`
