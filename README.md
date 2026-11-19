# Messe Navigator 3D Hannover – Neustart (V0.9)

**Einfacher Neustart, ohne GitHub Actions, ohne Workflow, ohne GitHub-Fork.**

## Hochladen (nur eine Datei)
1. Auf GitHub ein **neues, leeres, öffentliches Repository** anlegen, z. B. `messe-navigator-neustart`.
2. Die `index.html` aus diesem ZIP **direkt ins Hauptverzeichnis** von `main` laden (nicht die ZIP-Datei selbst). `README.md` ist optional.
3. GitHub → **Settings → Pages → Deploy from a branch → main → /(root) → Save**.
4. Anschließend die GitHub-Pages-Adresse öffnen.

**Keine `.github/workflows`-Datei im Paket.** Der Working-Copy-Fehler mit fehlender `workflow`-Berechtigung kann dadurch nicht erneut von dieser Datei ausgelöst werden.

## Was dieses Paket kann
- Eigenständige stilisierte WebGL-3D-Darstellung von Straßen, Gehwegen, Radwegen, Plätzen und Grünflächen.
- Vogelperspektive + Ich-Perspektive; Maus, Touch, iPhone-Joystick.
- **Keine Gebäude und keine Hallen.** Kein 2D-Kartenbild als Hintergrund.
- Eingelesene Wege haben tatsächliche OSM-Objekt-IDs und echte geografische Linienkoordinaten.
- Die Webseite fragt die offenen OSM-Daten **beim ersten Start im Browser** ab und speichert erfolgreich geladene Daten in IndexedDB. Beim nächsten Start auf demselben Gerät werden sie wiederverwendet.
- Optional: Nach erfolgreichem Abruf kann unter ⓘ eine `terrain.json` exportiert werden. Wenn sie später unter `data/terrain.json` im Repository liegt, können alle Besucher diese **direkt** nutzen, ohne OSM-Server beim ersten Start anzufragen. Dafür ist weder GitHub Actions noch ein Skript nötig.

## Wichtige ehrliche Einschränkung
**Das ZIP enthält noch keine vollständige, lokal eingebundene Karte der echten Messewege.** Die Rohdaten konnten in dieser Entwicklungsumgebung nicht abgerufen werden. Daher braucht das Projekt für den ersten Datenimport Internet und einen erreichbaren OSM-Datenserver. Schlägt der Abruf fehl, wird eine klare Fehlermeldung statt erfundener Weggeometrie angezeigt. Eine vollständige Offline-Nutzung für alle Geräte ist erst mit einer eingebundenen `terrain.json` möglich.

Die Straßen **sind nicht 1:1 vermessen**: OpenStreetMap-Wegachsen sind georeferenziert, aber Vollständigkeit, tatsächliche Breiten, Höhenniveaus, Beläge, Zugangsrechte und Details des Messegeländes müssen anhand freigegebener Bestandspläne überprüft werden. Falls keine Breite vorhanden ist, verwendet die Darstellung reine Visualisierungsbreiten. Es handelt sich ausdrücklich nicht um eine freigegebene Besuchernavigation.

## Dateien
- `index.html` – vollständige Anwendung, keine externen JavaScript-Bibliotheken.
- `README.md` – Anleitung.

## Quelle/Lizenz
Datengrundlage: © [OpenStreetMap-Mitwirkende](https://www.openstreetmap.org/copyright), Open Database License (ODbL). OpenStreetMap-Daten sind nicht automatisch amtlich verifiziert.
