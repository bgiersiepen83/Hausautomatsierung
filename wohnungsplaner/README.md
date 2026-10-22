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
5. **Raum**: In einen Raum klicken oder tippen, der ringsum von Wänden umschlossen ist. Das Tool erkennt den Raum automatisch, Türen und Fenster zählen dabei als Begrenzung.
   Unter „Eigenschaften“ vergibst du Name und Bodenfarbe. Angezeigt wird die **Innenfläche** bis zur Wandinnenseite. Ändern sich die Wände, wird der Raum automatisch neu berechnet.
   Ist ein Bereich nicht geschlossen, zeichnest du ihn mit **„Raum ✎“** als Polygon von Hand. Ecken setzen, dann schließen per Klick auf den ersten Punkt, Doppelklick, Enter oder „Fertig“.
   Ohne Auswahl zeigt die Seitenleiste eine Übersicht aller Räume mit Summe.
6. **Möbel hinzufügen** (linke Leiste): Möbel anklicken und dann in 2D oder 3D an die gewünschte Stelle ziehen.
   Unter „Eigenschaften“ lassen sich Maße, Drehung, Farbe und Höhe über Boden ändern. Mit **„Ersetzen durch“** tauschst du ein Möbelstück an gleicher Position und Drehung gegen ein anderes aus.
7. **Variante → „+ Kopie“**: Kopiert die aktuelle Einrichtung, um eine alternative Gestaltung auszuprobieren. Möbel und Bodenfarben gehören zur Variante, Wände und Räume gelten für alle Varianten.

## Bedienung

| Aktion | 2D-Grundriss (Maus) | 2D-Grundriss (Touch) | 3D (Maus) | 3D (Touch) |
|---|---|---|---|---|
| Ansicht verschieben | Ziehen auf freier Fläche, rechte/mittlere Maustaste, Alt+Ziehen | 1 Finger auf freier Fläche (Werkzeug „Auswählen“), 2 Finger | rechte Maustaste | 2 Finger |
| Zoom | Mausrad | 2 Finger auseinander/zusammen | Mausrad | 2 Finger auseinander/zusammen |
| Drehen | – | – | linke Maustaste | 1 Finger |
| Möbel verschieben | ziehen | ziehen | ziehen | ziehen |
| Wandecke verschieben | orange Quadrate ziehen (Werkzeug „Auswählen“) | ebenso | – | – |
| Wandzug / Raum-Polygon beenden | Doppelklick, Enter, Esc oder „Fertig“ | langes Tippen oder „Fertig“ | – | – |

Bei Touch wird ein Wandpunkt erst beim Loslassen gesetzt. Du kannst den Finger also bis zur richtigen Stelle ziehen, eine Vorschaulinie zeigt die Länge.
Auf schmalen Bildschirmen (Tablet hochkant, Handy) blendest du Möbelkatalog und Eigenschaften über **„☰ Panel“** als Bereich am unteren Rand ein.

Tastenkürzel: `R` dreht um 90°, `Shift+R` um 15°, `Entf` löscht, `Strg+D` dupliziert, `Strg+Z` / `Strg+Y` macht rückgängig bzw. wiederholt. Werkzeuge: `V` Auswählen, `W` Wand, `T` Tür, `F` Fenster.

In der 3D-Ansicht lassen sich die Wände auf „transparent“ oder „niedrig (1 m)“ stellen, damit du besser in die Räume siehst.

## Speichern

- Der Stand wird automatisch im Speicher des Browsers (`localStorage`) abgelegt. Das Grundriss-Bild wird dafür auf höchstens 2048 px verkleinert.
- **Export** schreibt alles (Bild, Wände, alle Varianten) in eine JSON-Datei, **Import** lädt sie wieder. Exportiere regelmäßig als Sicherung, denn der Browser-Speicher ist an den Browser und das Gerät gebunden.

## Grenzen

- Die Möbel sind einfache, parametrische Formen und keine Herstellermodelle.
- Die Raumfläche ist die Bodenfläche innerhalb der gezeichneten Wände. Es ist **keine Wohnflächenberechnung nach der Wohnflächenverordnung (WoFlV)**, zum Beispiel ohne Abzüge für Raumhöhen unter 2 m bzw. Dachschrägen ([§ 4 WoFlV](https://www.gesetze-im-internet.de/woflv/__4.html)). Die Genauigkeit hängt davon ab, wie genau die Wände gezeichnet und kalibriert sind.
- Automatisch erkannte Räume arbeiten intern mit einem 1-cm-Raster; die Raumkanten werden anschließend exakt auf die Wandflächen gelegt. Bei sehr großen Grundrissen wird das Raster gröber (max. 4 Mio. Zellen).
