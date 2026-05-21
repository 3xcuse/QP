# Működési feltételek

**URL:** https://www.qsoft.hu/mukodesi-feltetelek/

---

A SUP Vállalatirányítási Rendszer a kliens-szerver architektúrából következően alapvetően hálózati működési környezetre van tervezve, azonban működtethető egygépes környezetben is, ún. localserver üzemmódban. Lehetőség van a Microsoft Windows Terminál Szerver (RDP), vagy Citrix környezetben történő üzemeltetésre is.

## Szerver oldali hardver

A szerver teljesítményét és memória (RAM) kapacitását a feldolgozandó adatmennyiséggel, és a várható munkahelyek számával összhangban kell meghatározni. A merevlemez kapacitás a könyvelt cégek számával, ill. az éves várható könyvelési tételszámmal függ össze.

Fontos olyan gépet választani erre a célra, mely folyamatos, megbízható rendelkezésre állást biztosít. Ilyenek pl.: a Dell, HP, IBM stb. szerverek. Olyan architektúrát kell választani amely lehetővé teszi a Firebird SQL adatbázismotor telepítését. (http://www.firebirdsql.org)

Ha a szerver operációs rendszer valamelyik Windows, az ajánlotthoz képest további legalább 4 GB RAM-ot célszerű biztosítani.

- **Közepes kiépítettségű Linux szerver:** Intel® Core™ i7 vagy jobb kategóriájú processzor, 4 GB vagy több RAM, 500 GB merevlemez, szünetmentes tápegység.
- **Egy „erősebb" Linux szerver:** Intel Xeon processzor, vagy egyéb szerver architektúra, 4 GB vagy több RAM, 3×500 GB (hot-plug, vagy non hot-plug) RAID5 merevlemez, mentést biztosító eszköz, szünetmentes tápegység.
- **Átlagos Windows szerver:** Intel Xeon kategóriájú processzor, 8 GB vagy több RAM, 3×500 GB HDD (RAID), szünetmentes tápegység

## Szerver oldali szoftver

- **Linux:** az Firebird SQL adatbázisszerver üzemeltetéséhez általunk ajánlott Linux disztribúció: Debian vagy Ubuntu. File szerver modulként a Samba szükséges.

A Firebird SQL adatbázis szervert a disztribúció repozitorijából, vagy Docker.CE környezetben lehetséges telepíteni.

- **Windows Szerver termékcsalád:** Windows 2008/2008R2 Server változatoktól kezdődően, 2019 DataCenter-ig bármi megfelelő.
- **Windows Desktop termékcsalád** (nem ideális, de kis cégek esetében szóba jöhet): Windows 10 Professional.
- **Mac OS X:** A Firebird SQL szerver támogatja, de a SUP rendszerrel kapcsolatosan gyakorlati megvalósításról még nincs tudomásunk.

## Kliens oldali hardver

Intel® Core™ i3 vagy jobb kategóriájú számítógép, további alkalmazásoktól függően legalább 4 GB RAM, 500 MB szabad merevlemez kapacitás, 1024×768 képpont felbontásra beállított monitor.

## Kliens oldali szoftver

Operációs rendszer: **Windows 10, (Windows 7) Professional vagy Ultimate változata.**

A Windows 95/98/Me/Vista/2000/XP és egyéb Home vagy Embedded (IoT) változatok nem alkalmasak!

Szükséges továbbá a Firebird SQL adatbázismotor **kliensének** telepítése. Ajánlott a Windows legutolsó Service Pack telepítése.

---

## Lábléc

© Copyright Qsoft Kft. Minden jog fenntartva.  
Qsoft Kft. 1119 Budapest, Fehérvári út 85.  
Tel.: +36 (1) 365-4446
