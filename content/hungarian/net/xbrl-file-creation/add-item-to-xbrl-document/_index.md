---
title: Elem hozzáadása az XBRL-dokumentumhoz
linktitle: Elem hozzáadása az XBRL-dokumentumhoz
second_title: Aspose.Finance .NET API
description: Ismerje meg, hogyan adhat hozzá elemeket XBRL-dokumentumokhoz az Aspose.Finance for .NET használatával. Egyszerűsítse a pénzügyi jelentéseket .NET-alkalmazásaiban. #Aspose #Pénzügyek
type: docs
weight: 13
url: /hu/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Az Extensible Business Reporting Language (XBRL) a pénzügyi jelentések szabványos formátumává vált, lehetővé téve a pénzügyi adatok hatékony és pontos kommunikációját. Az Aspose.Finance for .NET robusztus funkcionalitást biztosít a .NET-alkalmazások XBRL-dokumentumainak kezeléséhez. Ebben az oktatóanyagban végigvezetjük azokat a lépéseket, amelyekkel az Aspose.Finance for .NET segítségével elemet adhatunk XBRL-dokumentumhoz.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. Telepítse az Aspose.Finance for .NET programot
 Ha még nem tette meg, töltse le és telepítse az Aspose.Finance for .NET programot a webhelyről[hivatalos honlapján](https://releases.aspose.com/finance/net/). Kövesse a telepítési utasításokat a könyvtár beállításához a .NET-környezetben.
### 2. Állítsa be fejlesztői környezetét
Győződjön meg arról, hogy működő fejlesztői környezettel rendelkezik a .NET fejlesztéshez. Szüksége lesz egy kompatibilis IDE-re, például a Visual Studiora, valamint a rendszerére telepített .NET-keretrendszerre.
## Névterek importálása
Először is importálja a szükséges névtereket .NET-alkalmazásába, hogy kihasználhassa az Aspose.Finance for .NET által biztosított funkciókat.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Most bontsuk fel a példakódot több lépésre:
## 1. lépés: Forrás- és kimeneti könyvtárak meghatározása
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Cserélje ki`"Your Source Directory"` és`"Your Output Directory"` a forrás- és kimeneti könyvtár elérési útjával.
## 2. lépés: Hozzon létre egy XBRL-dokumentumot és -példányt
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inicializáljon egy XBRL dokumentumot és példányt a munkavégzéshez.
## 3. lépés: Sémahivatkozás hozzáadása
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonómia");
```
Adjon hozzá egy sémahivatkozást az XBRL-példányhoz, adja meg a sémafájl elérési útját, és adja meg a névtér részleteit.
## 4. lépés: A kontextus és az entitás meghatározása
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Hozzon létre egy környezetet és entitást az XBRL-példányhoz, megadva a periódus és az entitás részleteit.
## 5. lépés: Adjon hozzá egységet
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Határozzon meg egy egységet az XBRL-példányhoz, megadva a mérték minősített neveket.
## 6. lépés: Tétel hozzáadása
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
Adjon hozzá egy elemet az XBRL-példányhoz, megadva annak fogalmát, kontextusát, mértékegységét, pontosságát és értékét.
## 7. lépés: Mentse el a dokumentumot
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Mentse az XBRL dokumentumot a kimeneti könyvtárba.
## Következtetés
Az elemek XBRL-dokumentumhoz való hozzáadása elengedhetetlen a pénzügyi adatok pontos megjelenítéséhez. Az Aspose.Finance for .NET leegyszerűsíti ezt a folyamatot, mivel átfogó API-t biztosít a .NET-alkalmazások XBRL-dokumentumainak kezelésére.
## GYIK
### Használhatom az Aspose.Finance for .NET-et bármely .NET-alkalmazással?
Igen, az Aspose.Finance for .NET kompatibilis bármely .NET-alkalmazással, beleértve az ASP.NET-, a WinForms- és a Console-alkalmazásokat.
### Ingyenesen használható az Aspose.Finance for .NET?
 Az Aspose.Finance for .NET egy kereskedelmi könyvtár. Letölthet egy ingyenes próbaverziót a funkcióinak értékeléséhez, és licenceket vásárolhat a webhelyen[itt](https://purchase.aspose.com/buy).
### Az Aspose.Finance for .NET támogatja az XBRL-en kívül más pénzügyi jelentési formátumokat is?
Az Aspose.Finance for .NET elsősorban az XBRL-hez kapcsolódó funkciókra összpontosít. Az Aspose azonban más könyvtárakat is kínál a különböző pénzügyi formátumokkal való munkavégzéshez.
### Hogyan kaphatok támogatást az Aspose.Finance for .NET-hez?
 Az Aspose.Finance for .NET-hez a következőn keresztül kaphat támogatást[hivatalos fórum](https://forum.aspose.com/c/finance/43)ahol kérdéseket tehet fel, és kapcsolatba léphet más felhasználókkal és támogató személyzettel.
### Kaphatok ideiglenes licencet az Aspose.Finance for .NET számára?
 Igen, tesztelési célokra rendelkezésre állnak az Aspose.Finance for .NET ideiglenes licencei. Beszerezhetsz egyet[itt](https://purchase.aspose.com/temporary-license/).