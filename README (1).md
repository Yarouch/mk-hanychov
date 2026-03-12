# 🏛️ Místní komise Horní Hanychov - Digitální nástroje

Webová aplikace pro vytváření zápisů z jednání a správu podnětů pro Místní komisi Horní Hanychov, Liberec.

## 📋 Co obsahuje

- **Zápis z jednání** - kompletní formulář s docházkou, programem, hlasováním, usneseními
- **Formulář podnětu** - samostatný podnět s možností označení místa na mapě
- **Interaktivní mapy** - GPS lokalizace míst podnětů pomocí OpenStreetMap

## 🚀 Rychlý start

### Nahrání na GitHub Pages

1. **Vytvoř nový repozitář na GitHubu:**
   - Jdi na https://github.com/new
   - Název: `mk-horni-hanychov` (nebo jiný)
   - Public ✓
   - Add README ✓
   - Create repository

2. **Nahraj soubory:**
   - Klikni na "Add file" → "Upload files"
   - Přetáhni tyto soubory:
     - `index.html`
     - `zapis.html` (přejmenuj `zapis_WITH_MAP_v3_FINAL.html`)
     - `podnet.html` (přejmenuj `formular_podnetu_WITH_MAP_v3_FINAL.html`)
     - `README.md` (tento soubor)
   - Commit changes

3. **Zapni GitHub Pages:**
   - Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` → `/ (root)` → Save
   - Počkaj 1-2 minuty

4. **Otevři web:**
   - URL bude: `https://[tvůj-github-nick].github.io/mk-horni-hanychov/`

## 📁 Struktura souborů

```
mk-horni-hanychov/
├── index.html          # Vstupní stránka
├── zapis.html          # Zápis z jednání
├── podnet.html         # Formulář podnětu
└── README.md           # Tento soubor
```

## 💾 Jak funguje ukládání dat

- **LocalStorage** - Data se ukládají ve vašem prohlížeči
- **JSON export** - Zápisy a podněty lze stáhnout jako JSON
- **PDF export** - Zápisy lze vytisknout / uložit jako PDF
- **Žádný server** - Aplikace běží čistě v prohlížeči, data nikam neposíláme

## 🗺️ Funkce map

- **OpenStreetMap** - Zdarma, bez API klíčů
- **Leaflet.js** - Knihovna pro interaktivní mapy
- **GPS souřadnice** - Přesné označení míst podnětů
- **Střed mapy** - Zastávka Spáleniště (50.7402839, 15.0169669)

## 🔒 Bezpečnost

- **CSP (Content Security Policy)** - Ochrana proti XSS útokům
- **Žádné unsafe-inline** - Veškerý kód s nonce
- **Lokální data** - Nic se neposílá na server

## 📝 Workflow

### Typické použití:

1. **Před jednáním:**
   - Otevři `zapis.html`
   - Vyplň základní info (datum, místo)

2. **Během jednání:**
   - Zaznamenávej docházku
   - Přidávej body programu
   - Zapisuj diskuzi a usnesení
   - Označuj místa na mapě
   - Zaznamenávej hlasování

3. **Po jednání:**
   - Exportuj zápis do PDF (pro schválení)
   - Exportuj podněty do JSON
   - Importuj JSON do formulářů podnětů
   - Odešli městu

## 🛠️ Technologie

- HTML5
- CSS3 (žádné frameworky)
- Vanilla JavaScript (ES6+)
- OpenStreetMap + Leaflet.js
- LocalStorage API

## 📞 Kontakt

**Místní komise Horní Hanychov**
- Předseda: Jaroslav Podsedník
- Magistrát města Liberec

## 📄 Licence

Vytvořeno pro interní použití Místní komise Horní Hanychov.

---

*Vytvořeno s pomocí Claude (Anthropic) • 2026*
