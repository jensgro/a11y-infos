# Zu korrigierender Code

Die folgenden Beispiele sind auf das Wesentliche reduziert, weil es auf das Muster ankommt. Dieses Muster kann sich in mehreren Komponenten befinden.

## Etwas verstecken 

```html
<li aria-hidden="true" role="presentation">
````

Das Attribut ``aria-hidden="true"`` versteckt das Element vor dem Screenreader. Jegliche weiteren Attribute sind hier also unnötig.

Die ``role="presentation"`` wird nicht angewendet. Würde sie angewendet werden, würde der Screenreader nicht wissen, dass es sich um ein Listenelement handelt. Es würde wie ein DIV oder SPAN behandelt werden. Der Inhalt des Listenelements würde vorgelesen werden.