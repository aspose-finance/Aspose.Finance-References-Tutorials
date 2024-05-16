---
title: Adja hozzá az egységet az XBRL dokumentumhoz
linktitle: Adja hozzá az egységet az XBRL dokumentumhoz
second_title: Aspose.Finance .NET API
description: Az Aspose.Finance for .NET segítségével megtudhatja, hogyan vehet fel könnyedén egységeket XBRL-dokumentumokhoz. Növelje pénzügyi adatfeldolgozási képességeit még ma!
type: docs
weight: 16
url: /hu/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Üdvözöljük az Aspose.Finance for .NET világában – ez az átjáró a .NET-alkalmazásokon belüli hatékony pénzügyi dokumentumok kezeléséhez. Függetlenül attól, hogy számviteli szoftvert, pénzügyi elemző eszközöket vagy bármilyen más pénzügyi alkalmazást épít, az Aspose.Finance for .NET a fejlesztési folyamatok egyszerűsítésére szolgáló funkciók átfogó készletével látja el.
## Előfeltételek
Mielőtt belevágnánk az Aspose.Finance erejének .NET-hez való hasznosításába, győződjön meg arról, hogy megvannak a szükséges előfeltételek:
### 1. A Visual Studio telepítése
Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren. Ha nem, letöltheti és telepítheti a Microsoft hivatalos webhelyéről.
### 2. Szerezzen engedélyt
 Az Aspose.Finance .NET-hez való teljes potenciáljának kiaknázásához érvényes licencre van szüksége. Engedélyt vásárolhat innen[itt](https://purchase.aspose.com/buy) vagy válasszon ideiglenes licencet tesztelési célokra.
### 3. Töltse le és tekintse meg az Aspose.Finance for .NET programot
 Töltse le az Aspose.Finance for .NET könyvtárat a[kiadások oldala](https://releases.aspose.com/finance/net/) és hivatkozzon rá a .NET projektben.
### 4. Hozzáférés a dokumentációhoz és támogatáshoz
 Utal[dokumentáció](https://reference.aspose.com/finance/net/)Az Aspose.Finance for .NET használatával kapcsolatos részletes információkért. Ezenkívül segítséget kérhet az Aspose.Finance közösségtől a webhelyen[támogatói fórum](https://forum.aspose.com/c/finance/43).
## Névterek importálása
Most importáljuk a szükséges névtereket a .NET-projektbe:
## 1. lépés: Adja hozzá az Aspose.Finance névteret
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Ez a névtér osztályokat és metódusokat tartalmaz, amelyek elengedhetetlenek az XBRL dokumentumok és adatok kezeléséhez.
Bontsuk le a példát több lépésre, hogy megértsük, hogyan adhatunk egy egységet XBRL-dokumentumhoz az Aspose.Finance for .NET használatával.
## 1. lépés: Határozza meg a kimeneti könyvtárat
```csharp
// Kimeneti könyvtár
string outputDir = "Your Output Directory";
```
 Cserélje ki`"Your Output Directory"` a kívánt kimeneti könyvtár tényleges elérési útjával.
## 2. lépés: Hozzon létre egy XBRL-dokumentumot
```csharp
XbrlDocument document = new XbrlDocument();
```
Ezzel inicializálja az XBRL dokumentum új példányát.
## 3. lépés: Nyissa meg az XBRL-példányokat
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ez lekéri az XBRL-példányok gyűjteményét a dokumentumból, és új példányt ad hozzá.
## 4. lépés: Adjon hozzá egységet
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Ez létrehoz egy új mértékegységet (jelen esetben USD), és hozzáadja az XBRL-példányhoz. Szükség szerint módosíthatja a pénznemkódot és a névtér URI-t.
## 5. lépés: Mentse el a dokumentumot
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Ez elmenti a módosított XBRL dokumentumot a megadott kimeneti könyvtárba.
## Következtetés
Összefoglalva, az Aspose.Finance for .NET lehetővé teszi a fejlesztők számára, hogy könnyedén kezeljék a pénzügyi dokumentumokat és adatokat .NET-alkalmazásaikon belül. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja az Aspose.Finance for .NET-et projektjeibe, és javíthatja pénzügyi feldolgozási képességeit.
## GYIK
### 1. Használhatom az Aspose.Finance-t .NET-hez licenc nélkül?
Nem, érvényes licenc szükséges az Aspose.Finance for .NET összes funkciójának feloldásához. Tesztelési célokra azonban rendelkezésre állnak ideiglenes licencek.
### 2. Az Aspose.Finance for .NET alkalmas számviteli szoftverek készítésére?
Igen, az Aspose.Finance for .NET robusztus funkciókat kínál a számviteli szoftverek és a kapcsolódó pénzügyi alkalmazások létrehozásához.
### 3. Hol találok támogatást az Aspose.Finance for .NET-hez?
Kérhet segítséget az Aspose.Finance közösségtől a támogatási fórumon.
### 4. Testreszabhatom a mértékegységet egy XBRL dokumentumban?
Igen, az Aspose.Finance for .NET segítségével egyéni mértékegységeket hozhat létre és adhat hozzá XBRL-dokumentumokhoz.
### 5. Az Aspose.Finance for .NET támogat több pénznemet?
Igen, az Aspose.Finance for .NET több pénznemet is támogat, ami sokoldalú pénzügyi adatfeldolgozást tesz lehetővé.