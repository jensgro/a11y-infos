# NVDA Minimal-Konfiguration

Dies ist eine Schritt‑für‑Schritt‑Minimal-Konfiguration für NVDA – so wenig „Nebenwirkung“ wie möglich, aber jederzeit nutzbar.

## 1. NVDA starten und Grundmenü öffnen

- **NVDA starten:**  
  NVDA per Desktop‑Icon oder Startmenü öffnen.  
- **Menü öffnen:**  
  `NVDA`‑Taste (meist Insert oder Caps Lock) + `N` → NVDA-Menü erscheint.

## 2. Autostart komplett ausschalten

- **Pfad:** `Einstellungen → Allgemein`  
- **Optionen:**  
  - Haken bei **„NVDA beim Windows-Start ausführen“** entfernen  
  - Falls vorhanden: Haken bei **„NVDA beim Anmelden automatisch starten“** entfernen  
→ NVDA läuft nur, wenn du es bewusst startest.

## 3. Sprachausgabe auf Minimum setzen

- **Pfad:** `Einstellungen → Sprachausgabe`  
- **Optionen:**  
  - Stimme auf eine neutrale Stimme stellen oder  
  - Lautstärke stark reduzieren, wenn du nur gelegentlich hören willst  
Wenn du wirklich gar keine Sprachausgabe brauchst:  
- **Sprachausgabe:** auf **sehr leise** und NVDA nur für Tests nutzen.

(„Keine Sprachausgabe“ ist je nach Version nicht direkt wählbar, daher hier der pragmatische Weg.)

## 4. NVDA-Modifikatortaste umlegen

Damit Insert für andere Programme frei bleibt:

- **Pfad:** `Einstellungen → Tastatur`  
- **Optionen:**  
  - **NVDA-Modifikatortaste:** auf **Caps Lock** setzen  
  - Prüfen, ob **„NVDA-Modifikatortaste als normale Taste verwenden“** deaktiviert ist  
→ Konflikte mit Insert‑Shortcuts anderer Programme werden minimiert.

## 5. Visuelle Hervorhebungen deaktivieren

Falls du keine zusätzlichen Rahmen oder Markierungen willst:

- **Pfad:** `Einstellungen → Visuelle Hervorhebung` (oder ähnlich benannt)  
- **Optionen:**  
  - Alle Hervorhebungs‑Optionen (Fokusrahmen, Objektmarkierungen etc.) deaktivieren  
→ NVDA verändert dein Bild nicht sichtbar.

## 6. Add-ons und Spezialfunktionen ausdünnen

- **Pfad:** `Extras → Add-ons verwalten`  
- **Optionen:**  
  - Alles deaktivieren, was du nicht bewusst nutzt  
- **Weitere Bereiche:**  
  - Braille-Unterstützung deaktivieren, wenn du sie nicht brauchst  
  - Entwickler‑/Debug‑Funktionen ausgeschaltet lassen  

## 7. Prüfen, dass NVDA wirklich „still“ ist

- NVDA schließen  
- Windows neu starten  
- Prüfen, ob NVDA **nicht automatisch** startet  
- Bei Bedarf NVDA manuell starten und schauen:  
  - Keine störenden Rahmen  
  - Insert funktioniert wie gewohnt  
  - Sprachausgabe nur, wenn du sie willst
