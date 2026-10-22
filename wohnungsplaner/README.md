# Wohnungsplaner 3D

Einzelne HTML-Datei (`index.html`) zum Nachzeichnen eines Grundrisses und zum Einrichten der Wohnung in 2D und 3D.
Gerendert wird mit [three.js](https://threejs.org/) r160. three.js wird beim Öffnen von `cdn.jsdelivr.net` geladen, dafür ist eine Internetverbindung nötig.

## Start

`index.html` im Browser öffnen (Doppelklick). Eine Installation ist nicht nötig.

## Ablauf

1. **Grundriss-Bild → „Laden…“**: Bild des Grundrisses wählen (z. B. Foto oder Scan, PNG oder JPG).
2. **Maßstab**: Zwei Punkte mit bekanntem Abstand anklicken, zum Beispiel die Enden einer bemaßten Wand. Danach die echte Länge in cm eingeben.
3. **Wand**: Wände nachzeichnen. Jeder Klick setzt einen Punkt. Doppelklick, Enter oder Esc beendet den Zug. Das Tool fängt an vorhandenen Wandenden und an 45°-Winkeln; mit gedrückter Shift-Taste wird nicht gefangen.
4. **Tür / Fenster**: Auf eine Wand klicken. Die Öffnung wird mit der Standardbreite eingesetzt.
5. **Möbel hinzufügen** (linke Leiste): Möbel anklicken und dann in 2D oder 3D an die gewünschte Stelle ziehen.
   Unter „Eigenschaften“ lassen sich Maße, Drehung, Farbe und Höhe über Boden ändern. Mit **„Ersetzen durch“** tauschst du ein Möbelstück an gleicher Position und Drehung gegen ein anderes aus.
6. **Variante → „+ Kopie“**: Kopiert die aktuelle Einrichtung, um eine alternative Gestaltung auszuprobieren. Die Wände sind für alle Varianten gleich.

## Bedienung

| Aktion | 2D-Grundriss | 3D |
|---|---|---|
| Ansicht verschieben | Ziehen auf freier Fläche, rechte/mittlere Maustaste, Alt+Ziehen | rechte Maustaste |
| Zoom | Mausrad | Mausrad |
| Drehen | – | linke Maustaste |
| Möbel verschieben | ziehen | ziehen |
| Wandecke verschieben | orange Quadrate ziehen (Werkzeug „Auswählen“) | – |

Tastenkürzel: `R` dreht um 90°, `Shift+R` um 15°, `Entf` löscht, `Strg+D` dupliziert, `Strg+Z` / `Strg+Y` macht rückgängig bzw. wiederholt. Werkzeuge: `V` Auswählen, `W` Wand, `T` Tür, `F` Fenster.

In der 3D-Ansicht lassen sich die Wände auf „transparent“ oder „niedrig (1 m)“ stellen, damit du besser in die Räume siehst.

## Speichern

- Der Stand wird automatisch im Speicher des Browsers (`localStorage`) abgelegt. Das Grundriss-Bild wird dafür auf höchstens 2048 px verkleinert.
- **Export** schreibt alles (Bild, Wände, alle Varianten) in eine JSON-Datei, **Import** lädt sie wieder. Exportiere regelmäßig als Sicherung, denn der Browser-Speicher ist an den Browser und das Gerät gebunden.

## Grenzen

- Die Möbel sind einfache, parametrische Formen und keine Herstellermodelle.
- Das Tool ist für Maus und Tastatur ausgelegt. Touch-Gesten wie Pinch-Zoom werden nicht unterstützt.
