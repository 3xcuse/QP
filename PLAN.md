# Terv: QP repo — qsoft.hu oldalak tartalmának mentése

## Context
A https://github.com/3xcuse/QP repóban lévő `context.md` egy link tree, amely a qsoft.hu összes aloldalát felsorolja. A feladat: minden URL-t meglátogatni, a szöveget és a képeket elmenteni a repóba, majd oldalanként pusholni. A jelenlegi munkamappa IS ez a repo.

## Mappa struktúra
```
pages/
  01_fooldal/
    content.md        ← teljes szöveg, eredeti formában
    images/
      kep1.jpg
      ...
  02_sup-integralt/
    content.md
    images/
  ...
```

## Az összes feldolgozandó URL (36 db)

| # | Státusz | URL |
|---|---------|-----|
| 01 | ✅ KÉSZ | https://www.qsoft.hu/ |
| 02 | ✅ KÉSZ | https://www.qsoft.hu/sup-integralt-vallalatiranyitasi-rendszer/ |
| 03 | ✅ KÉSZ | https://www.qsoft.hu/mukodesi-feltetelek/ |
| 04 | ⏳ | https://www.qsoft.hu/course/szamviteli-modul/ |
| 05 | ⏳ | https://www.qsoft.hu/course/penzugyi-modul/ |
| 06 | ⏳ | https://www.qsoft.hu/course/targyi-eszkoz-modul/ |
| 07 | ⏳ | https://www.qsoft.hu/course/raktari-keszlet-es-aruforgalmi-modul/ |
| 08 | ⏳ | https://www.qsoft.hu/course/szamlazas-modul/ |
| 09 | ⏳ | https://www.qsoft.hu/course/szerzodes-nyilvantartas-modul/ |
| 10 | ⏳ | https://www.qsoft.hu/course/hazi-penztar-modul/ |
| 11 | ⏳ | https://www.qsoft.hu/course/merleg-es-elemezes-modul/ |
| 12 | ⏳ | https://www.qsoft.hu/course/740/ |
| 13 | ⏳ | https://www.qsoft.hu/tip-iratkozelo-es-informacios-rendszer/ |
| 14 | ⏳ | https://www.qsoft.hu/online-informacios-lekerdezesek/ |
| 15 | ⏳ | https://www.qsoft.hu/vasarlas-es-rendszerbevezetes/ |
| 16 | ⏳ | https://www.qsoft.hu/referencia-lista/ |
| 17 | ⏳ | https://www.qsoft.hu/tamogatas/ |
| 18 | ⏳ | https://www.qsoft.hu/course/felso-szogaltatas/ |
| 19 | ⏳ | https://www.qsoft.hu/course/ocr/ |
| 20 | ⏳ | https://www.qsoft.hu/course/adatmentesi-es-archivaasi-szolgaltatasunk/ |
| 21 | ⏳ | https://www.qsoft.hu/course/banki-terminalal-torteno-kommunikacio/ |
| 22 | ⏳ | https://www.qsoft.hu/course/egyedi-programfejlesztesek/ |
| 23 | ⏳ | http://virusirvto.qsoft.hu/ |
| 24 | ⏳ | http://virusirvto.qsoft.hu/getprice.html |
| 25 | ⏳ | https://www.qsoft.hu/allas/ |
| 26 | ⏳ | https://www.qsoft.hu/minosegpolitikank/ |
| 27 | ⏳ | https://www.qsoft.hu/kapcsolat/ |
| 28 | ⏳ | https://www.qsoft.hu/aktualitasaink/ |
| 29 | ⏳ | https://www.qsoft.hu/majusi-rendszervaltás/ |
| 30 | ⏳ | https://www.qsoft.hu/bizonylatok-digitalizalasa/ |
| 31 | ⏳ | https://www.qsoft.hu/ai-szerepe-a-sup-rendszer-fejlesztesebenб/ |
| 32 | ⏳ | https://www.qsoft.hu/automata-szamlafeldolgozó/ |
| 33 | ⏳ | https://www.qsoft.hu/miert-valassza-rendszerunket/ |
| 34 | ⏳ | https://www.qsoft.hu/kellemes-unnepeket-kivanunk-2/ |
| 35 | ⏳ | https://www.qsoft.hu/utanvet-es-bankkartyá-elsámolás-kezelese/ |
| 36 | ⏳ | https://www.facebook.com/Qsoftkft |

## Megjegyzések
- A context.md egyes URL-jeiben elírás van — a helyes URL-eket a navigációból kell kiszedni
- Képletöltés: PowerShell `Invoke-WebRequest` (curl nem működik a sandboxban)
- Facebook (#36): várhatóan nem ad vissza tartalmat
- Minden push után: `git log --oneline -1` ellenőrzés
