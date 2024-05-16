---
title: Lábjegyzet hivatkozás hozzáadása az XBRL-dokumentumhoz
linktitle: Lábjegyzet hivatkozás hozzáadása az XBRL-dokumentumhoz
second_title: Aspose.Finance .NET API
description: Ismerje meg, hogyan adhat hozzá lábjegyzet-hivatkozásokat XBRL-dokumentumokhoz az Aspose.Finance for .NET segítségével. Könnyedén javíthatja a pénzügyi jelentéseket további kontextussal.
type: docs
weight: 12
url: /hu/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Lábjegyzet-hivatkozás hozzáadása egy XBRL-dokumentumhoz kulcsfontosságú ahhoz, hogy további kontextust vagy magyarázatokat adjon az adott adatpontokhoz. Ebben az oktatóanyagban lépésről lépésre végigjárjuk a folyamatot az Aspose.Finance for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1.  Aspose.Finance for .NET: Győződjön meg arról, hogy az Aspose.Finance for .NET telepítette a rendszerére. Letöltheti innen[itt](https://releases.aspose.com/finance/net/).
  
2. Fejlesztői környezet: .NET-keretrendszerrel vagy .NET Core-al rendelkező fejlesztői környezetet kell beállítani.
## Névterek importálása:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 1. lépés: Állítsa be a forrás- és kimeneti könyvtárakat
Először adja meg a forrás- és kimeneti fájlok könyvtárait:
```csharp
// Forrás könyvtár
string sourceDir = "Your Source Directory";
// Kimeneti könyvtár
string outputDir = "Your Output Directory";
```
## 2. lépés: Hozzon létre egy XBRL-dokumentumot és -példányt
XBRL-dokumentum és példány inicializálása:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 3. lépés: Sémahivatkozások hozzáadása
Adjon hozzá sémahivatkozásokat az XBRL-példányhoz:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonómia");
SchemaRef schema = schemaRefs[0];
```
## 4. lépés: Határozza meg a kontextust
Határozza meg az XBRL-példány kontextusát:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## 5. lépés: Lábjegyzet hivatkozás hozzáadása
Hozzon létre és adjon hozzá egy lábjegyzet hivatkozást az XBRL-példányhoz:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## 6. lépés: Mentse el a dokumentumot
Mentse el a módosított XBRL dokumentumot:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Következtetés
A lábjegyzet hivatkozásának hozzáadása egy XBRL-dokumentumhoz egyszerű folyamat az Aspose.Finance for .NET segítségével. Az ebben az oktatóanyagban felvázolt lépések követésével zökkenőmentesen építhet be további kontextust vagy magyarázatokat a pénzügyi jelentéseibe.
## GYIK
### Hozzáadhatok több lábjegyzet hivatkozást egyetlen XBRL-dokumentumhoz?
Igen, több lábjegyzet-hivatkozást is hozzáadhat az oktatóanyagban ismertetett lépések megismétlésével minden további hivatkozáshoz.
### Az Aspose.Finance for .NET kompatibilis a .NET-keretrendszerrel és a .NET Core-el is?
Igen, az Aspose.Finance for .NET támogatja a .NET Framework és a .NET Core környezeteket is.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Finance for .NET számára?
 Ideiglenes jogosítványt szerezhet be[itt](https://purchase.aspose.com/temporary-license/).
### Az Aspose.Finance for .NET támogatja az XBRL-ellenőrzést?
Igen, az Aspose.Finance for .NET átfogó támogatást nyújt az XBRL-érvényesítéshez, hogy biztosítsa az iparági szabványoknak való megfelelést.
### Hol találhatok további forrásokat és támogatást az Aspose.Finance for .NET-hez?
 Meglátogathatja a[Aspose.Finance for .NET fórum](https://forum.aspose.com/c/finance/43) támogatásért és a dokumentáció eléréséhez[itt](https://reference.aspose.com/finance/net/).