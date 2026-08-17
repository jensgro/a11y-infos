# NVDA für Tests einrichten

## Übersicht der Konfiguration

| Bereich | Einstellung |
| --- | --- |
| Autostart | Aus |
| Sprachausgabe | Keine / sehr leise |
| NVDA‑Modifikatortaste | Caps Lock |
| Visuelle Hervorhebung | Aus |
| Add-ons | Nur das Nötigste |
| Braille | Aus |
| Tastaturhilfe | Aus |
| Fokus-Tracking | Standard |

Die optimale NVDA‑Konfiguration für  *Gelegenheitsnutzer* besteht darin, NVDA möglichst **ruhig**, **unauffällig** und **leicht steuerbar** zu machen. 


## Grundkonfiguration für seltene Nutzung
Diese Einstellungen sorgen dafür, dass NVDA *nur aktiv ist, wenn du es bewusst startest*.

### Autostart deaktivieren
- NVDA öffnen  
- *Einstellungen → Allgemein*  
- Haken bei **„NVDA beim Windows-Start ausführen“** entfernen  
- Optional: **„NVDA beim Anmelden automatisch starten“** ebenfalls deaktivieren  

Damit bleibt dein System komplett NVDA‑frei, bis du es manuell startest.


### Sprachausgabe minimal halten
Wenn du nicht blind bist, willst du *vermutlich* **keine dauerhafte Sprachausgabe**.

- *Einstellungen → Sprachausgabe*  
- Stimme auf **„Keine Sprachausgabe“** setzen  
  oder  
- Lautstärke stark reduzieren  

### Fokus-Hervorhebung deaktivieren
NVDA kann visuelle Rahmen um UI‑Elemente zeichnen. Für Sehende oft störend.

- *Einstellungen → Visuelle Hervorhebung*  
- Alle Optionen deaktivieren  

Allerdings sind diese Rahmen auch eine sehr gute Hilfe zur Orientierung. Es lohnt sich also, mit dieser Einstellung zu experimentieren.

### Tastaturkürzel entschärfen
NVDA nutzt viele **Insert‑Kombinationen** (also mit der Einfg/Insert-Taste), die mit anderen Apps kollidieren können.

- *Einstellungen → Tastatur*  
- NVDA‑Modifikatortaste auf **Caps Lock** setzen  
  → Insert bleibt frei für andere Programme

- In derselben Ansicht:  
  - Haken bei **„NVDA-Modifikatortaste als normale Taste verwenden“** entfernen  
  - Seltene Funktionen deaktivieren (z. B. „Tastaturhilfe“)

Dadurch werden unnötige Hotkeys abgeschaltet.

### Add-ons deaktivieren
NVDA kann Add-ons laden, die du nicht brauchst.

- *Extras → Add-ons verwalten*  
- Alles deaktivieren, was du nicht aktiv nutzt  

Das reduziert Hintergrundaktivität und potenzielle Konflikte.

### Oberfläche vereinfachen
NVDA hat viele Features, die du als Sehender nicht brauchst.

- **Braille-Unterstützung**  
- **Objektnavigation** (falls du sie nie nutzt)  
- **Bildschirmvorlese-Modi** wie „Lesemodus“  
- **Erweiterte Entwicklerfunktionen**  

---

## Die empfohlene Minimal-Konfiguration 

Diese Kombination ist für Gelegenheitsnutzer am angenehmsten:

| Bereich | Einstellung |
|--------|-------------|
| Autostart | Aus |
| Sprachausgabe | Keine / sehr leise |
| NVDA‑Modifikatortaste | Caps Lock |
| Visuelle Hervorhebung | Aus |
| Add-ons | Nur das Nötigste |
| Braille | Aus |
| Tastaturhilfe | Aus |
| Fokus-Tracking | Standard |


## Probleme durch die Installation von NVDA?

**Nein, NVDA verursacht unter Windows 11 normalerweise keine systemweiten Probleme**, auch wenn du es nur selten nutzt. Es ist leichtgewichtig, sauber programmiert und greift nicht tief ins System ein. Die meisten Nutzer – auch sehende – merken **keine negativen Nebenwirkungen**.


### Was NVDA auf deinem System tatsächlich verändert

- **Ein Hintergrunddienst (nvda.exe)**, der nur läuft, wenn du NVDA startest.  
- **Ein Tastatur-Hook**, damit NVDA seine eigenen Shortcuts erkennt.  
- **Optionale Sprachausgaben** (SAPI5 oder eSpeak).  
- **Ein Eintrag im Autostart**, falls du das aktivierst (standardmäßig *nicht*).

NVDA ersetzt **keine Systemkomponenten**, verändert keine Registry-Bereiche außerhalb seiner eigenen Einstellungen und installiert keine Treiber.


### Bekannte Probleme – realistisch eingeordnet
Hier die Punkte, die gelegentlich auftreten können, aber nur in sehr speziellen Situationen:

- **Tastaturkürzel-Konflikte** — Wenn du Apps nutzt, die dieselben Hotkeys wie NVDA verwenden (z. B. Insert‑Kombinationen).  
- **Leicht erhöhte CPU-Last** — Nur während NVDA aktiv ist, weil es ständig UI-Elemente ausliest.  
- **Sprachausgabe stört Audio-Apps** — Selten, meist nur bei professionellen DAWs.  
- **Autostart versehentlich aktiviert** — Dann startet NVDA bei jedem Windows-Login, was du aber leicht abschalten kannst.

Keiner dieser Punkte betrifft dich, **wenn NVDA nicht läuft**. NVDA ist komplett passiv, solange du es nicht startest.


