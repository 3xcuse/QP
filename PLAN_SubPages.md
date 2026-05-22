# Terv: Szoftverek aloldalak — 15 HTML oldal az index.html designjával

## Context
Az `index.html` főoldal már elkészült (Planer font, `#1e3184` brand szín, sticky header, fade-in animációk, hero MP4 videó 55/45 split layoutban). A `pages/` mappában 15 aloldal tartalmát már lementettük szöveggel és képekkel. A feladat: minden aloldalhoz önálló HTML fájlt létrehozni a repo gyökerében, az eredeti szövegekkel és képekkel, az index.html design rendszerével.

---

## Létrehozandó fájlok (repo gyökér)

| Fájlnév | Forrás mappa | Cím |
|---------|-------------|-----|
| `sup-integralt.html` | `pages/02_sup-integralt/` | SUP Integrált Vállalatirányítási Rendszer |
| `mukodesi-feltetelek.html` | `pages/03_mukodesi-feltetelek/` | Működési feltételek |
| `szamviteli-modul.html` | `pages/04_szamviteli-modul/` | Számvitel modul |
| `penzugyi-modul.html` | `pages/05_penzugyi-modul/` | Pénzügy modul |
| `targyi-eszkoz-modul.html` | `pages/06_targyi-eszkoz-modul/` | Tárgyi eszköz modul |
| `raktari-keszlet.html` | `pages/07_raktari-keszlet/` | Raktári készlet és Áruforgalmi modul |
| `szamlazas-modul.html` | `pages/08_szamlazas-modul/` | Számlázás modul |
| `szerzodes-nyilvantartas.html` | `pages/09_szerzodes-nyilvantartas/` | Szerződés nyilvántartás modul |
| `hazi-penztar-modul.html` | `pages/10_hazi-penztar-modul/` | Házi Pénztár modul |
| `merleg-es-elemzes-modul.html` | `pages/11_merleg-es-elemzes-modul/` | Mérleg és elemzés modul |
| `excel-fugvenycsomag.html` | `pages/12_excel-fugvenycsomag/` | Excel függvénycsomag |
| `tip-iratkezelo.html` | `pages/13_tip-iratkezelo/` | TIP Iratkezelő és Információs Rendszer |
| `online-informacios-lekerdezesek.html` | `pages/14_online-informacios-lekerdezesek/` | Online Információs Lekérdezések |
| `vasarlas-es-rendszerbevezetes.html` | `pages/15_vasarlas-es-rendszerbevezetes/` | Vásárlás és rendszerbevezetés |
| `referencia-lista.html` | `pages/16_referencia-lista/` | Referencia lista |

---

## Design rendszer (index.html-ből átemelve)

Minden fájl **önálló, self-contained HTML** — azonos `<style>` és `<script>` blokk, mint az `index.html`-ben.

### Átemelt komponensek
- `@font-face` Planer Regular + DemiBold (`fonts/...`)
- `:root` CSS változók (`--blue: #1e3184`, szürke skála, árnyékok, radius)
- Header CSS + HTML (sticky, backdrop-blur, dropdown, hamburger, mobile nav)
- Footer CSS + HTML (sötét `#0f172a`, 3 oszlop)
- Fade-in, button, card, section stílusok
- JS blokk (sticky shadow, hamburger, dropdown, smooth scroll, IntersectionObserver fade-in)

### Nav link frissítés
Az aloldalakon valódi fájlnév linkek (nem `#anchor`):
```html
<a href="index.html">Főoldal</a>
<a href="sup-integralt.html">SUP Rendszer</a>
<a href="tip-iratkezelo.html">TIP Iratkezelő</a>
<a href="excel-fugvenycsomag.html">Excel függvénycsomag</a>
<a href="referencia-lista.html">Referencia lista</a>
```

---

## Aloldalak sablon szerkezete

```html
<section class="page-hero">
  <div class="container">
    <div class="breadcrumb">
      <a href="index.html">Főoldal</a> › <a href="sup-integralt.html">Szoftverek</a> › Oldalcím
    </div>
    <h1 class="page-hero-title fade-in">Oldalcím</h1>
    <p class="page-hero-sub fade-in fade-in-delay-1">Bevezető szöveg</p>
  </div>
</section>
```

### Kiegészítő CSS (minden aloldalon)
```css
.page-hero { padding:120px 0 56px; background:linear-gradient(160deg,#fff 70%,var(--blue-light)); border-bottom:3px solid var(--blue); }
.page-hero-title { font-size:clamp(28px,4vw,44px); font-weight:600; }
.breadcrumb { font-size:13px; color:var(--gray-500); margin-bottom:16px; }
.feature-cols { display:grid; grid-template-columns:1fr 1fr; gap:40px; }
.feature-list li::before { content:'✓'; color:var(--blue); font-weight:700; }
.screenshot-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:16px; }
.logo-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(160px,1fr)); gap:16px; }
.cta-bar { background:var(--blue); color:#fff; padding:48px 0; text-align:center; }
@media (max-width:767px) {
  .feature-cols { grid-template-columns:1fr; }
  .screenshot-grid { grid-template-columns:repeat(2,1fr); }
}
```

---

## Oldalankénti tartalom és layout

### 1. `sup-integralt.html`
- Page hero: cím + intro szöveg (pages/02_sup-integralt/content.md bevezető)
- 19 bullet jellemző → 2 oszlopos lista
- 12 modul → `.modules-grid` (3×4) kártyák, minden kártya linkkel a modul HTML-re
- Képek: `SUP-1.jpg` + `MERLEG-1.jpg` → 2 oszlopos képrács
- CTA: „Kérjen ajánlatot" → `vasarlas-es-rendszerbevezetes.html`

### 2. `mukodesi-feltetelek.html`
- Page hero: cím + intro (kliens-szerver architektúra)
- Kép: `mukodesi_feltetelek.png` teljes szélességben
- 4 szekció kártya (2×2): Szerver HW | Szerver SW | Kliens HW | Kliens SW

### 3–10. Modul oldalak (egységes template)
**Érintett:** szamviteli, penzugyi, targyi-eszkoz, raktari-keszlet, szamlazas, szerzodes-nyilvantartas, hazi-penztar, merleg-es-elemzes

```
Page hero → 2 oszlop [Felépítése lista | Főbb jellemzők lista] → Screenshot grid (3 oszlopos) → CTA sáv
```

| Oldal | Felépítése (db) | Főbb jellemzők (db) | Képek (db) |
|-------|-----------------|---------------------|------------|
| Számviteli | 10 | 20 | 12 |
| Pénzügyi | 7 | 18 | 7 |
| Tárgyi eszköz | 3 | 15 | 9 |
| Raktári készlet | 15 | 25+ | 11 |
| Számlázás | 3 | 15 | 4 |
| Szerződés nyilvántartás | 8 | 7 | 3 |
| Házipénztár | 4 | 9 | 3 |
| Mérleg és elemzés | 5 | 18 | 6 |

### 11. `excel-fugvenycsomag.html`
- Page hero + 3 feature kártya: Egyedi elemzés | Több cég egy riportban | Többéves összehasonlítás
- 11 kép (EX_01–EX_11) → 3 oszlopos screenshot rács

### 12. `tip-iratkezelo.html`
- Page hero + logo (`Tip_web_logo-1.png` jobbra float)
- 4 feature kártya alkalmazási területek (2×2)
- QR kód szekció: kék háttér, szöveg + `szamla.jpg`

### 13. `online-informacios-lekerdezesek.html`
- Page hero + logo (`OIL_web_logo-1.png`)
- 7 kimutatás → numbered list kártyákban
- Nyelvi badge-ek: HU | EN | IT
- 6+1 screenshot (OIL_01–OIL_06 + `wg-1024x550.png`)

### 14. `vasarlas-es-rendszerbevezetes.html`
- Page hero
- 5 lépéses folyamat (timeline/accordion): Kapcsolatfelvétel → Árajánlat → Szerződéskötés → Üzembe helyezés → Támogatás
- Képek: `bevezetes2.png`, `ajanlat.jpg`, `callcenter.jpg`

### 15. `referencia-lista.html`
- Page hero: cím + ~900 ügyfél intro szöveg
- 21 céglogó → `logo-grid` (minden logo fehér kártyán, középre igazítva)
- CTA: „Legyen Ön is ügyfelünk"

---

## index.html nav link frissítés

A header dropdown `#anchor` hivatkozásai cserélendők:
```html
<a href="sup-integralt.html">SUP Vállalatirányítási Rendszer</a>
<a href="tip-iratkezelo.html">TIP Iratkezelő Rendszer</a>
<a href="online-informacios-lekerdezesek.html">Online Információs Lekérdezések</a>
<a href="excel-fugvenycsomag.html">Excel függvénycsomag</a>
<a href="referencia-lista.html">Referencia lista</a>
```

---

## Git stratégia

```
git add *.html
git commit -m "Szoftverek aloldalak (15 db) — eredeti tartalommal, új designnal"
git push origin master
```

---

## Ellenőrzés
1. Minden HTML megnyitható `file://`-ból
2. Breadcrumb linkek működnek (index.html ↔ aloldal)
3. Header dropdown az aloldalon is működik (hamburger, szoftverek dropdown)
4. Képek betöltődnek (`pages/NN_slug/images/` útvonalak helyesek)
5. Fade-in animációk görgetésre működnek
6. Footer linkek helyes fájlokra mutatnak
7. Mobilon (767px alatt) 1 oszlopos, hamburger megjelenik
