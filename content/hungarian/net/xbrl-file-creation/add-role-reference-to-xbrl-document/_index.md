---
title: Szerepköri hivatkozás hozzáadása az XBRL-dokumentumhoz
linktitle: Szerepköri hivatkozás hozzáadása az XBRL-dokumentumhoz
second_title: Aspose.Finance .NET API
description: Ismerje meg, hogyan adhat szerephivatkozásokat XBRL-dokumentumokhoz az Aspose.Finance for .NET használatával. Ezzel az oktatóanyaggal egyszerűsítheti a pénzügyi jelentéskészítést .NET-alkalmazásaiban.
type: docs
weight: 14
url: /hu/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
Az XBRL (eXtensible Business Reporting Language) az üzleti információk cseréjének szabványává vált, különösen a pénzügyi jelentésekben. Az Aspose.Finance for .NET leegyszerűsíti az XBRL dokumentumokkal való munkát a .NET alkalmazásokban. Ez az oktatóanyag végigvezeti Önt a szerephivatkozás XBRL-dokumentumhoz való hozzáadásának folyamatán az Aspose.Finance for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. Telepítse az Aspose.Finance for .NET programot
Győződjön meg arról, hogy az Aspose.Finance for .NET telepítve van a fejlesztői környezetében. Ha még nem tette meg, töltse le a[kiadja](https://releases.aspose.com/finance/net/) és kövesse a telepítési utasításokat.
### 2. Állítsa be fejlesztői környezetét
Győződjön meg arról, hogy rendelkezik működő fejlesztői környezettel a .NET fejlesztéshez. Ide tartozik egy kompatibilis IDE, például a Visual Studio és a rendszerére telepített .NET-keretrendszer.
## Névterek importálása
Kezdje azzal, hogy importálja a szükséges névtereket a .NET-alkalmazásba, hogy hozzáférjen az Aspose.Finance for .NET szolgáltatásaihoz.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## 4. lépés: Szereptípus lekérése és szerephivatkozás hozzáadása
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Töltse le a szerepkör típusát az URI-jával, és adjon hozzá egy szerephivatkozást az XBRL-példányhoz.
## 5. lépés: Mentse el a dokumentumot
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Mentse az XBRL dokumentumot a kimeneti könyvtárba.
## Következtetés
A szerephivatkozások hozzáadása az XBRL-dokumentumokhoz elengedhetetlen a dokumentumon belüli különböző elemek szerepének meghatározásához. Az Aspose.Finance for .NET egyszerű módszert kínál ennek a feladatnak a végrehajtására, lehetővé téve a fejlesztők számára, hogy hatékonyan dolgozzanak XBRL-dokumentumokkal .NET-alkalmazásaikban.
## GYIK
### Használhatom az Aspose.Finance for .NET-et bármely .NET-alkalmazással?
Igen, az Aspose.Finance for .NET kompatibilis bármely .NET-alkalmazással, beleértve az ASP.NET-, a WinForms- és a Console-alkalmazásokat.
### Ingyenesen használható az Aspose.Finance for .NET?
 Az Aspose.Finance for .NET egy kereskedelmi könyvtár. Letölthet egy ingyenes próbaverziót a funkcióinak értékeléséhez, és licenceket vásárolhat a webhelyen[itt](https://purchase.aspose.com/buy).
### Az Aspose.Finance for .NET támogatja az XBRL-en kívül más pénzügyi jelentési formátumokat is?
Az Aspose.Finance for .NET elsősorban az XBRL-hez kapcsolódó funkciókra összpontosít. Az Aspose azonban más könyvtárakat is kínál a különböző pénzügyi formátumokkal való munkavégzéshez.
### Hogyan kaphatok támogatást az Aspose.Finance for .NET-hez?
 Az Aspose.Finance for .NET-hez a következőn keresztül kaphat támogatást[fórum](https://forum.aspose.com/c/finance/43)ahol kérdéseket tehet fel, és kapcsolatba léphet más felhasználókkal és támogató személyzettel.
### Kaphatok ideiglenes licencet az Aspose.Finance for .NET számára?
 Igen, tesztelési célokra rendelkezésre állnak az Aspose.Finance for .NET ideiglenes licencei. Beszerezhetsz egyet[itt](https://purchase.aspose.com/temporary-license/).