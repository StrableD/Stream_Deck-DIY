# Aktueller Plan

Der aktuelle Plan besteht aus den nachfolgenden Punkten.

## Ziel

Ein voll funktionsfähiges Stream Deck, welche die folgenden Punkte erfüllt:

- selbst gebaut
- 15 Tasten mit Beleuchtung (wie beim original)
- billiger als das original (aktuell ca. 150 €)
- kompatibel mit der Stream Deck Software oder Alternativen (z.B. StreamController, OpenDeck)

## Bauteile

Aktuell plane ich mit folgender Teileliste:

| Name | Menge | Beschreibung | Einkaufslink | Preis |
| ---- | ---- | ---- | ---- | ---- |
| Raspberry Pi Pico | 1 | Microcontroller (RP2040) | | |
| SPI LCD Display | 1 | 4,0" TFT, ST7796 Controller, 480x320 | | |
| SMD Tactile Switch | 20 | 6x6x5mm, 4-Pin SMD | | |
| Dioden 1N4148 | 20 | Kleinsignal-Dioden (SOD-123 SMD) | | |
| Buchsenleisten | 2 | 1x20 Pin für Pico-Sockel | | |
| Acrylglas 3mm | 1 | Transparent, für Taster-Inlays | | |
| Custom PCB | 1 | 100x100mm (5er Pack bei JLCPCB) | | |
| M2.5 Schrauben/Spacer | 1 Set | Zur Montage von Display & Gehäuse | | |

## Schaltplan

Der Schaltplan wird mit KiCad erstellt.
Daraus wird eine PCB Vorlage exportiert, welches bei PCBWay bestellt werden soll.

Das PCB soll alle elektronischen Komponenten halten.
Die Knöpfe für die Tasten werden über eine Matrix mit dem Microcontroller verbunden um Pins zu sparen.
Bei der geplanten Anzahl an Tasten werden bei einer 3×5 Anordnung 8 Pins für die Matrix gebraucht.
Weitere 4 Pins werden für das SPI Display benötigt.

## Taster

Die Taster sollen aus Plexiglas zugeschnitten werden.
Für den Taster selber wird ein Laufschaft und eine Halterung 3D-gedruckt.
Die Halterung hat einen , welcher den Knopf auf dem PCB drückt.
Die Knöpfe sind mit jeweils einer Diode in einer Matrix miteinander verbunden.

## Aufbau

Von unten nach oben gibt es folgende Reihenfolge für die Komponenten:

- Boden des Gehäuses
- Display
- PCB
- Knöpfe mit Tastern
- Gehäusedeckel

Hierbei ist das PCB der tragende Teil, welcher die ganzen elektrischen Bauteile hält.
Das Display wird mit Abstandshaltern auf dem PCB montiert, damit die Displayfläche nicht direkt auf dem PCB liegt.
Die Schächte für die Tasten (Knopf mit Diode, Plexiglas mit Führungsschiene) werden auf der anderen Seite des PCBs montiert.
Dies könnte durch Stecken, Schrauben, Kleben oder einfaches Auflegen (Halt durch Gehäuse) erfolgen, wird noch festgelegt.
Das PCB selber hat Löcher an den Stellen, wo die Tasten sind, damit die Taster durch das PCB hindurch auf die Knöpfe drücken können.
Der Raspberry Pi Pico wird auf der Unterseite des PCBs neben das Display mit einer Buchsenleiste montiert, damit er einfach ausgetauscht werden kann.
Die Stromversorgung erfolgt über den USB-C Anschluss des Raspberry Pi Pico, welcher durch ein Loch im Gehäuse zugänglich ist.
Das Gehäuse wird so gestaltet, dass es die Komponenten, v.a. das PCB und die Tasten, sicher hält und gleichzeitig eine ansprechende Optik bietet.
Es könnten auch Lüftungsschlitze oder andere Designelemente integriert werden, um die Funktionalität und das Aussehen zu verbessern.
