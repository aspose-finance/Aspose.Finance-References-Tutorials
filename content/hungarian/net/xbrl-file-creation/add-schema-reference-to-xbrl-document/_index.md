---
title: Sémahivatkozás hozzáadása az XBRL-dokumentumhoz
linktitle: Sémahivatkozás hozzáadása az XBRL-dokumentumhoz
second_title: Aspose.Finance .NET API
description: Ismerje meg, hogyan adhat hozzá sémahivatkozásokat XBRL-dokumentumokhoz az Aspose.Finance for .NET segítségével. Egyszerűsítse pénzügyi adatainak feldolgozását még ma!
type: docs
weight: 15
url: /hu/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Bemutatkozik az Aspose.Finance for .NET
Az Aspose.Finance for .NET egy hatékony könyvtár, amely átfogó funkciókat kínál a .NET-alkalmazásokon belüli pénzügyi dokumentumok és adatok feldolgozásához és kezeléséhez. Függetlenül attól, hogy számviteli szoftvert, pénzügyi elemző eszközöket vagy bármilyen más pénzügyi alkalmazást épít, az Aspose.Finance for .NET a funkciók széles skáláját kínálja a fejlesztési folyamat egyszerűsítésére.
## Előfeltételek
Mielőtt belevágna az Aspose.Finance for .NET használatába, győződjön meg arról, hogy beállította a következő előfeltételeket:
### 1. Telepítse a Visual Studio programot
Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren. Letöltheti és telepítheti a Microsoft hivatalos webhelyéről.
### 2. Szerezzen be egy Aspose.Finance licencet
Az Aspose.Finance for .NET teljes képességeinek kihasználásához érvényes licencet kell beszereznie. Engedélyt vásárolhat innen[itt](https://purchase.aspose.com/buy) vagy válasszon ideiglenes licencet tesztelési célokra.
### 3. Töltse le és tekintse meg az Aspose.Finance for .NET programot
 Töltse le az Aspose.Finance for .NET könyvtárat a[kiadások oldala](https://releases.aspose.com/finance/net/) és hivatkozzon rá a .NET projektben.
### 4. Hozzáférés a dokumentációhoz és támogatáshoz
 Utal[API dokumentáció](https://reference.aspose.com/finance/net/) Az Aspose.Finance for .NET használatával kapcsolatos részletes információkért. Ezenkívül segítséget kérhet az Aspose.Finance közösségtől a webhelyen[támogatói fórum](https://forum.aspose.com/c/finance/43).
## Névterek importálása
Kezdjük a szükséges névterek importálásával a .NET projektbe:
## 1. lépés: Adja hozzá az Aspose.Finance névteret
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Ez a névtér osztályokat és metódusokat tartalmaz az XBRL dokumentumokkal és adatokkal való munkavégzéshez.
Most bontsuk fel a megadott példát több lépésre, hogy megértsük, hogyan lehet sémahivatkozást hozzáadni egy XBRL-dokumentumhoz az Aspose.Finance for .NET használatával.
## 1. lépés: Forrás- és kimeneti könyvtárak meghatározása
```csharp
// Forrás könyvtár
string sourceDir = "Your Source Directory";
// Kimeneti könyvtár
string outputDir = "Your Output Directory";
```
 Cserélje ki`"Your Source Directory"` és`"Your Output Directory"` forrás- és kimeneti könyvtárak tényleges elérési útjaival.
## 2. lépés: Hozzon létre egy XBRL-dokumentumot
```csharp
XbrlDocument document = new XbrlDocument();
```
Ezzel létrehozza az XBRL dokumentum új példányát.
## 3. lépés: Nyissa meg az XBRL-példányokat
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ez lekéri az XBRL-példányok gyűjteményét a dokumentumból, és új példányt ad hozzá.
## 4. lépés: Sémahivatkozás hozzáadása
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonómia");
```
 Ezzel hozzáad egy sémahivatkozást az XBRL-példányhoz. Cserélje ki`"schema.xsd"` a sémafájl tényleges nevével,`"example"` megfelelő előtaggal, és`"http://example.com/xbrl/taxonomy"` a cél névtér URI-jával.
## 5. lépés: Mentse el a dokumentumot
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Ez elmenti a módosított XBRL dokumentumot a megadott kimeneti könyvtárba.
## Következtetés
Összefoglalva, az Aspose.Finance for .NET robusztus megoldást kínál a pénzügyi dokumentumok és adatok kezelésére .NET-alkalmazásokban. Az oktatóanyagban ismertetett lépések követésével könnyedén integrálhatja az Aspose.Finance-t projektjeibe, és hatékonyan kezelheti az XBRL dokumentumokat.
## GYIK
 (Gyakran Ismételt Kérdések)
### 1. Használhatom az Aspose.Finance-t .NET-hez licenc nélkül?
Nem, érvényes licencre van szüksége az Aspose.Finance for .NET teljes szolgáltatásának használatához. Tesztelési célra azonban ideiglenes licencet szerezhet.
### 2. Alkalmas-e az Aspose.Finance számviteli szoftver építésére?
Igen, az Aspose.Finance átfogó funkcionalitást biztosít a pénzügyi adatok feldolgozásához, így ideális számviteli szoftverek és kapcsolódó alkalmazások létrehozásához.
### 3. Hol találok támogatást az Aspose.Finance számára?
Kérhet segítséget az Aspose.Finance közösségtől a hivatalos támogatási fórumon.
### 4. Testreszabhatom a séma hivatkozási előtagját?
Igen, kiválaszthat megfelelő előtagot, amikor sémahivatkozást ad hozzá egy XBRL-dokumentumhoz az Aspose.Finance for .NET használatával.
### 5. Az Aspose.Finance az XBRL-en kívül más pénzügyi formátumokat is támogat?
Igen, az Aspose.Finance különféle pénzügyi formátumokat és szabványokat támogat, lehetővé téve a különféle pénzügyi alkalmazásokba való zökkenőmentes integrációt.