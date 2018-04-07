# calliope-wahlcomputer
Calliope Mini als Wahlcomputer (Projekt & Unterrichtsmaterial)

_Bitte habt Spaß daran, dieses Projekt zu nutzen. Ich würde mich auch sehr freuen, wenn ihr Verbesserungen an der Software oder an der Dokumentation# calliope-wahlcomputer gleich hier im Git anpasst. Wenn du nicht weist wie, oder es dir zu viel Arbeit ist, schick mir deine Verbesserungen einfach an boris.crismancich@gmail.com.

# Warum gibt es Wahlcomputer?
Die meisten Wahlen finden mit Wahlzetteln aus Papier statt. Alle wahlberechtigten bekommen je einen Wahlzettel und können darauf ihre Wahlmöglichkeiten ankreuzen. Die ausgefüllten werden gesammelt und die Stimmen für die Wahlmöglichkeiten ausgezählt. Die Wahlmöglichkeit mit den meisten Stimmen gewinnt die Wahl.Wahlzettel aus Papier hat viele Nachteile, besonders bei Wahlen, wo viele Tausend oder sogar Millionen von Menschen wählen dürfen.

- Wahlzettel müssen für jede Wahl neu gedruckt werden, das ist teuer, langwierig und belastet die Umwelt
- Wahlzettel müssen zu Wahllokalen an vielen Orten transportiert werden, ebenfalls teuer, langwierig und umweltschädlich
- Wahlzettel müssen von Hand ausgezählt werden, das ist viel Arbeit, dauert lange und man braucht viele Wahlhelfer.
- Es muss sichergestellt werden, dass keine Wahlzettel hinzugemogelt werden
- Es muss sichergestellt werden, dass die Wahlhelfer sie Stimmen richtig zählen
- Wenn Wahlzettel verloren gehen oder nicht rechtzeitig eintreffen, verzögern sich Wahlen
- Es dauert sehr lange, bis alle Stimmen ausgezählt sind und man das Ergebnis kennt

Die Idee von Wahlcomputern ist es, auf das Papier verzichten zu können. Jedes Wahllokal bekommt einen Wahlcomputer. Am Wahlcomputer können die Wahlberechtigten ihre Stimme abgeben. Ihnen werden die zur Wahl stehenden Wahlmöglichkeiten angezeigt und sie können sich für eine ( manchmal auch mehrere) entscheiden. Die Wahlcomputer senden die abgegebenen Stimmen über ein Netzwerk an einen Zentralcomputer.

- Statt Whalzetteln schafft man einmal Wahlcomputer an, die immer wieder verwendet werden können
- Die Wahlergebnisse kann man jederzeit live mitverfolgen und genaue live Hochrechnungen anzeigen
- Wahlen können sehr schnell organisiert werden

# Calliope Mini als Wahlcomputer
## Das brauchst du
Zwei oder mehr Calliope Mini.
## So funktioniert es
Ein Calliope Mini fungiert als zentraler Hauptrechner, auf dem die Stimmen gesammelt und angezeigt werden.
Je nachdem wie viele Calliopes man zur Verfügung hat, dient ein Calliope Mini als Wahlcomputer zur Stimmabgabe für alle, oder jede*r stimmt mit dem eigenen Wahlcomputer ab.
## Bedienung Wahlcomputer
Beim Wahlcomputer kannst du mit den Knöpfen A und B zwischen den Wahlmöglichkeiten hin- und her schalten. Drückst du A und B zusammen, wird deine Wahl abgesendet und du hörst einen Piepton als Bestätigung.

Um die Anzahl der möglichen Wahlmöglichkeiten anzupassen, muss im Code des Wahlcomputers der Platzhalter für Anzahl_Wahlmoeglichkeiten angepasst werden. Bei zentralen Wahlcomputer sind derzeit 3 Wahlmöglichkeiten vorgesehen, du kannst das aber jederzeit erweitern.

## Programmierung der Wahlcomputer (Client für Abstimmung)
Hier brauchen wir zwei Platzhalter. Einmal müssen wir die Anzahl von Auswahlmöglichkeiten festlegen. Dann kann man die gewählte Wahlmöglichkeit mit Knopf A oder B auswählen. Wir beginnen mit 1. Dann kann man die Zahl mit B so lange erhöhen, bis die Anzahl von AUswahlmöglichkeiten erreicht ist. Danach beginnen wir wieder bei 1. Mit 1 geht es genauso, nur zählen wir runter. Die aktuelle Zahl wird immer kleiner. Außer wenn 1 erreicht ist. Dann zählen wir nicht nach 0 sondern fangen wieder bei der größten AUswahlmöglichkeit an.

## Programmierung des zentralen Wahlcomputer (Server für Auswertung und ANzeige)
Der Hauptrechner für unsere Wahl hat zwei Aufgaben. Als erstes müssen eingehende Stimmen gezählt werden.

Hier zählen wir je nach gewählter Wahlmöglichkeit, die vom Wahlcomputer gesendet wurde, die abgegebenen Stimmen in den Platzhaltern Stimmen_fuer_1, Stimmen_fuer_2 und Stimmen_fuer_3.

Beim Auszählen müssen wir jedes Mal vergleichen und alle Wahlmöglichkeiten durchgehen: Hat die aktuelle Wahlmöglichkeiten mehr Stimmen als die letzte? Wenn ja, ist das erstmal unser Favorit.Wir merken uns dabei den aktuellen Favoriten (im Platzhalter Die_meisten_Stimmen_hat) und die bisher höchste Zahl an Stimmen Hoechste_Anzahl_Stimmen. Wenn wir sehen, dass eine Wahlmöglichkeiten noch mehr Stimmen hat, als unser bisheriger Favorit, dann nehmen wir die neue Wahlmöglichkeit und dpeichern sie in Die_meisten_Stimmen_hat. Da diese die meisten Stimmen hat, aktualisieren wir auch die Hoechste_Anzahl_Stimmen. Am Ende bleibt in Die_meisten_Stimmen_hat die Wahlmöglichkeit stehen, die wirklich gewonnen hat. Jetzt spielen wir noch einen Ton und zeigen das Ergebnis an.

# Unterrichtsideen
- Diskutiert, welche vor- und Nachteile die Umstellung auf Wahlcomputer hat.
- Diskutiert, wo, wie und von wem Wahlcomputer oder die Daten der Wahl manipuliert werden könnten (Entwickler, Betreiber, Datentransport, Wahlhelfer).
- Macht es einen Unterschied, wenn die Wahlberechtigten bereits während der Wahl den aktuellen Stand der Hochrechnungen sehen?

# Ideen für weiterentwicklungen
- Lass den zwntralen Hauptconmputer piepen, wenn eine Stimme abgegeben wurde.
- Erweitere die Lösung so, dass jeder Wahlcomputer nur einmal senden kann.
- Erweitere die Lösung so, dass auf dem zentralen Wahlcomputer 1. und 2. Platz angezeigt werden.
- Nutzt eine einzigartige Geräte-ID für jeden Calliope Mini um sicherzustellen, dass jede*r nur eine Stimme abgibt.
- Nutzt eine einzigartige Geräte-ID für jeden Calliope Mini um sicherzustellen, dass nur die zur Wahl zugelassenen Calliopes stimmen abgeben können.
- Ihr könnt auch für jede Wahlmöglichkeit einen Calliope nehmen. Dann muss bei Wahlcomputer bei der Abstimmung die Funk Gruppe umgestellt werden.



# Warum gibt es Wahlcomputer?
Die meisten Wahlen finden mit Wahlzetteln aus Papier statt. Alle wahlberechtigten bekommen je einen Wahlzettel und können darauf ihre Wahlmöglichkeiten ankreuzen. Die ausgefüllten werden gesammelt und die Stimmen für die Wahlmöglichkeiten ausgezählt. Die Wahlmöglichkeit mit den meisten Stimmen gewinnt die Wahl.Wahlzettel aus Papier hat viele Nachteile, besonders bei Wahlen, wo viele Tausend oder sogar Millionen von Menschen wählen dürfen.

- Wahlzettel müssen für jede Wahl neu gedruckt werden, das ist teuer, langwierig und belastet die Umwelt
- Wahlzettel müssen zu Wahllokalen an vielen Orten transportiert werden, ebenfalls teuer, langwierig und umweltschädlich
- Wahlzettel müssen von Hand ausgezählt werden, das ist viel Arbeit, dauert lange und man braucht viele Wahlhelfer.
- Es muss sichergestellt werden, dass keine Wahlzettel hinzugemogelt werden
- Es muss sichergestellt werden, dass die Wahlhelfer sie Stimmen richtig zählenich hier
- Wenn Wahlzettel verloren gehen oder nicht rechtzeitig eintreffen, verzögern sich Wahlen
- Es dauert sehr lange, bis alle Stimmen ausgezählt sind und man das Ergebnis kennt

Die Idee von Wahlcomputern ist es, auf das Papier verzichten zu können. Jedes Wahllokal bekommt einen Wahlcomputer. Am Wahlcomputer können die Wahlberechtigten ihre Stimme abgeben. Ihnen werden die zur Wahl stehenden Wahlmöglichkeiten angezeigt und sie können sich für eine ( manchmal auch mehrere) entscheiden. Die Wahlcomputer senden die abgegebenen Stimmen über ein Netzwerk an einen Zentralcomputer.

- Statt Whalzetteln schafft man einmal Wahlcomputer an, die immer wieder verwendet werden können
- Die Wahlergebnisse kann man jederzeit live mitverfolgen und genaue live Hochrechnungen anzeigen
- Wahlen können sehr schnell organisiert werden

# Calliope Mini als Wahlcomputer
## Das brauchst du
Zwei oder mehr Calliope Mini.
## So funktioniert es
Ein Calliope Mini fungiert als zentraler Hauptrechner, auf dem die Stimmen gesammelt und angezeigt werden.
Je nachdem wie viele Calliopes man zur Verfügung hat, dient ein Calliope Mini als Wahlcomputer zur Stimmabgabe für alle, oder jede*r stimmt mit dem eigenen Wahlcomputer ab.
## Bedienung Wahlcomputer
Beim Wahlcomputer kannst du mit den Knöpfen A und B zwischen den Wahlmöglichkeiten hin- und her schalten. Drückst du A und B zusammen, wird deine Wahl abgesendet und du hörst einen Piepton als Bestätigung.

Um die Anzahl der möglichen Wahlmöglichkeiten anzupassen, muss im Code des Wahlcomputers der Platzhalter für Anzahl_Wahlmoeglichkeiten angepasst werden. Bei zentralen Wahlcomputer sind derzeit 3 Wahlmöglichkeiten vorgesehen, du kannst das aber jederzeit erweitern.

## Programmierung der Wahlcomputer (Client für Abstimmung)
Hier brauchen wir zwei Platzhalter. Einmal müssen wir die Anzahl von Auswahlmöglichkeiten festlegen. Dann kann man die gewählte Wahlmöglichkeit mit Knopf A oder B auswählen. Wir beginnen mit 1. Dann kann man die Zahl mit B so lange erhöhen, bis die Anzahl von AUswahlmöglichkeiten erreicht ist. Danach beginnen wir wieder bei 1. Mit 1 geht es genauso, nur zählen wir runter. Die aktuelle Zahl wird immer kleiner. Außer wenn 1 erreicht ist. Dann zählen wir nicht nach 0 sondern fangen wieder bei der größten AUswahlmöglichkeit an.

## Programmierung des zentralen Wahlcomputer (Server für Auswertung und ANzeige)
Der Hauptrechner für unsere Wahl hat zwei Aufgaben. Als erstes müssen eingehende Stimmen gezählt werden.

Hier zählen wir je nach gewählter Wahlmöglichkeit, die vom Wahlcomputer gesendet wurde, die abgegebenen Stimmen in den Platzhaltern Stimmen_fuer_1, Stimmen_fuer_2 und Stimmen_fuer_3.

Beim Auszählen müssen wir jedes Mal vergleichen und alle Wahlmöglichkeiten durchgehen: Hat die aktuelle Wahlmöglichkeiten mehr Stimmen als die letzte? Wenn ja, ist das erstmal unser Favorit.Wir merken uns dabei den aktuellen Favoriten (im Platzhalter Die_meisten_Stimmen_hat) und die bisher höchste Zahl an Stimmen Hoechste_Anzahl_Stimmen. Wenn wir sehen, dass eine Wahlmöglichkeiten noch mehr Stimmen hat, als unser bisheriger Favorit, dann nehmen wir die neue Wahlmöglichkeit und dpeichern sie in Die_meisten_Stimmen_hat. Da diese die meisten Stimmen hat, aktualisieren wir auch die Hoechste_Anzahl_Stimmen. Am Ende bleibt in Die_meisten_Stimmen_hat die Wahlmöglichkeit stehen, die wirklich gewonnen hat. Jetzt spielen wir noch einen Ton und zeigen das Ergebnis an.

# Unterrichtsideen
- Diskutiert, welche vor- und Nachteile die Umstellung auf Wahlcomputer hat.
- Diskutiert, wo, wie und von wem Wahlcomputer oder die Daten der Wahl manipuliert werden könnten (Entwickler, Betreiber, Datentransport, Wahlhelfer).
- Macht es einen Unterschied, wenn die Wahlberechtigten bereits während der Wahl den aktuellen Stand der Hochrechnungen sehen?

# Ideen für weiterentwicklungen
- Lass den zwntralen Hauptconmputer piepen, wenn eine Stimme abgegeben wurde.
- Erweitere die Lösung so, dass jeder Wahlcomputer nur einmal senden kann.
- Erweitere die Lösung so, dass auf dem zentralen Wahlcomputer 1. und 2. Platz angezeigt werden.
- Nutzt eine einzigartige Geräte-ID für jeden Calliope Mini um sicherzustellen, dass jede*r nur eine Stimme abgibt.
- Nutzt eine einzigartige Geräte-ID für jeden Calliope Mini um sicherzustellen, dass nur die zur Wahl zugelassenen Calliopes stimmen abgeben können.
- Ihr könnt auch für jede Wahlmöglichkeit einen Calliope nehmen. Dann muss bei Wahlcomputer bei der Abstimmung die Funk Gruppe umgestellt werden.

