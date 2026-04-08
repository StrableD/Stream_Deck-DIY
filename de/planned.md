# Aktueller Plan

Der aktuelle Plan besteht aus den nachfolgenden Punkten.

## Ziel

Ein voll funktionsfähiges Stream Deck, welche die folgenden Punkte erfüllt:

- selbst gebaut
- 15 Tasten mit änderbaren Symbolen/Bildern durch ein Display (wie beim original)
- billiger als das original (aktuell ca. 150 €)
- kompatibel mit der Stream Deck Software oder Alternativen (z.B. StreamController, OpenDeck)
- idealerweise einfach zu bauen (durch diese Dokumentation)
- möglichst flexibel (z.B. durch austauschbare Tasten & Microcontroller, Erweiterbarkeit)
- ansprechendes Design (Gehäuse, Tasten mit haptischem Feedback, etc.)

## Bauteile

Aktuell plane ich mit folgender Teileliste:

| Name | Menge | Beschreibung |
| ---- | ---- | ---- | 
| Raspberry Pi Pico | 1 | Microcontroller (RP2040) |
| SPI LCD Display | 1 | 4,0" TFT, ST7796 Controller, 480x320 |
| SMD Tactile Switch | 20 | 6x6x5mm, 4-Pin SMD |
| Dioden 1N4148 | 20 | Kleinsignal-Dioden (SOD-123 SMD) |
| Buchsenleisten | 2 | 1x20 Pin für Pico-Sockel |
| Acrylglas 3mm | 1 | Transparent, für Tasten-Inlays |
| Custom PCB | 1 | 100x100mm (5er Pack bei JLCPCB/PCBWay) |
| M2.5 Schrauben/Spacer | 1 Set | Zur Montage von Display & Gehäuse |

Des weiteren benötigen wir folgendes Werkzeug: 
- Lötkolben & Lötzubehör (Lötzinn, Entlötlitze, etc.)
- 3D-Drucker (für Tasten und Gehäuse) (alternativ irgendwo drucken lassen)
- Laubsäge oder Laser Cutter (für Acrylglas, alternativ zuschneiden lassen)
- Schraubendreher, Zangen, etc. (für Montage)

## Schaltplan

Der Schaltplan wird mit KiCad erstellt.
Daraus wird eine PCB Vorlage exportiert, welches bei JLCPCB/PCBWay bestellt werden soll.

Das PCB soll alle elektronischen Komponenten halten.
Die Knöpfe für die Tasten werden über eine Matrix mit dem Microcontroller verbunden um Pins zu sparen.
Bei der geplanten Anzahl an Tasten werden bei einer 3×5 Anordnung 8 Pins für die Matrix gebraucht.
Weitere 4 Pins werden für das SPI Display benötigt.

## Tasten

Die Tasten sollen aus Plexiglas zugeschnitten werden.
Für den Tasten selber wird ein Laufschaft und eine Halterung 3D-gedruckt.
Die Halterung hat einen , welcher den Knopf auf dem PCB drückt.
Die Knöpfe sind mit jeweils einer Diode in einer Matrix miteinander verbunden.

## Aufbau

Von unten nach oben gibt es folgende Reihenfolge für die Komponenten:

- Boden des Gehäuses
- Display
- PCB
- Knöpfe mit Tasten
- Gehäusedeckel

Hierbei ist das PCB der tragende Teil, welcher die ganzen elektrischen Bauteile hält.
Das Display wird mit Abstandshaltern auf dem PCB montiert, damit die Displayfläche nicht direkt auf dem PCB liegt.
Die Schächte für die Tasten (Knopf mit Diode, Plexiglas mit Führungsschiene) werden auf der anderen Seite des PCBs montiert.
Dies könnte durch Stecken, Schrauben, Kleben oder einfaches Auflegen (Halt durch Gehäuse) erfolgen, wird noch festgelegt.
Das PCB selber hat Löcher an den Stellen, wo die Tasten sind, damit die Tasten durch das PCB hindurch auf die Knöpfe drücken können.
Der Raspberry Pi Pico wird auf der Unterseite des PCBs neben das Display mit einer Buchsenleiste montiert, damit er einfach ausgetauscht werden kann.
Die Stromversorgung erfolgt über den USB-C Anschluss des Raspberry Pi Pico, welcher durch ein Loch im Gehäuse zugänglich ist.
Das Gehäuse wird so gestaltet, dass es die Komponenten, v.a. das PCB und die Tasten, sicher hält und gleichzeitig eine ansprechende Optik bietet.
Es könnten auch Lüftungsschlitze oder andere Designelemente integriert werden, um die Funktionalität und das Aussehen zu verbessern.

## Software

Aktuell plane ich die Software KiCad für die Erstellung des Schaltplans und der PCB-Layouts zu verwenden.
Für die Erstellung des Gehäuses kommt für mich gerade nur FreeCAD in Frage, da es kostenlos, Open-Source und für alle Betriebssysteme verfügbar ist.
Für die Programmierung des Raspberry Pi Pico will ich CircuitPython oder MicroPython nutzen, da ich mit Python bereits Erfahrung habe und die Entwicklung damit schneller vonstatten gehen könnte.
Diese Software soll so gestaltet sein, dass sie die Tastenanschläge durch die Matrix erkennt und die entsprechende Aktion ausführt (z.B. Tastendruck an den Computer senden, Bild auf dem Display ändern, etc.).
Hierbei soll die Software auf dem Pi mit den oben genannten Alternativen zur Stream Deck Software kompatibel sein, damit sie von möglichst vielen Nutzern verwendet werden kann.

## Zeitplan

Der Zeitplan ist aktuell noch nicht festgelegt, da es von verschiedenen Faktoren abhängt (z.B. Verfügbarkeit der Bauteile, Lernkurve bei der Software, etc.).
Ich plane jedoch den folgenden groben Ablauf einzuhalten:

1. Recherche & Planung (mit diesem Dokument abgeschlossen)
2. Erstellen des Schaltplans (kann zu Planänderungen führen)
3. Erstellen des PCB-Layouts aus dem Schaltplan (ebenfalls mit möglichen Planänderungen)
4. Bestellung der PCB und Bauteile (abhängig von Lieferzeiten)
5. Erstellen und Ausprobieren der Tasten (Plexiglas zuschneiden, 3D-Druck der Halterungen, etc.)
6. Programmierung der Software (inklusive Testen mit der Hardware)
7. Zusammenbau der Komponenten (PCB bestücken, Gehäuse bauen, etc.)
8. Feinabstimmung & Fehlerbehebung (je nach Bedarf)

Die Reihenfolge der Schritte kann sich je nach Fortschritt und auftretenden Herausforderungen ändern, aber ich werde versuchen, mich so gut wie möglich an diesen Plan zu halten.
Die Dokumentation soll neben den einzelnen Schritten erfolgen und auch die Herausforderungen und Lösungen festhalten, damit andere von meinen Erfahrungen profitieren können.

_Anmerkungen_: Sowohl das Erstellen des Tasten-Designs als auch die Softwareentwicklung könnten parallel laufen, da sie sich nicht direkt beeinflussen.
Jedoch kann das wirkliche Testen von beidem erst erfolgen, wenn die Hardware (PCB, Tasten) verfügbar ist.
Gleichzeitig könnte die Bestellung der Bauteile auch schon vor der Fertigstellung des Schaltplans erfolgen, wenn die benötigten Komponenten bereits feststehen, um Zeit zu sparen.

## Risiken & Herausforderungen

Es gibt einige Risiken und Herausforderungen, die bei diesem Projekt auftreten könnten:

- Verfügbarkeit der Bauteile: Es könnte zu Lieferverzögerungen oder Engpässen bei bestimmten Komponenten kommen, was den Zeitplan beeinflussen könnte.
- Lernkurve bei der Software: Da ich mit KiCad/FreeCAD noch nicht viel Erfahrung habe, könnte dies die Entwicklungszeit verlängern.
Auch können bei der Programmierung unerwartete Probleme auftreten (z.B. noch nicht bekannte Libraries, unerwartetes Verhalten der Hardware), die zusätzliche Zeit erfordern.
- Komplexität der Tasten: Das Design und die Herstellung der Tasten könnte komplexer sein als erwartet, insbesondere wenn es um die Integration von Plexiglas, 3D-gedruckten Teilen und der Diode geht.
- Kompatibilität mit Software: Es könnte Herausforderungen geben, die Software so zu gestalten, dass sie mit verschiedenen Stream Deck Alternativen kompatibel ist, insbesondere wenn es um die Kommunikation zwischen der Hardware und der Software geht.
Hier wird noch weitere Recherche und Planung notwendig sein, um sicherzustellen, dass die Software flexibel genug ist, um mit verschiedenen Plattformen zu funktionieren.
- Kosten: Es könnte schwierig sein, alle geplanten Funktionen und Komponenten innerhalb des angestrebten Budgets zu realisieren, insbesondere wenn unerwartete Kosten auftreten (z.B. teurere Bauteile, Preisanstiege durch Lieferengpässe/Inflation/..., etc.).
- Design & Ästhetik: Es könnte eine Herausforderung sein, ein ansprechendes Design zu erstellen, das gleichzeitig funktional und einfach zu bauen ist.
Hier könnte es notwendig sein, Kompromisse zwischen Design und Funktionalität einzugehen, um ein zufriedenstellendes Ergebnis zu erzielen.

Trotz dieser Herausforderungen bin ich zuversichtlich, dass ich sie mit sorgfältiger Planung, Recherche und Anpassungsfähigkeit bewältigen kann.
Die Dokumentation dieser Herausforderungen und der Lösungen wird auch anderen helfen, die ähnliche Projekte angehen möchten.

## Weiteres

Dieses Projekt ist als Lern- und Dokumentationsprojekt gedacht, daher ist es möglich, dass sich der Plan im Laufe der Zeit ändert, wenn neue Erkenntnisse gewonnen werden oder unerwartete Herausforderungen auftreten.
Ich werde versuchen, so flexibel wie möglich zu bleiben und den Plan entsprechend anzupassen, um das bestmögliche Ergebnis zu erzielen.

Außerdem ist geplant den Bau des Projekts in Form eines Twitch-Streams mit VODs zu dokumentieren, um den Prozess noch transparenter zu machen und anderen die Möglichkeit zu geben, Fragen zu stellen oder Feedback zu geben.
Hierdurch gibt es die Möglichkeit sich direkt an dem Entwicklungsprozess durch Chat-Interaktionen zu beteiligen und mir damit zu helfen.
Die Dokumentation in diesem Repository soll dabei als ergänzende Ressource dienen, um die wichtigsten Informationen, Pläne und Fortschritte festzuhalten, damit sie auch für andere zugänglich und nachvollziehbar sind.
