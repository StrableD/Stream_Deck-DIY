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
|----|----|----|----|----|
| Raspberry Pi Pico | 1 | Microcontroller (RP2040) | | |
| SPI LCD Display | 1 | 4,0" TFT, ST7796 Controller, 480x320 | | |

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

