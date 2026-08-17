# WAI-ARIA Checkliste

## The rules of WAI-ARIA

1. Don' use ARIA
    Wenn es ein Element gibt, das den Zweck erfüllt, nimm es!
2. Don't change native semantics
    Ändere nicht die Semantik eines Elements durch Hinzufügen einer ARIA-Rolle. Beispielsweise durch die Aria-Rolle "tabitem" an eine Überschrift. Diese würde von Screenreadern nicht mehr als Überschrift erkannt werden. Für solche Zwecke benötigen wir einen Wrapper.
3. Make interactive ARIA controls keyboard accessible
    Wenn Du ein neues Element mit der Hilfe von ARIA erstellst, muss es mit der Tastatur bedienbar sein. Die wenigsten Elemente sind dies von sich aus. Ist das verwendete Wrapper-Element nicht mit der Tastatur bedienbar, helften `tabindex="0"` oder `tabindex="-1`.
4. Don't neutralise focusable elements
    Auf einen Link oder einen Button (als die gängigsten fokussierbaren Elemente) darf keine `role="presentation"` gesetzt werden. Das würde dem Element seine Eigenschaft nehmen und der Screenreader wüsste nicht mehr, dass es sich um einen Link oder Button handelt.
5. Interactive Elements must have an accessible name
    Wenn der Button oder der Link nur ein Icon enthalten, muss dafür gesorgt werden, dass dem Screenreader ein erklärender Alternativtext angesagt wird.

## Accessible name

[Testseite](https://patrickhlauke.github.io/aria/demos/accessible-name-calculation/)


## Linkliste

- [WAI-ARIA 1.1](https://www.w3.org/TR/wai-aria/) - der Standard
- [WAI-ARIA Authoring Practices 1.1](https://w3c.github.io/aria-practices/) - offizielles Dokument des W3C
- [Using ARIA](https://w3c.github.io/using-aria/) - offizielles Dokument des W3C
- [So werden HTML-Elemente in JAWS unterstützt/interpretiert](https://thepaciellogroup.github.io/AT-browser-tests/)
- [Umfangreiche WAI-ARIA-Präsentation von Patrick Lauke](https://patrickhlauke.github.io/aria/presentation/)
- [A11y nutrition cards](https://davatron5000.github.io/a11y-nutrition-cards/) - für einzelne Webseitenelemente gibt es Hinweise, welche ARIA-Attribute verwendet werden sollen und wie die erwartete Tastaturbedienung ist.

