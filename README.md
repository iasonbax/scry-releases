# Scry

**Scry** ist ein passiver Netzwerkmonitor für eigene ChatGPT-/Codex-Verbindungen.
Der installierte App-Name lautet aktuell **Chatlive**. Das Projekt soll später
in mockd integriert werden.

## Download

[Installer und Release-Notizen herunterladen](https://github.com/iasonbax/scry-releases/releases).

Wähle das Asset `chatlive-X.Y.Z-macos.pkg`. Es installiert die native Mac-App und
ihren Capture-Helfer. Das Paket funktioniert auf Apple Silicon und Intel ab macOS 12.
Homebrew, ein vorhandenes Python und Xcode sind für die Installation nicht nötig.
Beim ersten Start werden private Runtimes geladen; dafür ist Internet erforderlich.

Aktuelle Releases sind **Previews mit lokaler Ad-hoc-Signatur** und noch nicht von
Apple notarisiert. Gatekeeper kann heruntergeladene Builds zurückweisen.

Die Datei `SHA256SUMS` enthält die Prüfsumme des Installers:

```bash
shasum -a 256 -c SHA256SUMS
```

## Benutzen

1. Den Installer öffnen und die einmalige Administratorbestätigung abschließen.
2. Chatlive aus „Programme“ öffnen, die gewünschten Apps auswählen und „Monitor starten“ wählen.
3. Chat und Diagnose in der Oberfläche mitlesen. Weitere Monitor-Starts brauchen kein sudo-Passwort.

Du startest und beendest die überwachten Apps selbst. ⌘Q beendet die Chatlive-Oberfläche;
der Monitor läuft weiter. Wiederöffnen verbindet die Oberfläche mit dem laufenden
Monitor. „Monitor stoppen“ beendet die Erfassung. Abmelden oder ein Neustart beendet
die Monitorsitzung.

Logs und Runtimes liegen unter `~/Library/Application Support/chatlive`. Das
App-Menü bietet eine Deinstallation mit oder ohne Entfernung der eigenen Daten.

Der Monitor verwendet keinen Proxy und verändert keine Zertifikate. Für lesbare
Chattexte sind passende TLS-Keys und ausreichend erfasste Verbindungsdaten nötig.
Verbindungen ohne passende Keys bleiben verschlüsselt. Der passive Mitschnitt
blockiert keine Nachrichten vor dem Versand. Claude wird noch nicht unterstützt.

Dieses Repository enthält Download-Informationen und veröffentlichte Installer.
Die Entwicklung findet in einem separaten privaten Repository statt. Die automatisch
von GitHub angebotenen „Source code“-Archive enthalten nur dieses Download-Repository.
