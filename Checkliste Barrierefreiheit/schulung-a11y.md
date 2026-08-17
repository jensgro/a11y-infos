# a11y (Accessibility === Zugänglichkeit === Barrierefreiheit)

## Links

- [A Complete Guide To Accessible Front-End Components](https://www.smashingmagazine.com/2021/03/complete-guide-accessible-front-end-components)

## Screenreader

- Screenreader sind Aufsätze auf das Betriebssystem und die jeweiligen Applikationen. 
- Sie können nicht erkannt werden, wie Browser und deren Versionen.
- Am Ende werden die Inhalte eines Browsers an den Screenreader weitergereicht. Deshalb nehmen sie ``display: none;`` auch ernst. Denn die Browser als erste Station tun dies ja auch und reichen **nichts** weiter.
- SR lesen in der Reihenfolge des Quellcodes alles vor. Sie sind linear.
- Passiert etwas auf der Seite, so bekommen SR dies oft nicht mit. Vor allem, wenn sie "vom Ort des Geschehens" schon entfernt sind.
- Texte werden vorgelesen, auch viele HTML-Elemente werden als solche angesagt, wenn sie von semantischer Bedeutung sind (Button, Link, Liste, Tabelle ...)
- Für Bilder erstellen wir Alternativtexte, wenn sie von inhaltlicher Bedeutung sind. Wenn sie nur Schmuckelemente sind und ihre Bedeutung durch einen begleitenden Text transportiert wird (Button mit Icon und Text "Menü"), dann benötigen sie keinen alternativen Text.
- Ein Element hat immer einen "Accessible Name". Der wird aus sehr unterschiedlichen Quellen gespeist. Es gibt dafür eine ganz spezielle Hierarchie. Diese wird in den Devtools im Reiter "Accessibility" gut abgebildet. Man kann sogar aus merehren Quellen einen komplexen Accessible Name zusammenstellen.
- Ziel ist es nicht, dem SR-Nutzer mehr Infos zu geben, sondern die adäquaten.
- Manchmal kann es hilfreich sein, dem SR eigene Texte zu geben, die visuell nicht auftauchen. Dafür verschiebt man mittels CSS den Text ausserhalb des Viewports. 
- Fokus setzen und haben ist wichtig. SR werden mittels Tastatur entweder von fokussierbarem Element zu fokussierbarem Element bewegt oder einfach von oben nach unten durch die Seite (Absatz zu Absatz). Nur interaktive Elemente sind fokussierbar. Headlines bspw. nicht. Aber jeder SR hat eigene Shortcuts, um die Überschriften nacheinander durchzugehen. Ebenso kann man eine Liste aller Links vorlesen lassen und darüber dann weiter navigieren.


## Fokus

- ``DIV``s sollen nicht fokussierbar gemacht werden. Denn einem ``div`` kann man keinen accessible name (bspw. über aria-label) geben. Der SR-Nutzer weiss also nicht, was er da fokussiert.


## Buttons

- Es spricht sehr vieles dafür, dass wir keine disabled-Buttons haben sollten. Ein aktiver Button kann die Inline-Valisierung triggern und damit auf Fehler/Versäumnisse hinweisen. 
- [Betrachtung vor allem aus UX-Sicht, aber auch und a11y-Aspekte](https://www.smashingmagazine.com/2021/08/frustrating-design-patterns-disabled-buttons/)
- [a11y-Betrachtung](https://css-tricks.com/making-disabled-buttons-more-inclusive/)


## Accessible Names

- [Naming things to improve accessibility](https://hidde.blog/naming-things-to-improve-accessibility/)