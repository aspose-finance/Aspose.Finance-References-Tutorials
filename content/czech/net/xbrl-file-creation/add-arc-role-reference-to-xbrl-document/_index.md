---
title: Přidejte odkaz na roli ARC do dokumentu XBRL
linktitle: Přidejte odkaz na roli ARC do dokumentu XBRL
second_title: Aspose.Finance .NET API
description: Naučte se efektivně manipulovat s dokumenty XBRL pomocí Aspose.Finance for .NET. Přidejte reference rolí ARC bez námahy pomocí podrobného vedení.
type: docs
weight: 10
url: /cs/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Úvod
Ve světě správy finančních dat a reportingu hraje klíčovou roli eXtensible Business Reporting Language (XBRL). Standardizuje způsob sdělování a výměny finančních informací a zajišťuje konzistenci, přesnost a efektivitu. Manipulace s dokumenty XBRL, zejména při začleňování konkrétních rolí a referencí, však vyžaduje podrobné pochopení základních mechanismů. Tento výukový program se zaměřuje na jeden takový úkol: přidání ARC Role Reference do dokumentu XBRL pomocí Aspose.Finance for .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
### Nastavení prostředí
1.  Instalace Aspose.Finance for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Finance for .NET z[vydání](https://releases.aspose.com/finance/net/).
   
2. Vývojové prostředí: Nastavte své vývojové prostředí pomocí sady Visual Studio nebo jiného preferovaného IDE.
## Import jmenných prostorů
Ujistěte se, že jste do kódu C# importovali potřebné jmenné prostory:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Krok 1: Definujte zdrojové a výstupní adresáře
Než budete pokračovat, zadejte zdrojový a výstupní adresář, kde budou umístěny a uloženy vaše soubory XBRL.
```csharp
// Zdrojový adresář
string sourceDir = "Your Source Directory";
// Výstupní adresář
string outputDir = "Your Output Directory";
```
## Krok 2: Vytvořte dokument XBRL
 Instantovat an`XbrlDocument` objekt pro práci s daty XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Krok 3: Přístup ke kolekci XbrlInstance
Přístup ke kolekci instancí XBRL v dokumentu.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Krok 4: Přidejte XbrlInstance
Přidejte do kolekce novou instanci XBRL.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Krok 5: Přidejte odkaz na schéma
Zahrňte do instance XBRL odkaz na schéma s uvedením zdrojového adresáře, předpony oboru názvů a URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Krok 6: Načtěte ArcroleType
 Získat`ArcroleType` na základě konkrétního URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Krok 7: Přidejte ArcroleReference
 Pokud`ArcroleType` je nalezen, vytvořte`ArcroleReference` a přidejte jej do referencí arcrole instance XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Krok 8: Uložte dokument
Uložte upravený dokument XBRL do zadaného výstupního adresáře.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Závěr
V tomto tutoriálu jsme prozkoumali, jak přidat ARC Role Reference do dokumentu XBRL pomocí Aspose.Finance for .NET. Dodržováním těchto podrobných pokynů a využitím možností Aspose.Finance můžete efektivně spravovat a manipulovat s daty XBRL tak, aby splňovaly vaše specifické požadavky.
## Nejčastější dotazy
### Co je XBRL?
XBRL je zkratka pro eXtensible Business Reporting Language, což je standardizovaný jazyk pro elektronickou komunikaci obchodních a finančních dat.
### Proč je XBRL důležité?
XBRL zajišťuje konzistenci, přesnost a efektivitu při výměně a analýze finančních informací, z čehož těží regulační orgány, analytici a podniky.
### Dokáže Aspose.Finance zvládnout složité úkoly XBRL?
Ano, Aspose.Finance nabízí robustní funkce pro práci s dokumenty XBRL, včetně zpracování složitých úkolů, jako jsou odkazy na role a správa taxonomie.
### Je Aspose.Finance kompatibilní s jinými knihovnami .NET?
Ano, Aspose.Finance se hladce integruje s ostatními knihovnami .NET a poskytuje rozsáhlou podporu pro manipulaci s finančními daty a vytváření sestav.
### Kde najdu další podporu pro Aspose.Finance?
 Pro další podporu navštivte[Stránka podpory Aspose.Finance](https://forum.aspose.com/c/finance/43).