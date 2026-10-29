# Sprungmarke zieht nicht Fokus nach sich

> Wenn man auf https://www.swr.de/leben/gesundheit/zittern-essentieller-tremor-diagnose-neue-therapie-verfahren-100.html auf einen Link des Inhaltsverzeichnisses klickt und ann innerhalb der Seite springt, scheint sich für Screenreader der Fokus nicht zu verschiedebn, sondern auf der gesamten Seite zu bleiben. Warum? Wie kann man das beheben?

Ja, das klingt nach einem typischen Problem bei Sprunglinks (Anchor-Links) innerhalb einer Seite.

Wenn das Inhaltsverzeichnis auf der Seite lediglich auf Anker wie

```html
<a href="#diagnose">Diagnose beim essentiellen Tremor</a>
```
verweist und das Ziel nur so definiert ist:

```html
<h2 id="diagnose">Diagnose beim essentiellen Tremor</h2>
```
dann passiert Folgendes:

- Der Browser scrollt zur Zielstelle.
- Der Tastaturfokus bleibt jedoch auf dem geklickten Link im Inhaltsverzeichnis.
- Viele Screenreader folgen dem visuellen Scrollen nicht automatisch.
- Der Nutzer befindet sich aus Sicht des Screenreaders weiterhin am ursprünglichen Ort im Dokument. Dadurch entsteht leicht der Eindruck, dass "nichts passiert" ist.

Dieses Verhalten entspricht grundsätzlich dem Standardverhalten von HTML-Ankerlinks. WCAG fordert aber, dass bei Kontextwechseln und Navigation die Bedienung für Tastatur- und Screenreader-Nutzer nachvollziehbar bleibt.

## Wie prüft man das?

Mit NVDA:

- Link im Inhaltsverzeichnis aktivieren.
- Hören, ob der Screenreader anschließend die Überschrift des Zielabschnitts vorliest.
- Mit Tab weiternavigieren.

Bleibt der Fokus anschließend auf dem Link im Inhaltsverzeichnis, liegt genau dieses Problem vor.

## Mögliche Lösungen

### 1. Fokus programmatisch auf das Ziel setzen

Die robusteste Lösung:

```html
<h2 id="diagnose" tabindex="-1">
  Diagnose beim essentiellen Tremor
</h2>
```
```js
document.querySelectorAll('.toc a').forEach(link => {
  link.addEventListener('click', event => {
    const target = document.querySelector(
      event.currentTarget.getAttribute('href')
    );

    if (target) {
      target.focus();
    }
  });
});
```

Dadurch:

- springt die Seite,
- der Tastaturfokus liegt auf der Zielüberschrift,
- Screenreader lesen die neue Überschrift sofort vor.

Das entspricht dem Muster, das u.a. von GOV.UK und anderen Accessibility-Guidelines empfohlen wird.

### 2. Fokus nur nach dem Sprung setzen

Falls bereits Smooth-Scrolling eingesetzt wird:

```js
target.scrollIntoView({ behavior: 'smooth' });

setTimeout(() => {
  target.focus();
}, 500);
```

Der Fokuswechsel erfolgt dann nach Abschluss des Scrollens.

### 3. Nur Scrollen reicht nicht

Ein häufiges Missverständnis ist:

```js
element.scrollIntoView();
```

Das bewegt lediglich die Ansicht.

Der Fokus bleibt unverändert und Screenreader-Nutzer profitieren davon meist nicht.

## Speziell für eure SWR-Seite

Wenn die Inhaltsverzeichnis-Einträge auf die jeweiligen H2-Überschriften springen, würde ich prüfen:

- Haben die Zielüberschriften ein id?
- Besitzen sie zusätzlich tabindex="-1"?
- Wird nach dem Sprung focus() auf das Ziel gesetzt?

Fehlt Punkt 2 oder 3, ist sehr wahrscheinlich die Ursache gefunden.

Aus WCAG-Sicht würde ich das als Accessibility-Mangel einstufen, weil Tastatur- und Screenreader-Nutzer nach der Navigation keinen eindeutigen neuen Kontext erhalten. Es könnte je nach genauer Umsetzung insbesondere WCAG 2.4.3 (Focus Order) und die allgemeine Erwartung an nachvollziehbare intra-page Navigation betreffen.

----
## Lösung ohne JS?

Ohne JavaScript kannst du keinen Fokus aktiv auf ein beliebiges Ziel verschieben. Du kannst aber die Sprungmarken so umsetzen, dass der Browser das Ziel selbst fokussieren kann.

### Robuste HTML-Lösung

Das Ziel des Inhaltsverzeichnisses sollte ein fokussierbares Element sein:

```html
<nav aria-label="Inhaltsverzeichnis">
  <ul>
    <li>#diagnoseDiagnose beim essentiellen Tremor</a></li>
  </ul>
</nav>

<h2 id="diagnose" tabindex="-1">
  Diagnose beim essentiellen Tremor
</h2>
```

Der entscheidende Teil ist:

```html
tabindex="-1"
```

Dadurch wird die Überschrift programmatisch fokussierbar und Browser können sie beim Anspringen als Fokusziel verwenden.

### Noch robuster: Fokusziel explizit als Anker

Ein Muster, das häufig zuverlässiger funktioniert, ist ein leerer Anker vor der Überschrift:

```html
<a id="diagnose" tabindex="-1"></a>
<h2>Diagnose beim essentiellen Tremor</h2>
```

oder

```html
<h2>
  <a id="diagnose" tabindex="-1"></a>
  Diagnose beim essentiellen Tremor
</h2>
```

Das Sprungziel ist dann explizit der Anker selbst.

Was man erwarten kann

Je nach Browser-/Screenreader-Kombination:

die Seite scrollt zur Zielstelle,
der virtuelle Cursor landet direkt am Ziel,
die Überschrift wird vorgelesen oder unmittelbar erreicht.

Das Verhalten ist deutlich besser als bei einem reinen id auf einem nicht fokussierbaren Element.

### WCAG-konforme Alternative

Eigentlich ist ein Inhaltsverzeichnis innerhalb eines Artikels meist keine echte Anwendungssituation für Tastaturfokusmanagement. Viele große Websites (Wikipedia, GOV.UK, MDN) setzen bei In-Page-Navigation lediglich auf semantisch korrekte Sprunglinks und Überschriftenstruktur.

Deshalb würde ich zunächst prüfen, ob das Problem wirklich im Fokus liegt oder ob der Screenreader nach dem Sprung nicht an der Zielüberschrift landet. Falls bei NVDA nach Aktivierung des Links weiterhin der Link im Inhaltsverzeichnis der aktuelle Fokus bleibt und die Zielüberschrift nicht erreicht wird, wäre tabindex="-1" am Ziel die sauberste JavaScript-freie Verbesserung.

Empfohlener Fix für SWR:

```html
<h2 id="diagnose" tabindex="-1">
  Diagnose beim essentiellen Tremor
</h2>
```

Das ist minimalinvasiv, robust und erfordert keine Skripte.

----

## SWR-Lösung

Ja, in diesem Fall ist die Situation etwas anders.

Ihr verwendet kein modernes Fragmentziel über id, sondern ein historisches Muster:
```html
<h2>
  <span class="headline-heading">
    <a name="diagnose">Diagnose beim essentiellen Tremor&nbsp;</a>
  </span>
</h2>
```

Wenn das Inhaltsverzeichnis auf

```html
#diagnose
```

verlinkt, scrollt der Browser zum `<a name="diagnose">`, setzt aber keinen Tastaturfokus dorthin. Der Fokus verbleibt auf dem angeklickten Link im Inhaltsverzeichnis.

Da das HTML laut deiner Aussage nicht geändert werden kann, bleibt tatsächlich nur JavaScript als praktikable Lösung.

### Minimalinvasiver JS-Fix

Nach dem Sprung das Ankerziel fokussieren:

```js
document.addEventListener('click', (event) => {
  const link = event.target.closest('a[href^="#"]');
  if (!link) {
    return;
  }

  const targetName = link.getAttribute('href').substring(1);

  setTimeout(() => {
    const target = document.querySelector(
      `a[name="${CSS.escape(targetName)}"]`
    );

    if (target) {
      target.tabIndex = -1;
      target.focus();
    }
  }, 0);
});
```

Noch besser

Da der eigentliche semantische Zielpunkt die Überschrift ist, würde ich den Fokus auf das umgebende `<h2>` setzen:

```js
document.addEventListener('click', (event) => {
  const link = event.target.closest('a[href^="#"]');
  if (!link) {
    return;
  }

  const targetName = link.getAttribute('href').slice(1);

  setTimeout(() => {
    const anchor = document.querySelector(
      `a[name="${CSS.escape(targetName)}"]`
    );

    const heading = anchor?.closest('h2');

    if (heading) {
      heading.tabIndex = -1;
      heading.focus();
    }
  }, 0);
});
```

Das führt dazu, dass NVDA, JAWS und VoiceOver typischerweise direkt die Überschrift ansagen.
