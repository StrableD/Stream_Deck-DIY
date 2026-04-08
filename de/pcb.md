# PCB und Schaltplan

Der Schaltplan wird mit KiCad erstellt.
Daraus wird eine PCB Vorlage exportiert, welches bei JLCPCB/PCBWay bestellt werden soll.

Im Ordner [`stream_deck-circuit`](../stream_deck-circuit/) findet ihr das KiCad Projekt mit Schaltplan und PCB-Layout.
Das PCB soll alle elektronischen Komponenten halten.
Die Knöpfe für die Tasten werden über eine Matrix mit dem Microcontroller verbunden um Pins zu sparen.
Bei der geplanten Anzahl an Tasten werden bei einer 3×5 Anordnung 8 Pins für die Matrix gebraucht.
Weitere 6-7 Pins werden für das SPI Display benötigt.

## Schaltplan

Der Schaltplan zeigt die Verbindung zwischen den Komponenten, einschließlich des Raspberry Pi Pico, des SPI LCD Displays und der Tastenmatrix.
Hierbei ist bisher folgende Belegung geplant:

| Komponente | Pin am Pico | Funktion |
| --- | --- | --- |
| Tastenreihe 1 | GPIO0 | Tastenmatrix Zeile 1 |
| Tastenreihe 2 | GPIO1 | Tastenmatrix Zeile 2 |
| Tastenreihe 3 | GPIO2 | Tastenmatrix Zeile 3 |
| Tastenspalte 1 | GPIO3 | Tastenmatrix Spalte 1 |
| Tastenspalte 2 | GPIO4 | Tastenmatrix Spalte 2 |
| Tastenspalte 3 | GPIO5 | Tastenmatrix Spalte 3 |
| Tastenspalte 4 | GPIO6 | Tastenmatrix Spalte 4 |
| Tastenspalte 5 | GPIO7 | Tastenmatrix Spalte 5 |
| Display CS | GPI017 | SPI Chip Select |
| Display DC/RS | GPIO22 | SPI Data/Command |
| Display RST | GPIO20 | SPI Reset |
| Display MOSI | GPIO19 | SPI Master Out Slave In (SDI) |
| Display MISO | GPIO16 | SPI Master In Slave Out (SDO) |
| Display SCK | GPIO18 | SPI Clock |
| Display LED | GPIO21 | Display Hintergrundbeleuchtung (BL) |
| Display GND | GND | Masse |
| Display VCC | 3.3V | Versorgungsspannung |

Zwischen den Knöpfen der Tastenmatrix werden Dioden (1N4148) verwendet, um Ghosting-Effekte zu verhindern.
Hierbei geht vom Reihenpin die Leitung zu dem Knopf, dann durch die Diode in Schaltrichtung und von dort weiter zum Spaltenpin.

## PCB-Layout

Das PCB-Layout ist so gestaltet, dass alle Komponenten ordentlich angeordnet sind und die Verbindungen zwischen ihnen kurz und übersichtlich sind.
Wichtig ist hierbei, dass für die Tasten genügend Platz für die Löcher im PCB sowie für die Knöpfe, die Dioden und die Führungsschienen vorhanden ist.
Es muss noch das Display sowie die Buchsenleiste für den Raspberry Pi Pico auf die Rückseite des PCBs eingezeichnet werden, damit sie nicht mit den Tasten kollidieren.

Die Stromversorgung über USB-C wird ebenfalls berücksichtigt, indem ein Loch im Gehäuse vorgesehen wird, damit der Anschluss zugänglich ist.
Möglicherweise kommt auch ein verbindender USB-C Port zum Einsatz, der vom Gehäuse zum Pico führt, um das Kabelmanagement zu erleichtern und die Zugänglichkeit zu verbessern (je nach Design des Gehäuses und der Position des USB-C Anschlusses am Pico), indem das USB-C Kabel einfach vom Stream Deck entfernt und wieder angeschlossen werden kann, ohne das Gehäuse öffnen zu müssen.
