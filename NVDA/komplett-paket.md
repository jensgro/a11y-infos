# 🧭 NVDA‑Dokumentation

**Checkliste + Testprotokoll + WCAG‑Referenzen**



# 📌 Inhalt

1. NVDA‑Checkliste
2. NVDA‑Testprotokoll
3. Hinweise für sehende Tester
4. NVDA‑Shortcuts
5. WCAG‑Mapping (alle Prüfpunkte → WCAG‑Erfolgskriterien)



# ✅ 1. NVDA‑Checkliste

## **Vorbereitung**

* ☐ NVDA installiert
* ☐ NVDA gestartet (`Ctrl+Alt+N`)
* ☐ Nur Tastatur verwenden
* ☐ Wichtige NVDA‑Shortcuts bekannt
  * `Tab` / `Shift+Tab` – Fokusnavigation
  * `H` – Überschriften
  * `D` – Landmarken
  * `NVDA+F7` – Elementliste
  * `NVDA+Pfeiltasten` – Lesen
* WCAG‑Bezug: **Keyboard**, **No Keyboard Trap**

## **Strukturprüfung**

### **Überschriften**

* ☐ Überschriftenhierarchie logisch
* ☐ Keine Ebenen übersprungen
* ☐ NVDA erkennt alle Überschriften
* Weiter testen: Überschriften prüfen
* WCAG‑Bezug: **1.3.1 Info and Relationships**

### **Landmarks**

* ☐ `header`
* ☐ `nav`
* ☐ `main`
* ☐ `footer`
* ☐ Weitere Regionen (aside, form, search)
* Weiter testen: Landmarken testen
* WCAG‑Bezug: **1.3.1 Info and Relationships**, **2.4.1 Bypass Blocks**

### **Listen & Tabellen**

* ☐ Listen werden als Listen vorgelesen
* ☐ Tabellen haben Header
* ☐ Tabellenzellen werden korrekt angesagt
* Weiter testen: Tabellen prüfen
* WCAG‑Bezug: **1.3.1 Info and Relationships**, **1.3.2 Meaningful Sequence**

## **Navigation & Fokus**

* ☐ Fokusreihenfolge logisch
* ☐ Keine Fokusfallen
* ☐ Skip‑Links vorhanden
* ☐ Skip‑Links funktionieren
* Weiter testen: Fokusreihenfolge
* WCAG‑Bezug:
  * **2.4.3 Focus Order**
  * **2.1.2 No Keyboard Trap**
  * **2.4.1 Bypass Blocks**

## **Interaktive Elemente**

### **Buttons & Links**

* ☐ Buttons korrekt ausgezeichnet
* ☐ Links eindeutig benannt
* ☐ Linktexte nicht doppeldeutig
* Weiter testen: Buttons & Links
* WCAG‑Bezug:
  * **4.1.2 Name, Role, Value**
  * **2.4.4 Link Purpose**

### **Formulare**

* ☐ Labels korrekt zugeordnet
* ☐ Fehlermeldungen werden vorgelesen
* ☐ Pflichtfelder erkennbar
* ☐ ARIA‑Status korrekt
* Weiter testen: Formulare testen
* WCAG‑Bezug:
  * **3.3.2 Labels or Instructions**
  * **3.3.1 Error Identification**
  * **4.1.2 Name, Role, Value**

## **ARIA & Semantik**

* ☐ Rollen korrekt (Button, Checkbox, Dialog, Menü)
* ☐ Zustände korrekt (expanded, collapsed, checked)
* ☐ ARIA‑Live‑Regionen vorhanden
* ☐ Dynamische Inhalte werden angesagt
* Weiter testen: ARIA‑Rollen
* WCAG‑Bezug:
  * **4.1.2 Name, Role, Value**
  * **1.3.1 Info and Relationships**
  * **4.1.3 Status Messages**

## **Alternative Texte**

* ☐ Alt‑Texte sinnvoll
* ☐ Keine redundanten Beschreibungen
* ☐ Dekorative Bilder korrekt markiert
* Weiter testen: Alt‑Texte prüfen
* WCAG‑Bezug: **1.1.1 Non‑text Content**

## **Dynamische Inhalte**

* ☐ Modale Dialoge fangen Fokus ein
* ☐ Overlays verhindern Fokusverlust
* ☐ AJAX‑Updates werden angesagt
* Weiter testen:
  * Modale Dialoge
  * Overlays
  * Statusupdates
* WCAG‑Bezug:
  * **2.4.3 Focus Order**
  * **4.1.3 Status Messages**
  * **2.1.2 No Keyboard Trap**

# 📋 2. NVDA‑Testprotokoll

## **Allgemeine Informationen**

* **Getestete Seite:**
* **Datum:**
* **Tester:**
* **NVDA‑Version:**
* **Browser:**



## **Seitenstruktur**

### **Überschriften**

* ☐ Korrekte Reihenfolge
* ☐ Keine ausgelassenen Ebenen
* **Kommentar:**

### **Landmarks**

* ☐ header
* ☐ nav
* ☐ main
* ☐ footer
* **Kommentar:**

### **Listen & Tabellen**

* ☐ Listen korrekt
* ☐ Tabellen korrekt lesbar
* **Kommentar:**



## **Navigation & Fokus**

* ☐ Fokusreihenfolge logisch
* ☐ Keine Fokusfallen
* ☐ Skip‑Links funktionieren
* **Kommentar:**



## **Interaktive Elemente**

### **Buttons & Links**

* ☐ Buttons korrekt ausgezeichnet
* ☐ Links eindeutig benannt
* **Kommentar:**

### **Formulare**

* ☐ Labels korrekt
* ☐ Fehlermeldungen werden vorgelesen
* ☐ Pflichtfelder erkennbar
* **Kommentar:**



## **ARIA & Semantik**

* ☐ Rollen korrekt
* ☐ Zustände korrekt
* ☐ Live‑Regionen funktionieren
* **Kommentar:**



## **Alternative Texte**

* ☐ Alt‑Texte sinnvoll
* ☐ Dekorative Bilder korrekt markiert
* **Kommentar:**



## **Dynamische Inhalte**

* ☐ Modale Dialoge: Fokus eingeschlossen
* ☐ Overlays: Fokus bleibt im Overlay
* ☐ AJAX‑Updates werden angesagt
* **Kommentar:**



## **Gesamtbewertung**

* **Barrieren gefunden:**
* **Kritische Probleme:**
* **Empfohlene Maßnahmen:**



# 👁️ 3. Hinweise für sehende Tester

* Nutze **nur die Tastatur**.
* Höre bewusst auf die **Strukturansagen**.
* Vermeide visuelle Orientierung.
* Prüfe: *Passt das, was NVDA sagt, zu dem, was ich sehe?*
* Diskrepanzen sind fast immer **WCAG‑Verstöße**.



# ⌨️ 4. NVDA‑Shortcuts (Kurzreferenz)

* **Navigation**

  * `Tab` / `Shift+Tab` – Fokus
  * `H` – Überschriften
  * `D` – Landmarken
  * `K` – Links
  * `NVDA+F7` – Elementliste

* **Lesen**

  * `NVDA+Pfeil runter` – Zeile lesen
  * `NVDA+Pfeil hoch` – vorherige Zeile
  * `NVDA+Pfeil rechts` – Wort weiter
  * `NVDA+Pfeil links` – Wort zurück

* **Elementinfo**

  * `NVDA+Tab` – Fokusansage
  * `NVDA+F` – Formatierung



# 📚 5. WCAG‑Mapping (alle Prüfpunkte → WCAG)

| Bereich | Prüfpunkte | WCAG‑Erfolgskriterium | 
|-- | -- | -- | 
| Struktur | Überschriften | **1.3.1 Info and Relationships** | 
| Struktur | Landmarks | **1.3.1**, **2.4.1** | 
| Struktur | Listen & Tabellen | **1.3.1** | 
| Navigation | Fokusreihenfolge | **2.4.3 Focus Order** | 
| Navigation | Keine Fokusfallen | **2.1.2 No Keyboard Trap** | 
| Navigation | Skip‑Links | **2.4.1 Bypass Blocks** | 
| Interaktiv | Buttons & Links | **4.1.2 Name, Role, Value** | 
| Interaktiv | Linkzweck | **2.4.4 Link Purpose** | 
| Formulare | Labels | **3.3.2 Labels or Instructions** | 
| Formulare | Fehler | **3.3.1 Error Identification** | 
| ARIA | Rollen & Zustände | **4.1.2** | 
| ARIA | Live‑Regionen | **4.1.3 Status Messages** | 
| Bilder | Alt‑Texte | **1.1.1 Non‑text Content** | 
| Dynamik | Modale Dialoge | **2.4.3** | 
| Dynamik | Overlays | **2.1.2** | 
| Dynamik | AJAX‑Updates | **4.1.3** | 

