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
| 04 | ✅ KÉSZ | https://www.qsoft.hu/course/szamviteli-modul/ |
| 05 | ✅ KÉSZ | https://www.qsoft.hu/course/penzugyi-modul/ |
| 06 | ✅ KÉSZ | https://www.qsoft.hu/course/targyi-eszkoz-modul/ |
| 07 | ✅ KÉSZ | https://www.qsoft.hu/course/raktari-keszlet-es-aruforgalmi-modul/ |
| 08 | ✅ KÉSZ | https://www.qsoft.hu/course/szamlazas-modul/ |
| 09 | ✅ KÉSZ | https://www.qsoft.hu/course/szerzodes-nyilvantartas-modul/ |
| 10 | ✅ KÉSZ | https://www.qsoft.hu/course/hazi-penztar-modul/ |
| 11 | ✅ KÉSZ | https://www.qsoft.hu/course/merleg-es-elemzes-modul/ |
| 12 | ✅ KÉSZ | https://www.qsoft.hu/course/740/ |
| 13 | ✅ KÉSZ | https://www.qsoft.hu/tip-iratkezelo-es-informacios-rendszer/ |
| 14 | ✅ KÉSZ | https://www.qsoft.hu/online-informacios-lekerdezesek/ |
| 15 | ✅ KÉSZ | https://www.qsoft.hu/vasarlas-es-rendszerbevezetes/ |
| 16 | ✅ KÉSZ | https://www.qsoft.hu/referencia-lista/ |
| 17 | ✅ KÉSZ | https://www.qsoft.hu/tamogatas/ |
| 18 | ✅ KÉSZ | https://www.qsoft.hu/course/felho-szogaltatas/ |
| 19 | ✅ KÉSZ | https://www.qsoft.hu/course/ocr/ |
| 20 | ✅ KÉSZ | https://www.qsoft.hu/course/adatmentesi-es-archivalasi-szolgaltatasunk/ |
| 21 | ✅ KÉSZ | https://www.qsoft.hu/course/banki-terminallal-torteno-kommunikacio/ |
| 22 | ✅ KÉSZ | https://www.qsoft.hu/course/egyedi-programfejlesztesek/ |
| 23 | ✅ KÉSZ | http://virusirvto.qsoft.hu/ — NEM ELÉRHETŐ |
| 24 | ✅ KÉSZ | http://virusirvto.qsoft.hu/getprice.html — NEM ELÉRHETŐ |
| 25 | ✅ KÉSZ | https://www.qsoft.hu/allas/ |
| 26 | ✅ KÉSZ | https://www.qsoft.hu/minosegpolitikank/ |
| 27 | ✅ KÉSZ | https://www.qsoft.hu/kapcsolat/ |
| 28 | ✅ KÉSZ | https://www.qsoft.hu/aktualitasaink/ — 404 |
| 29 | ✅ KÉSZ | https://www.qsoft.hu/majusi-rendszervaltas/ |
| 30 | ✅ KÉSZ | https://www.qsoft.hu/bizonylatok-digitalizalasa/ |
| 31 | ✅ KÉSZ | https://www.qsoft.hu/ai-szerepe-a-sup-rendszer-fejleszteseben/ |
| 32 | ✅ KÉSZ | https://www.qsoft.hu/automata-szamlafeldolgozo/ |
| 33 | ✅ KÉSZ | https://www.qsoft.hu/miert-valassza-rendszerunket/ |
| 34 | ✅ KÉSZ | https://www.qsoft.hu/kellemes-unnepeket-kivanunk-2/ |
| 35 | ✅ KÉSZ | https://www.qsoft.hu/utanvet-es-bankkartya-elszamolas-kezelese/ |
| 36 | ✅ KÉSZ | https://www.facebook.com/Qsoftkft — bejelentkezés szükséges |

## ✅ MINDEN OLDAL FELDOLGOZVA (36/36)

## Megjegyzések
- A context.md egyes URL-jeiben elírás van — a helyes URL-eket a navigációból kell kiszedni
- Képletöltés: PowerShell `Invoke-WebRequest` (curl nem működik a sandboxban)
- Facebook (#36): bejelentkezést igényel, tartalom nem menthető
- virusirvto.qsoft.hu (#23, #24): ECONNREFUSED, szerver nem válaszol
- Aktualitásaink (#28): 404 Not Found
