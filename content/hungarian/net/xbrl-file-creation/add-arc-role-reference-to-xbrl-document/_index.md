---
title: Adja hozzá az ARC szerephivatkozást az XBRL-dokumentumhoz
linktitle: Adja hozzá az ARC szerephivatkozást az XBRL-dokumentumhoz
second_title: Aspose.Finance .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az XBRL-dokumentumokat az Aspose.Finance for .NET használatával. Adjon hozzá ARC szerepkör referenciákat a lépésről lépésre történő útmutatásnak köszönhetően.
type: docs
weight: 10
url: /hu/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Bevezetés
pénzügyi adatkezelés és jelentéskészítés világában az eXtensible Business Reporting Language (XBRL) döntő szerepet játszik. Szabványosítja a pénzügyi információk közlésének és cseréjének módját, biztosítva a következetességet, pontosságot és hatékonyságot. Az XBRL-dokumentumok manipulálása azonban, különösen konkrét szerepkörök és hivatkozások beépítésekor, megköveteli a mögöttes mechanizmusok árnyalt megértését. Ez az oktatóanyag egy ilyen feladatra összpontosít: ARC szerephivatkozás hozzáadása egy XBRL dokumentumhoz az Aspose.Finance for .NET segítségével.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### Környezet beállítása
1.  Az Aspose.Finance for .NET telepítése: Töltse le és telepítse az Aspose.Finance for .NET könyvtárat a[kiadja](https://releases.aspose.com/finance/net/).
   
2. Fejlesztési környezet: Állítsa be fejlesztői környezetét a Visual Studio vagy bármely más preferált IDE segítségével.
## Névterek importálása
Ügyeljen arra, hogy importálja a szükséges névtereket a C# kódban:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 1. lépés: Forrás- és kimeneti könyvtárak meghatározása
folytatás előtt adja meg a forrás- és kimeneti könyvtárat, ahová az XBRL-fájlokat el kell helyezni és menteni.
```csharp
// Forrás könyvtár
string sourceDir = "Your Source Directory";
// Kimeneti könyvtár
string outputDir = "Your Output Directory";
```
## 2. lépés: Hozzon létre egy XBRL-dokumentumot
 Példányosítása an`XbrlDocument` objektum az XBRL adatokkal való munkavégzéshez.
```csharp
XbrlDocument document = new XbrlDocument();
```
## 3. lépés: Hozzáférés az XbrlInstance Collectionhez
Hozzáférés az XBRL-példányok gyűjteményéhez a dokumentumon belül.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## 4. lépés: Adja hozzá az XbrlInstance-t
Adjon hozzá egy új XBRL-példányt a gyűjteményhez.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 5. lépés: Sémahivatkozás hozzáadása
Adjon meg egy séma hivatkozást az XBRL-példányban, megadva a forráskönyvtárat, a névtér előtagot és az URI-t.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonómia");
```
## 6. lépés: Az ArcroleType lekérése
 Szerezze vissza a`ArcroleType` egy adott URI alapján.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## 7. lépés: Adja hozzá az ArcroleReference-t
 Ha a`ArcroleType` található, hozzon létre egy`ArcroleReference` és adja hozzá az XBRL-példány arcrole hivatkozásaihoz.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## 8. lépés: Mentse el a dokumentumot
Mentse el a módosított XBRL dokumentumot a megadott kimeneti könyvtárba.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan adhatunk ARC-szerepreferenciát egy XBRL-dokumentumhoz az Aspose.Finance for .NET használatával. Ha követi ezeket a lépésenkénti utasításokat, és kihasználja az Aspose.Finance képességeit, hatékonyan kezelheti és kezelheti az XBRL-adatokat, hogy megfeleljen sajátos követelményeinek.
## GYIK
### Mi az XBRL?
Az XBRL az eXtensible Business Reporting Language rövidítése, amely az üzleti és pénzügyi adatok elektronikus kommunikációjának szabványosított nyelve.
### Miért fontos az XBRL?
Az XBRL biztosítja a következetességet, pontosságot és hatékonyságot a pénzügyi információk cseréje és elemzése során, ami a szabályozó hatóságok, elemzők és vállalkozások számára előnyös.
### Az Aspose.Finance képes kezelni az összetett XBRL-feladatokat?
Igen, az Aspose.Finance robusztus funkcionalitást kínál az XBRL-dokumentumokkal való munkavégzéshez, beleértve az olyan összetett feladatok kezelését, mint a szerephivatkozások és a taxonómia-kezelés.
### Az Aspose.Finance kompatibilis más .NET könyvtárakkal?
Igen, az Aspose.Finance zökkenőmentesen integrálódik más .NET-könyvtárakba, és széleskörű támogatást nyújt a pénzügyi adatok kezeléséhez és jelentésekhez.
### Hol találok további támogatást az Aspose.Finance számára?
 További támogatásért látogassa meg a[Aspose.Finance támogatási oldal](https://forum.aspose.com/c/finance/43).