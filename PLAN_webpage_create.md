# Terv: Qsoft főoldal — modern HTML/CSS/JS főoldal készítése

## Context
A qsoft.hu főoldalának modern, statikus HTML újratervezése. A tartalom már megvan (`pages/01_fooldal/content.md`), a design alapja a meglévő `header-demo.html` fájl (Planer font, `#1e3184` brand szín). Az új fájl neve: `index.html` a repo gyökerében.

---

## Design döntések (grill-me session eredménye)

| Szempont | Döntés |
|----------|--------|
| Tech stack | Pure HTML + CSS (header-demo.html kiterjesztése), nincs Tailwind CDN |
| Font | Planer (woff2, már van `fonts/` mappában) + system-ui fallback |
| Elsődleges szín | `#1e3184` (Qsoft brand navy) |
| Logo | `<span class="logo-q">Q</span><span class="logo-soft">soft</span>` — header-demo.html-ből |
| JS | Teljes fancy csomag: smooth scroll + fade-in + counter animáció + sticky header + dropdown + hamburger |

---

## Szekciók sorrendje

1. **Header** — sticky, fehér bg, logo + nav dropdown + hamburger mobilon
2. **Hero** — h1 + alcím + 2 CTA gomb (fehér bg, fade-in animáció)
3. **Statisztikák sáv** — `#1e3184` bg, fehér, 4 szám counter animációval
4. **4 kiemelt termék** — 2×2 kártyarács (SUP, TIP, Online Lekérdezés, Miért válassza)
5. **Modulok** — 3×3 kompakt rács, `#f9fafb` bg, ikon + modulnév + 1 sor leírás
6. **Vélemények** — 3 kártya egymás mellett, avatar fotókkal (meglévő képek)
7. **Különleges ajánlat** — kártya highlight, keret + badge, 20% + ingyenes telepítés
8. **Kapcsolattartók** — 3 kártya fotókkal (qsoft_gabika/timi/karcsi)
9. **Lábléc** — `#111827` bg, 3 oszlop: logo+leírás | nav linkek | elérhetőség

---

## Reszponzivitás
- Desktop (≥1024px): teljes layout
- Tablet (768–1023px): 2 oszlopos rácsok
- Mobil (<768px): 1 oszlop, hamburger menü

---

## JS funkciók (inline `<script>`)

1. **Sticky header** — scrollnál árnyék jelenik meg a fejlécen
2. **Hamburger mobilmenü** — toggle `.nav-open` class
3. **Dropdown navigáció** — „Szoftverek" hover/kattintásra almenü (SUP, TIP, Online Lekérdezés, Rendszerbevezetés, Referencia lista)
4. **Smooth scroll** — `<a href="#szekció">` linkek simán görgetnek
5. **IntersectionObserver fade-in** — szekciók belépéskor `opacity: 0 → 1` + `translateY(20px → 0)` animáció
6. **Counter animáció** — a statisztika számai 0-tól felszámolnak, amikor belépnek a viewport-ba
7. **Kártya hover** — CSS `transform: translateY(-4px)` + árnyék mélyítés

---

## Felhasznált meglévő képek (`pages/01_fooldal/images/`)

| Szekció | Kép |
|---------|-----|
| Vélemények | `Maria-125x125.png`, `katalin-125x125.png`, `Ajtai_Karolyne-125x125.jpg` |
| Kapcsolattartók | `qsoft_gabika-360x455.jpg`, `qsoft_timi-360x455.jpg`, `qsoft_karcsi-360x455.jpg` |
| Termék/modul ikonok | Unicode emoji vagy inline SVG |

---

## Kritikus fájlok

- **Olvasni:** `header-demo.html` — CSS változók, logo markup, font deklarációk
- **Olvasni:** `pages/01_fooldal/content.md` — szövegek, statisztikák, modullisták
- **Létrehozni:** `index.html` (repo gyökér) — minden CSS + JS inline, 1 önálló fájl

---

## Ellenőrzés
1. `index.html` megnyitása böngészőben (`file://`) — minden szekció megjelenik
2. Ablak keskenyítése mobilra — hamburger menü, 1 oszlopos rácsok
3. Lefelé görgetés — counter animáció elindul, fade-in szekciók megjelennek
4. „Szoftverek" hover — dropdown almenü megjelenik
