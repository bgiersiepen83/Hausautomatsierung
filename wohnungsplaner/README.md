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
   **Innenmaße ändern:** Beim ausgewählten Raum trägst du Breite und Tiefe in cm ein. Vorher wählst du, welche Wand sich bewegt: rechts oder links bzw. unten oder oben, wie im 2D-Grundriss. Türen und Fenster wandern mit ihrer Wand, Möbel bleiben stehen. Das funktioniert bei rechteckigen, gerade ausgerichteten Räumen. Andere Formen änderst du über die Wandecken.
   **Inhalt übertragen:** Beim ausgewählten Raum speichert **„Inhalt exportieren“** alle Möbel, die in dem Raum stehen, als eigene Datei (`rauminhalt-….json`). In einem anderen Raum lädst du sie mit **„Inhalt importieren…“**, auf Wunsch um 90°, 180° oder 270° gedreht. Die Möbel kommen zu den vorhandenen hinzu. Jedes Möbel behält den Abstand zu den beiden Wänden seiner nächstgelegenen Raumecke, Möbel an der Wand bleiben also an der Wand. Liegt danach ein Möbel außerhalb des Zielraums, weist ein Hinweis darauf hin.
   **Oberflächen:** Beim ausgewählten Raum stellst du **Boden** und **Wände des Raums** ein. Zur Wahl stehen Vorlagen und eigene Werte:
   - Boden: Holz/Laminat-Dielen (Breite, Länge, Verlegung längs oder quer), Fliesen (Größe, Fugenfarbe, gerade oder diagonal), Teppichboden, Beton/Estrich, einfarbig
   - Wände: Farbe/Putz, Tapete gestreift, Holzpaneele, Klinker, Fliesen, Sichtbeton
   - Glanzgrad: matt, seidenmatt oder glänzend

   Eine einzelne Wandseite gestaltest du abweichend, indem du die Wand anklickst und bei der Seite „eigene Oberfläche“ wählst, zum Beispiel für eine Akzentwand. Die Muster erzeugt das Tool selbst, Downloads sind dafür nicht nötig. Zu sehen sind sie in 3D, die Böden auch im 2D-Grundriss.
6. **Möbel hinzufügen** (linke Leiste): Möbel anklicken und dann in 2D oder 3D an die gewünschte Stelle ziehen.
   Unter „Eigenschaften“ lassen sich Maße, Drehung und Höhe über Boden ändern. Mit **„Ersetzen durch“** tauschst du ein Möbelstück an gleicher Position und Drehung gegen ein anderes aus.
   - **Ausführung** je nach Möbel:
     - Schränke: Anzahl Türen, Dreh- oder Schiebetüren, Schubladen, Kassettenfront, Kranz, Sockel/Füße/Kugelfüße, Griffart
     - Kommoden und Sideboards: Schubladen-Reihen und -Spalten, Türen
     - Regale: Fächer, Rückwand, Türen unten
     - Sofas und Sessel: Armlehnen, Sitzkissen, Rückenkissen, Füße, Kufen oder Drehfuß
     - Stühle: Beine, Bürostuhl oder Freischwinger, Armlehnen
     - Tische: eckig oder rund, 4 Beine, Wangen, Mittelfuß oder Kufengestell
     - Betten: Kopfteil, Beine, Bettkasten
     - Küche: Fronten, Schubladen
   - **Katalog-Gruppen:** Wohnen, Schlafen, Essen & Arbeiten, Küche, Bad, **Bilder & Deko** (Bilder, Spiegel, Wanduhr, Wandregal, Vorhang, Vase, Bücher, Kissen), **Elektronik** (Fernseher, Monitor, Laptop, PC, Drucker, Lautsprecher, Soundbar, Konsole, Router, Waschmaschine, Trockner, Geschirrspüler, Herd, Mikrowelle), **Lampen** (Steh-, Decken-, Pendel-, Schreibtisch-, Bogen-, Tisch-, Wandleuchte, LED-Leiste) und **Pflanzen** (Busch, Zimmerpalme, Monstera, Ficus, Kaktus, Bogenhanf, Hängepflanze, Orchidee, Pflanzkübel). Über das Suchfeld findest du einen Gegenstand schnell.
   - **Wandgegenstände** (Bilder, Spiegel, Uhr, Wandregal, Vorhang, Wandleuchte, LED-Leiste) rasten beim Hinzufügen und Ziehen an der nächsten Wand ein, bis 60 cm Abstand. Sie drehen sich dabei zur Raumseite, die Höhe stellst du unter „über Boden“ ein. Decken- und Pendelleuchten sowie die Hängepflanze hängen automatisch unter der Decke (Standard-Wandhöhe).
   - **Bilder:** Motiv abstrakt, Landschaft oder Farbflächen, oder ein **eigenes Foto** über „Eigenes Foto als Motiv laden…“. Das Foto wird auf höchstens 800 px verkleinert und mit gespeichert. Dazu Rahmen und Passepartout.
   - **Lampen** geben in der 3D-Ansicht Licht ab: an/aus, Lichtfarbe (warm-, neutral-, kaltweiß), Helligkeit. Mit dem Schalter **„Licht: Tag/Abend“** oben dunkelst du die Grundbeleuchtung ab, dann sieht man die Lampen deutlich. Gleichzeitig leuchten die 8 Lampen, die dem Blickpunkt am nächsten sind. Im 2D-Grundriss ist das Lampenlicht aus.
   - **Aufbau-Spots:** Bei Kleiderschrank, Regal, Kommode, Sideboard, Nachttisch und TV-Board stellst du unter „Ausführung“ die Anzahl Spots ein (0–8). Sie sitzen gleichmäßig verteilt oben auf der Vorderkante, ragen über die Front hinaus und beleuchten sie von oben. Einstellbar sind an/aus, Neigung zur Front, Lichtfarbe und Helligkeit. Die Spots wandern mit dem Möbel mit. Gleichzeitig leuchten die 8 Spots, die dem Blickpunkt am nächsten sind; am besten sichtbar mit „Licht: Abend“.
   - **Oberflächen je Teil**, z. B. Korpus, Fronten, Griffe, Bezug, Kissen, Tischplatte, Beine: Holz (Kiefer, Eiche, Buche, Nussbaum …), Lack/Kunststoff, Metall (Edelstahl, Chrom, Schwarz, Messing), Glas (klar, getönt, milchig), Stoff mit Muster (uni, Leinen, Cord, Samt, Bouclé, Karo, Streifen, Fischgrät) und Leder, jeweils mit Farbe und Glanzgrad. „Standard wiederherstellen“ setzt ein Teil zurück.
7. **📏 Messen** (nur im 2D-Grundriss):
   - **Freies Messen:** Werkzeug „Messen“ (Taste `M`) wählen und zwei Punkte anklicken oder antippen. Angezeigt wird der Abstand in cm, bei schrägen Strecken zusätzlich die waagerechte (↔) und senkrechte (↕) Länge. Der Punkt rastet an Ecken ein (Raum-, Wand- und Möbelecken), sonst an Wand-, Raum- und Möbelkanten und waagerecht oder senkrecht zum ersten Punkt. Mit gedrückter `Shift`-Taste wird nicht gefangen. Die Messung ist vorübergehend: Der nächste Klick beginnt eine neue, `Esc` oder ein Werkzeugwechsel löscht sie.
   - **Abstände am Möbel:** Ist ein Möbel ausgewählt (Werkzeug „Auswählen“), zeigen blaue Maßlinien den Abstand von jeder Möbelseite zur nächsten Wand: links, rechts, oben und unten. Beim Verschieben laufen die Werte mit. Gemessen wird bis zur Wandoberfläche.
8. **Variante → „+ Kopie“**: Kopiert die aktuelle Einrichtung, um eine alternative Gestaltung auszuprobieren. Möbel und Oberflächen (Boden, Wände) gehören zur Variante. Wandverlauf und Räume gelten für alle Varianten.

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

Tastenkürzel: `R` dreht um 90°, `Shift+R` um 15°, `Entf` löscht, `Strg+D` dupliziert, `Strg+Z` / `Strg+Y` macht rückgängig bzw. wiederholt. Werkzeuge: `V` Auswählen, `W` Wand, `T` Tür, `F` Fenster, `M` Messen.

In der 3D-Ansicht ist der Zoom auf 0,5 m bis 60 m Abstand zum Drehpunkt begrenzt. Die Schrittweite pro Mausrad-Rastung stellst du oben unter **„Zoom“** ein: fein 1 %, mittel 2 % (Standard) oder grob 5 %. Sie gilt unabhängig von Bildschirm und Browser-Zoom. Gerät die Ansicht trotzdem durcheinander, stellt **„Zentrieren“** sie wieder her.

In der 3D-Ansicht lassen sich die Wände auf „transparent“ oder „niedrig (1 m)“ stellen, damit du besser in die Räume siehst.

## Drucken

**„🖨 Drucken…“** öffnet einen Dialog:

- **Inhalt:** 2D-Grundriss, 3D-Ansicht (so wie sie gerade eingestellt ist, auch mit „Licht: Abend“) und Möbelliste. Die Möbelliste ist nach Räumen gruppiert, mit Maßen, Ausführung und Oberflächen. Jeder Teil kommt auf eine eigene Seite.
- **Maße im Grundriss:** Raum-Innenmaße (rot), Wandlängen auf der Raumseite mit Türen (T) und Fenstern (F) sowie Möbelmaße (B × T). Raumname und Fläche stehen immer dabei, unten auch eine Maßstabsleiste.
- **Papier:** A4 oder A3, quer oder hoch.
- **Maßstab:** „passend“ füllt die Seite. Mit 1:50 oder 1:100 kannst du mit dem Lineal nachmessen. Passt der Grundriss nicht aufs Papier, weist der Dialog darauf hin.

Im Druckfenster des Browsers die Skalierung auf **100 % / „Tatsächliche Größe“** stellen, damit 1:50 und 1:100 stimmen, und **Hintergrundgrafiken** einschalten. Dort lässt sich der Ausdruck auch als PDF speichern.

## Speichern

- Der Stand wird automatisch im Speicher des Browsers (`localStorage`) abgelegt. Das Grundriss-Bild wird dafür auf höchstens 2048 px verkleinert.
- **Export** schreibt alles (Bild, Wände, alle Varianten) in eine JSON-Datei, **Import** lädt sie wieder. Exportiere regelmäßig als Sicherung, denn der Browser-Speicher ist an den Browser und das Gerät gebunden.

## Grenzen

- Die Möbel sind einfache, parametrische Formen und keine Herstellermodelle.
- Die Raumfläche ist die Bodenfläche innerhalb der gezeichneten Wände. Es ist **keine Wohnflächenberechnung nach der Wohnflächenverordnung (WoFlV)**, zum Beispiel ohne Abzüge für Raumhöhen unter 2 m bzw. Dachschrägen ([§ 4 WoFlV](https://www.gesetze-im-internet.de/woflv/__4.html)). Die Genauigkeit hängt davon ab, wie genau die Wände gezeichnet und kalibriert sind.
- Automatisch erkannte Räume arbeiten intern mit einem 1-cm-Raster; die Raumkanten werden anschließend exakt auf die Wandflächen gelegt. Bei sehr großen Grundrissen wird das Raster gröber (max. 4 Mio. Zellen).
