## Headlines
- Überschriften sind H-Tags und semantisch sinnvoll
- Sublines sind keine H-Tags sondern P-Tags
- Versteckte Überschriften für Screenreader vorhanden (optional)

## Text & Icons
- Kontraste für Text und Icons werden eingehalten (4,5:1 oder 3:1 bei großen Elementen)
- Informative Icons haben ein aria-label
- ``<article>`` wird nur bei langen Textblöcken verwendet, nicht für Teasertexte
- Texte/Icons sind im High-Contrast-Mode lesbar

## Bilder
- Informative Bilder haben kurzen, beschreibenden alt-Text
- Dekorative Bilder haben leeren alt-Text, kein redundanter alt-Texte
- Hintergrundbilder sollen nicht kriegsentscheidend für das Verständnis und die Erfassung der Inhalte sein, weil der High Contrast Mode diese nicht darstellt.

## Screenreader-Bedienung
- Listen sind als UL bzw. OL definiert und korrekt verschachtelt
- Nav-Tag ist um Navigation gewrappt
- Formularfelder haben ein eindeutiges label-Tag
- **Nachgeladener Content** oder **Änderungen** durch Filter werden SR-Nutzern mitgeteilt
- Aria-Properties (z. B. extended, hidden) sind korrekt gesetzt und werden bei Bedarf korrekt aktualisiert
- optische Buttons sind immer ``<a>`` oder ``<button>`` Elemente
  - ein Button führt eine Aktion aus
  - ein Link führt zu einer anderen Seite oder zu einem anderen Bereich auf der gleichen Seite

## Tastatur-Bedienung
- Die Tab-Reihenfolge ist gleich wie die sichtbare Reihenfolge
- Alle Elemente, die klickbar sind, sind auch mit der Tastatur bedienbar
- Der Fokus geht nicht verloren, wenn Content nachgeladen wird

## Qualitätssicherung
- Gerendertes HTML weist keine Fehler auf (W3C-Validator)
- Wave-Plugin oder axe weist keine Fehler auf


## Optional

### Screenreader-Tests in folgenden Kombinationen
- Firefox & NVDA
- Chrome & JAWS

### Test im High Contrast Mode