# Finanzplan für Windows

Finanzplan ist eine Finanzübersicht für den eigenen Computer: Konten, Umsätze, Budgets, Depot, Vermögen und Reports. Die App läuft vollständig lokal. Es gibt kein Benutzerkonto, keine Cloud und kein Tracking.

Dieses Repository dient nur dem Download. Es enthält die fertige Windows-Anwendung als Installationsdatei, aber keinen Quellcode.

## Download

**[Finanzen_0.1.1_x64-setup.exe herunterladen](https://github.com/jpixel-art/finanzplan/releases/download/v0.1.1/Finanzen_0.1.1_x64-setup.exe)** (5,2 MB) · [alle Versionen](https://github.com/jpixel-art/finanzplan/releases)

Voraussetzung: Windows 10 oder 11, 64 Bit.

## Installation und Start

1. `Finanzen_0.1.1_x64-setup.exe` herunterladen und doppelklicken.
2. Erscheint „Der Computer wurde durch Windows geschützt“: auf **Weitere Informationen** und dann **Trotzdem ausführen** klicken. Die Warnung erscheint, weil die Datei nicht mit einem kostenpflichtigen Herstellerzertifikat signiert ist.
3. Dem Installationsassistenten folgen. Administratorrechte sind nicht nötig. Die App wird nur für deinen Windows-Benutzer installiert.
4. **Finanzen** über das Startmenü starten.

Fehlt die Microsoft-WebView2-Laufzeit (in Windows 10 und 11 normalerweise vorhanden), lädt der Installer sie automatisch von Microsoft nach.

Beim ersten Start wählst du Region und Land. Optional setzt du ein Passwort: Dann wird die Datenbank verschlüsselt, und die App sperrt sich. Ohne dieses Passwort lassen sich die Daten nicht wiederherstellen. Zum Ausprobieren gibt es **Demo-Daten laden** mit erfundenen Beispieldaten.

## Deine Daten

- Alle Daten bleiben auf deinem Computer, in `%APPDATA%\local.finanzen.app\`. Backups liegen dort im Unterordner `backups`.
- Ohne deine Zustimmung baut die App keine Verbindung ins Internet auf. Nur zwei Funktionen tun das, und beide musst du ausdrücklich einschalten:
  - **Online-Kurse:** Wertpapierkennungen (ISIN bzw. Börsenkürzel) gehen an Yahoo Finance.
  - **Synchronisation** mit einem eigenen Server: Die Daten werden vorher Ende-zu-Ende-verschlüsselt.
- Gespeichert wird automatisch, auch direkt vor dem Schließen. Nach einem Neustart sind alle Daten wieder da.
- Alle Daten löschen: in der App unter *Einstellungen › Alle Daten löschen*, oder die App beenden und den oben genannten Ordner löschen.

## Update und Deinstallation

- **Update:** neue Version herunterladen und über die alte installieren. Deine Daten bleiben erhalten.
- **Deinstallieren:** *Einstellungen › Apps › Installierte Apps › Finanzen*. Deine Daten bleiben dabei erhalten, solange du den Datenordner nicht selbst löschst.

## Datei prüfen

SHA-256 von `Finanzen_0.1.1_x64-setup.exe`:

```
e1731aaa995fd2fdb70a1597bb1a76ee34dceb13b85765ddb47b5df7efec153b
```

In PowerShell prüfen: `Get-FileHash .\Finanzen_0.1.1_x64-setup.exe`
