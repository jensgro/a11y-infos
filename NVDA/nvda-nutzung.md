#  NVDA als Sehender sinnvoll nutzen

## 1. **NVDA installieren**
NVDA ist kostenlos. Nach der Installation kannst du es mit `Ctrl+Alt+N` starten.

## 2. **Nur Tastatur verwenden**
Screenreader-Nutzer navigieren fast ausschließlich per Tastatur. Die wichtigsten Tasten:
- `Tab` – Fokus durch interaktive Elemente
- `H` – durch Überschriften springen
- `D` – durch Regionen springen (Landmarken)
- `NVDA+F7` – Elementliste (Überschriften, Links, Formulare)
- `NVDA+Pfeiltasten` – Lesen

## 3. **Struktur testen**
Prüfe:
- Sind Überschriften logisch gegliedert?
- Gibt es Landmarken (main, nav, header, footer)?
- Sind Listen korrekt als Listen erkennbar?
- Werden Tabellen sinnvoll vorgelesen?

## 4. **Interaktive Elemente testen**
Formulare sind oft die größte Fehlerquelle:
- Wird das Label vorgelesen?
- Wird der Fehlertext vorgelesen?
- Springt der Fokus korrekt?
- Wird der Button als Button erkannt?

## 5. **Alternativtexte prüfen**
Mit `NVDA+Tab` hörst du, wie NVDA ein fokussiertes Element beschreibt.
- Ist der Alt-Text sinnvoll?
- Ist er zu lang?
- Ist er überflüssig (z. B. bei dekorativen Bildern)?

## 6. **ARIA-Rollen und Zustände testen**
NVDA liest z. B. vor:
- „Button, collapsed“
- „Checkbox, checked“
- „Menu item, submenu“

Wenn das nicht stimmt, ist die ARIA-Implementierung fehlerhaft.

## 7. **Fokusführung testen**
Drücke `Tab` wiederholt und beobachte:
- Springt der Fokus logisch?
- Gibt es „Fokusfallen“?
- Wandert der Fokus in modalen Dialogen korrekt?

## 8. **Visuelle Kontrolle erst am Ende**
Erst nachdem du die Seite „blind“ getestet hast, schaust du visuell nach, ob das Verhalten zu dem passt, was NVDA vorgelesen hat.

---

## Was du als Sehender besonders gut testen kannst

- **Diskrepanz zwischen Optik und Semantik**  
  (z. B. Buttons, die als `<div>` gebaut sind)
- **Fokusverlust bei Overlays, Popups, Offcanvas-Menüs**
- **Fehlende ARIA-Live-Regionen** bei dynamischen Updates
- **Unlogische Überschriftenhierarchie**  
- **Nicht erreichbare Elemente** (Keyboard-Traps)

---

## Profi-Tipp

Schalte deinen Monitor *nicht* aus — aber zwinge dich, **nicht hinzusehen**.  
Wenn du doch hinschaust, achte darauf, ob das, was du siehst, auch das ist, was NVDA ansagt. Diskrepanzen sind fast immer Accessibility-Bugs.

