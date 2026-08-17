# Bausteine für a11y-Checklisten (Definition of Done)

## Grundsätzlich gültig

- Interaktive Elemente sind mit der Tastatur bedienbar.
- Alle Elemente sind für Screenreader zugänglich.
- Sind dekorative Elemente Ersatz für Textinhalte, werden die fehlenden Textinhalte alternativ an den Screenreader übermittelt (visuell ausgeblendeter Text oder ARIA).
- Animationen sind pausierbar oder deaktivierbar.
- Die Seite ist auch im High Contrast Mode nutzbar.
- Die Seite ist auch ohne Maus bedienbar.
- Die Seite ist auch ohne Bilder nutzbar.
- Insbesondere interaktive Elemente benötigen ergänzende Informationen via ARIA.

## Akkordeon

- Verwende für jeden Akkordeon-Abschnitt einen semantisch geeigneten Container. Die Nutzung von ``details`` und ``summary`` ist zu prüfen.
- Jeder Akkordeon-Header muss als ``button`` umgesetzt werden und den aktuellen Zustand über aria-expanded kommunizieren.
- Der Inhalt eines Akkordeons sollte für Screenreader nur dann sichtbar sein, wenn das Akkordeon geöffnet ist.
- Der Fokus muss beim Öffnen eines Akkordeons automatisch in den Inhalt verschoben werden.
- Der Fokus muss beim Schließen eines Akkordeons automatisch auf den Header zurückgesetzt werden.
- Der Akkordeon-Header muss auch mit der Tastatur fokussierbar und bedienbar sein.
- Der Akkordeon-Inhalt muss für Screenreader als eigenständiger Bereich erkennbar sein.
- Verweise mittels aria-controls auf den zugehörigen Inhaltsbereich.

## Badge

- Ein Badge sollte visuell den Status oder die Kategorie darstellen, ohne wichtige Informationen ausschließlich visuell zu vermitteln.
- Falls der Badge interaktiv oder erklärungsbedürftig ist, stelle einen zugänglichen Namen (z.B. über aria-label) bereit.
- Achte darauf, dass der Farbkontrast ausreichend ist, damit der Badge auch im High Contrast Mode erkennbar bleibt.

## Bilder

- Jedes Bild besitzt ein Alt-Attribut.
- Für informative Bilder ist der Alt-Text zwingend erforderlich.
- Für dekorative Bilder genügt ein leeres Alt-Attribut.

## Buttons allgemein

- Der Button führt eine Aktion aus.
- Der Button verlinkt nicht zu einer anderen Seite oder zu einem Abschnitt auf der aktuellen Seite.
- Der Button ist über die Tastatur erreichbar und der Fokus deutlich sichtbar.

## Button mit Icon

- Falls der Button keinen sichtbaren Text enthält, sorge für Screenreader-spezifischen Text (aria-label oder visuell versteckter Text).
- Falls ein SVG im Button verwendet wird, muss dieses für Screenreader mit aria-hidden="true" verborgen sein.

## Breadcrumb

- Nutze ein ``nav``-Element mit einem passenden aria-label (es ist fraglich, ob "Breadcrumb" sehr hilfreich ist).
- Die aktuelle Seite bekommt das Attribut ``aria-current="page"``.
- Alle Links in der Breadcrumb-Leiste müssen fokussierbar und mit der Tastatur navigierbar sein.
- Die Breadcrumb sollte in einer ungeordneten oder geordneten Liste (``ul`` oder ``ol``) strukturiert sein.
- Der Tastaturfokus muss beim Navigieren durch die Breadcrumb-Leiste sichtbar sein.

## Card (bspw. Teaser)

- Gliedere die Card in klar erkennbare Abschnitte (z.B. Überschrift, Text, Bild) unter Verwendung der passenden semantischen Elemente.
- Eine Card sollte niemals als Ganzes klickbar sein. Ein Screenreader würde alle Inhalte (Headline, Absatz, Alternativtext eines Bildes) als Gesamtheit vorlesen. Jegliche semantische Information wäre dahin. Für Screenreadernutzer wäre eine Card sehr geschwätzig.
- Bilder haben einen Alternativtext
- Icons ohne begleitenden Text haben einen Alternativtext (via ``aria-label`` oder als versteckter Text)

## Divider

- Idealerweise nutzen wir keinen Divider, da es sich um ein gestalterisches Problem handelt, das mit CSS zu lösen ist.
- Verwenden wir doch einen Divider, dann ist er als rein visuelles Trennelement zu implementieren. Screenreader sollten ihn nicht wahrnehmen können (z.B. mit ``aria-hidden="true"``).

## Dynamische Inhalte

- Wenn Inhalte nachgeladen werden, muss der Screenreader darüber informiert werden (zum Beispiel mittels ARIA Live Regions).

## Footer

- Der Footer ist innerhalb eines ``footer``-Elements umgesetzt.
- Der Footer bekommt die passende Rolle ``role="contentinfo"``.
- Die Links befinden sich innerhalb eines ``nav``-Elements.

## Formulare

- Jedes Formular-Kontrollelement hat ein zugeordnetes ``label``. 
- Alle Steuerungselemente haben einen deutlich sichtbaren Fokuszustand.
- Ein Klick auf das Label fokussiert das zugehörige Kontrollelement.
- Optionaler Fehlertext sollte oberhalb des jeweiligen Kontrollelements angezeigt werden, um Probleme mit der virtuellen Tastatur mobiler Geräten zu umgehen.

## Hintergrundbilder

- Hintergrundbilder sollten möglichst vermieden werden, da sie im High Contrast Mode nicht dargestellt werden und keinen Alternativtext tragen können. 
- Sind Hintergrundbilder unverzichtbar, dürfen sie nicht entscheidend für das Verständnis der Inhalte sein.
- Sind Hintergrundbilder unverzichtbar, muss die Lesbarkeit der darüberliegenden Inhalte auch im High Contrast Mode gewährleistet sein.

## Karussel

- Stelle sicher, dass das Karussel eine klare, semantische Struktur besitzt und alle Slides in einem Container liegen.
- Implementiere Buttons (!) für Navigation (Vorwärts, Rückwärts) sowie Pausen-/Spiel-Funktionen.
- Verwende aria-controls, um die Beziehung zwischen den Navigations-Buttons und den Slides zu kennzeichnen.
- Nutze aria-live und aria-atomic, um Änderungen (z.B. Wechsel der Slides) für Screenreader ankündigen zu können.
- Jedes Slide sollte als eigenständiger, zugänglicher Bereich erkennbar sein.
- Der Fokus muss beim Wechsel des Slides automatisch auf den neuen Inhalt gesetzt werden.
- Ein Karussel sollte nicht automatisch starten, sondern nur auf Benutzerinteraktion reagieren.
- Sollte das Karussel doch automatisch starten, muss es eine Pause-Funktion geben, die den Fokus auf den Pause-Button setzt.

## Liste

- Stelle sicher, dass Listen auch von Screenreadern als solche erkannt werden.
- Nutze dazu die entsprechenden HTML-Elemente (``ul``, ``ol`` und ``li``) und sorge für eine korrekte Verschachtelung.
- 
## Navigation

- Verwende das native <nav>-Element ohne zusätzliche ARIA-Rollen, um die Navigation eindeutig zu kennzeichnen.
- Die Navigationsinhalte sollten in einer ungeordneten Liste (ul) organisiert sein, um eine klare Struktur zu gewährleisten.
- Die Listen und ihre Inhalte bekommen keine separaten ARIA-Rollen.
- Inhalte, die nicht sichtbar sein sollen, müssen auch für Screenreader versteckt werden (z. B. mittels aria-hidden oder durch entsprechende CSS-Klassen).

## Navigation: Burger-Menü

- Ein Burger-Menü wird mit einem Button geöffnet, der entweder sichtbaren Fließtext oder einen zugänglichen Namen über ARIA erhält.
- Wird die Navigation ein- oder ausgeblendet, informiere den Screenreader über die Änderung (zum Beispiel durch ARIA Live Regions).

##  Popover

- Verwende ein semantisch neutrales Container-Element für den Popover, der bei Bedarf über ARIA als Dialog (role="dialog") deklariert werden kann.
- Die Nutzung der neuen popover-API sollte geprüft werden. Sie nimmt einiges an ARIA-Aufwand ab.
- Der Popover-Trigger sollte als Button umgesetzt sein, sonst funktionieren viele eingebaute ARIA-Mechanismen nicht.
- Beim Öffnen muss der Fokus automatisch in den Popover wechseln, und beim Schließen zurückgeführt werden.
- Setze aria-haspopup, aria-expanded und aria-controls, um den Status und die Beziehung zwischen Auslöser und Popover zu kommunizieren.
- Erlaube das Schließen mittels der ESC-Taste und durch Klicks außerhalb des Popovers. (Ist Standard der popover-API)

## Seitenstruktur

- Überschriften werden mit H‑Tags (z.B. ``h1`` bis ``h6``) umgesetzt und sollten in der gesamten Seite konsistent in ihrer Hierarchie verwendet werden.
- Es muss gewährleistet sein, dass die Überschriften semantisch sinnvoll sind.
- Sublines sollten als normale Textabsätze (P‑Tags) realisiert werden und nicht als Überschrift-Tags, um die korrekte Hierarchie beizubehalten.
- Es gibt skiplinks zu den wichtigen Seitenbereichen

## Tabelle

- Falls eine Tabelle in einer linearen Darstellung (z.B. für mobile Endgeräte) angezeigt werden soll, müssen die notwendigen display-Eigenschaften mittels JavaScript in der mobilen Version eingefügt werden.
- Eine linearisierte Tabelle muss intensiv mit einem Screenreader bzw. den A11y-Tools der Browser-Devtools getestet werden.


## Text & Icons

- Der Farbkontrast von Texten und Icons entspricht den Mindestanforderungen (mindestens 4,5:1 bzw. 3:1 für größere Elemente).
- Informative Icons erhalten einen zugänglichen Namen über ein aria-label, sodass ihr Zweck auch ohne visuelle Hinweise erkenntlich ist.
- Texte und Icons sollten auch im High Contrast Mode gut lesbar sein.

## Versteckte Inhalte

- Werden versteckte Inhalte sichtbar gemacht, müssen Screenreader darüber per ARIA informiert werden.
- Der Tastaturfokus darf nicht verloren gehen, wenn neuer Content nachgeladen wird. Er sollte entweder beim Nachladen automatisch an eine sinnvolle Position gesetzt oder beibehalten werden.
