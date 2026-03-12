# 📊 NÁVOD: Jak používat Dashboard podnětů

## 🎯 Co Dashboard umí

Dashboard je centrální místo pro správu všech podnětů Místní komise. Nahrazuje Excel tabulky a poskytuje:

- ✅ **Přehled všech podnětů** v jedné tabulce
- ✅ **Sledování stavů** (Nové → Odesláno → Vyřízeno)
- ✅ **Detail podnětu** včetně mapy GPS
- ✅ **Export CSV** pro město
- ✅ **Automatické ukládání** do LocalStorage

---

## 🚀 RYCHLÝ START

### **Krok 1: Vytvoř podněty**

1. Otevři **zapis.html**
2. Vytvoř zápis z jednání
3. U bodů s usnesením klikni **"Vytvořit podnět z tohoto usnesení"**
4. Klikni **"Exportovat podněty"**
5. Stáhnou se JSON soubory (např. `podnet_MKHH_2026_03_12_c_2.json`)

### **Krok 2: Nahraj do Dashboardu**

1. Otevři **dashboard.html**
2. Klikni **"📁 Nahrát podněty (JSON)"** nebo přetáhni JSONy
3. Vyber všechny stažené JSON soubory najednou
4. Hotovo! Podněty se zobrazí v tabulce

### **Krok 3: Sleduj stavy**

1. Každý podnět má stav: **🆕 Nové**
2. Po odeslání městu klikni na badge → změní se na **📤 Odesláno**
3. Po vyřízení klikni znovu → **✅ Vyřízeno**
4. Stavy se automaticky ukládají

### **Krok 4: Export pro město**

1. Klikni **"📥 Export CSV"**
2. Stáhne se soubor `podnety_MK_Horni_Hanychov_2026-03-12.csv`
3. Otevři v Excelu nebo odešli městu

---

## 📋 KOMPLETNÍ WORKFLOW

### **Scénář: Jednání komise**

```
PŘED JEDNÁNÍM:
└─ Nic nepotřebuješ

BĚHEM JEDNÁNÍ:
├─ Otevři zapis.html
├─ Vyplň zápis
├─ U bodů s usnesením zaškrtni "Vytvořit podnět"
└─ Označ místa na mapě (GPS)

PO JEDNÁNÍ:
├─ Klikni "Exportovat podněty" v zápisu
├─ Stáhnou se JSONy (např. 5 souborů)
│
├─ Otevři dashboard.html
├─ Nahraj všech 5 JSONů najednou
├─ Zkontroluj že vypadají dobře
└─ (Data zůstanou v Dashboardu)

ODESLÁNÍ MĚSTU:
├─ V Dashboardu klikni "Export CSV"
├─ Otevři CSV v Excelu
├─ Připrav email (ručně nebo template)
├─ Pošli městu email + CSV
└─ V Dashboardu označ podněty jako "📤 Odesláno"

KDYŽ MĚSTO VYŘÍDÍ:
└─ V Dashboardu označ jako "✅ Vyřízeno"
```

---

## 🎨 FUNKCE DASHBOARDU

### **📁 Nahrát podněty**

- Klikni na tlačítko nebo přetáhni JSONy
- Můžeš nahrát více souborů najednou
- Duplicity se automaticky přeskakují
- Data se ukládají do LocalStorage

### **📊 Tabulka**

| Sloupec | Popis |
|---------|-------|
| **Usnesení** | Číslo usnesení (MKHH_2026_03_12 č. 2) |
| **Předmět** | Název podnětu |
| **Datum jednání** | Kdy byl schválen |
| **Stav** | 🆕 Nové / 📤 Odesláno / ✅ Vyřízeno |
| **GPS** | 📍 zelená = má GPS, šedá = bez GPS |
| **Akce** | 👁️ Detail, 🗑️ Smazat |

**Třídění:**
- Klikni na hlavičku sloupce → seřadí podle něj
- Druhý klik → obrátí pořadí

**Kliknutí na řádek:**
- Otevře detail podnětu
- Zobrazí GPS na mapě (pokud má)

### **🔄 Změna stavu**

Klikni na barevný badge se stavem:
```
🆕 Nové  →  klik  →  📤 Odesláno  →  klik  →  ✅ Vyřízeno  →  klik  →  🆕 Nové
                     (cyklus)
```

**Kdy měnit:**
- **📤 Odesláno** → Když pošleš email městu
- **✅ Vyřízeno** → Když město potvrdí vyřízení

### **👁️ Detail podnětu**

Zobrazí:
- Číslo usnesení
- Předmět
- Text usnesení
- Podrobný popis
- Datum jednání
- Počet příloh
- **Mapu s GPS** (pokud má lokalizaci)

### **📥 Export CSV**

Stáhne soubor ve formátu:
```csv
Číslo usnesení;Předmět;Datum jednání;Stav;Text usnesení;...;GPS LAT;GPS LNG
MKHH_2026_03_12 č. 2;Oprava chodníku;12.3.2026;Odesláno;...;50.740284;15.016967
```

**Otevře se v Excelu** s středníky jako oddělovač.

### **🗑️ Vymazat vše**

- Smaže VŠECHNY podněty z Dashboardu
- ⚠️ Tuto akci nelze vrátit!
- JSON soubory na PC zůstanou (ty můžeš znovu nahrát)

---

## 💾 JAK SE DATA UKLÁDAJÍ

### **LocalStorage (prohlížeč)**
```
Dashboard ukládá:
├─ Seznam všech podnětů
├─ Jejich stavy
├─ Poznámky
└─ Data změn

Automaticky při:
├─ Nahrání nového podnětu
├─ Změně stavu
└─ Smazání podnětu
```

### **Co to znamená:**

✅ **Výhody:**
- Data zůstávají i po zavření prohlížeče
- Není potřeba internet
- Rychlé načítání

⚠️ **Omezení:**
- Data jen v TOMHLE prohlížeči na TOMHLE PC
- Pokud jdeš na jiný PC → musíš mít JSONy s sebou
- Vyčištění cache smaže data (záloha = JSONy na disku)

### **Záloha:**

**Doporučení:**
```
📁 Tvůj počítač
└── mk-hanychov-data/
    ├── zapisy/
    │   └── zapis_2026-03-12.json
    └── podnety/
        ├── podnet_MKHH_2026_03_12_c_1.json
        ├── podnet_MKHH_2026_03_12_c_2.json
        └── ... (archiv všech JSONů)
```

Pokud se něco pokazí → prostě znovu nahraješ JSONy z archivu.

---

## 🔍 ŘEŠENÍ PROBLÉMŮ

### ❌ "Nevidím žádné podněty"

**Řešení:**
1. Zkontroluj že jsi nahrál JSONy (klikni "Nahrát podněty")
2. JSONy musí být z exportu ze zápisu nebo formuláře
3. Zkus kliknout "🔄 Obnovit"

### ❌ "CSV se divně otevírá v Excelu"

**Řešení:**
1. Excel → Data → Z textu/CSV
2. Vyber stažený CSV soubor
3. Oddělovač: **Středník** (;)
4. Kódování: **UTF-8**
5. Importuj

### ❌ "Ztratily se mi podněty"

**Možné příčiny:**
- Vyčistil jsi cache prohlížeče
- Otevřel jsi Dashboard v jiném prohlížeči
- Otevřel jsi Dashboard v anonymním režimu

**Řešení:**
- Nahraj JSONy znovu (z archivu na disku)
- Data se obnoví

### ❌ "Duplicitní podněty"

Dashboard automaticky **přeskakuje duplicity** podle čísla usnesení.

Pokud nahraješ stejný podnět 2x → přidá se jen jednou.

---

## 📊 STATISTIKY

Dashboard zobrazuje:

```
📋 Celkem: 12       → Počet všech podnětů
🆕 Nové: 3          → Zatím neodeslané
📤 Odesláno: 5      → Odeslané městu
✅ Vyřízeno: 4      → Vyřízené městem
```

Aktualizuje se automaticky při změnách.

---

## 🎯 TIPY & TRIKY

### **Tip 1: Hromadná změna stavů**

Pokud odesíláš 5 podnětů najednou:
1. Označ všech 5 jako "Odesláno"
2. Exportuj CSV
3. Odešli městu

### **Tip 2: Filtrování v Excelu**

Po exportu CSV:
1. Otevři v Excelu
2. Data → Filtr
3. Filtruj podle sloupce "Stav"
4. Zobrazíš jen "Nové" nebo "Odesláno"

### **Tip 3: Roční přehled**

Export CSV můžeš použít pro:
- Roční zprávu komise
- Statistiku vyřízených podnětů
- Prezentaci pro občany

### **Tip 4: Sdílení s členy**

Pokud chceš sdílet Dashboard s ostatními členy:
1. Každý si otevře dashboard.html na webu
2. Nahrajete stejné JSONy
3. Každý vidí stejná data (ale stavy se nesynchronizují)

**Lepší:** Používejte jeden PC nebo sdílejte JSONy emailem.

---

## ✅ CHECKLIST pro každé jednání

```
PO JEDNÁNÍ:
[ ] Exportovat podněty ze zápisu (JSONy)
[ ] Nahrát do Dashboardu
[ ] Zkontrolovat GPS u všech
[ ] Exportovat CSV
[ ] Odeslat městu
[ ] Označit jako "Odesláno"

KDYŽ MĚSTO ODPOVÍ:
[ ] Označit jako "Vyřízeno"
[ ] Případně přidat poznámku
```

---

## 🆘 Potřebuješ pomoct?

- ❓ Něco nefunguje?
- 💡 Nápad na vylepšení?
- 🐛 Našel jsi chybu?

Napiš mi! 💬

---

**Dashboard je hotový a připravený k použití!** 🎉
