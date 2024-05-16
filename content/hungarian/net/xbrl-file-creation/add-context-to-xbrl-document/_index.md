---
title: Kontextus hozzáadása az XBRL-dokumentumhoz
linktitle: Kontextus hozzáadása az XBRL-dokumentumhoz
second_title: Aspose.Finance .NET API
description: Ismerje meg, hogyan adhat kontextust az XBRL-dokumentumokhoz a .NET-ben az Aspose.Finance segítségével az egyszerűsített pénzügyi jelentéskészítés érdekében. #Aspose #Pénzügy #XBRL
type: docs
weight: 11
url: /hu/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Bevezetés
A pénzügyi jelentések területén az XBRL (eXtensible Business Reporting Language) kulcsfontosságú szerepet játszik az üzleti információk cseréjének szabványosításában. Az XBRL-dokumentumok kontextusának hozzáadása kulcsfontosságú a bennük található adatok integritásának és relevanciájának biztosításához. Az Aspose.Finance for .NET segítségével ez a folyamat leegyszerűsödik és hatékony, lehetővé téve a fejlesztők számára, hogy zökkenőmentesen építsék be a kontextust XBRL-dokumentumaikba.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Aspose.Finance for .NET Library: Töltse le és telepítse az Aspose.Finance for .NET könyvtárat a[kiadja](https://releases.aspose.com/finance/net/).
2. .NET fejlesztői környezet: Győződjön meg arról, hogy működő .NET fejlesztői környezet van beállítva a gépen.
3. A C# alapvető ismerete: A C# programozási nyelv ismerete hasznos lesz a példák követésében.
## Névterek importálása
A C# projektben importálja a szükséges névtereket az Aspose.Finance for .NET által biztosított funkciók eléréséhez:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 1. lépés: Állítsa be a kimeneti könyvtárat
Mielőtt kontextust adna az XBRL-dokumentumhoz, adja meg a kimeneti könyvtárat, ahová a módosított dokumentumot menti:
```csharp
string outputDir = "Your Output Directory";
```
 Cserélje ki`"Your Output Directory"` a kívánt elérési úttal a rendszeren.
## 2. lépés: Hozzon létre XBRL-dokumentumot
 Példányosítása an`XbrlDocument` objektum az XBRL dokumentumokkal való munkavégzéshez:
```csharp
XbrlDocument document = new XbrlDocument();
```
Ez az objektum a kezelni kívánt XBRL dokumentumot képviseli.
## 3. lépés: Adja hozzá az XBRL-példányt
Adjon hozzá egy XBRL-példányt a dokumentumhoz. Minden példány egy adott jelentési időszak adatait tartalmazza:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ez a lépés inicializál egy XBRL-példányt a dokumentumban.
## 4. lépés: Határozza meg a kontextus periódusát és az entitást
Hozzon létre egy környezeti időszakot és entitást az XBRL-példányhoz:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Adja meg az időszakot és az entitás részleteit a jelentési követelményeinek megfelelően.
## 5. lépés: Kontextus létrehozása
Kontextus létrehozása az előző lépésben meghatározott időszak és entitás felhasználásával:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Ez a kontextus magába foglalja az időbeli és az entitásokkal kapcsolatos információkat.
## 6. lépés: Kontextus hozzáadása az XBRL-példányhoz
Társítsa az előző lépésben létrehozott környezetet az XBRL-példányhoz:
```csharp
xbrlInstance.Contexts.Add(context);
```
Ez a lépés összekapcsolja a kontextust az XBRL-példánnyal, releváns környezeti információkat biztosítva az adatokhoz.
## 7. lépés: Mentse el a dokumentumot
Mentse el a módosított XBRL dokumentumot a megadott kimeneti könyvtárba:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Ezzel befejeződik a folyamat, mentve az XBRL-dokumentumot a hozzáadott kontextussal.
## Következtetés
Az alábbi lépések követésével hatékonyan adhat kontextust az XBRL-dokumentumokhoz az Aspose.Finance for .NET használatával. Ez javítja a pénzügyi adatok egyértelműségét és használhatóságát, megkönnyítve a pontos elemzést és jelentéskészítést.
## GYIK
### Az Aspose.Finance for .NET kezelheti a nagy XBRL dokumentumokat?
Az Aspose.Finance for .NET változó méretű XBRL-dokumentumok kezelésére lett optimalizálva, beleértve a nagy adatkészleteket is.
### Elérhető az Aspose.Finance próbaverziója .NET-hez?
Igen, letölthet egy ingyenes próbaverziót az Aspose hivatalos webhelyéről.
### Az Aspose.Finance for .NET támogat más pénzügyi jelentési szabványokat az XBRL-n kívül?
Az Aspose.Finance elsősorban az XBRL-hez kapcsolódó funkciókra összpontosít, de más pénzügyi formátumokhoz is támogatást nyújt.
### Testreszabhatom a kontextusinformációkat sajátos igényeim szerint?
Természetesen az Aspose.Finance for .NET rugalmasságot kínál a környezeti információk igényeinek megfelelő testreszabásához.
### Hol találhatok további támogatást vagy forrásokat az Aspose.Finance for .NET-hez?
Látogassa meg az Aspose.Finance fórumot a közösség segítségéért, vagy tekintse meg a dokumentációt átfogó útmutatásért.