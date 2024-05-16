---
title: Přidat položku do dokumentu XBRL
linktitle: Přidat položku do dokumentu XBRL
second_title: Aspose.Finance .NET API
description: Naučte se přidávat položky do dokumentů XBRL pomocí Aspose.Finance for .NET. Zjednodušte finanční výkaznictví ve svých aplikacích .NET. #Apose #Finance
type: docs
weight: 13
url: /cs/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) se stal standardním formátem pro finanční výkaznictví, který umožňuje efektivní a přesnou komunikaci finančních dat. Aspose.Finance for .NET poskytuje robustní funkce pro práci s dokumenty XBRL ve vašich aplikacích .NET. V tomto tutoriálu si projdeme kroky k přidání položky do dokumentu XBRL pomocí Aspose.Finance for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
### 1. Nainstalujte Aspose.Finance pro .NET
 Pokud jste to ještě neudělali, stáhněte si a nainstalujte Aspose.Finance for .NET z[oficiální webové stránky](https://releases.aspose.com/finance/net/). Postupujte podle pokynů k instalaci a nastavte knihovnu ve vašem prostředí .NET.
### 2. Nastavte své vývojové prostředí
Ujistěte se, že máte funkční vývojové prostředí pro vývoj .NET. Budete potřebovat kompatibilní IDE, jako je Visual Studio, spolu s .NET frameworkem nainstalovaným ve vašem systému.
## Import jmenných prostorů
Nejprve naimportujte potřebné jmenné prostory do své aplikace .NET, abyste mohli využívat funkce poskytované Aspose.Finance pro .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Nyní si ukázkový kód rozdělíme do několika kroků:
## Krok 1: Definujte zdrojové a výstupní adresáře
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Nahradit`"Your Source Directory"` a`"Your Output Directory"` s cestami ke zdrojovým a výstupním adresářům.
## Krok 2: Vytvořte dokument a instanci XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inicializujte dokument XBRL a instanci, se kterou chcete pracovat.
## Krok 3: Přidejte odkaz na schéma
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Přidejte odkaz na schéma k instanci XBRL, uveďte cestu k souboru schématu a určete podrobnosti o jmenném prostoru.
## Krok 4: Definujte kontext a entitu
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Vytvořte kontext a entitu pro instanci XBRL s uvedením období a podrobností o entitě.
## Krok 5: Přidejte jednotku
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Definujte jednotku pro instanci XBRL a uveďte kvalifikované názvy míry.
## Krok 6: Přidejte položku
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
Přidejte položku do instance XBRL a určete její koncept, kontext, jednotku, přesnost a hodnotu.
## Krok 7: Uložte dokument
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Uložte dokument XBRL do výstupního adresáře.
## Závěr
Přidání položek do dokumentu XBRL je nezbytné pro přesnou reprezentaci finančních dat. Aspose.Finance for .NET zjednodušuje tento proces tím, že poskytuje komplexní API pro práci s dokumenty XBRL v aplikacích .NET.
## Nejčastější dotazy
### Mohu používat Aspose.Finance pro .NET s jakoukoli aplikací .NET?
Ano, Aspose.Finance for .NET je kompatibilní s jakoukoli aplikací .NET, včetně aplikací ASP.NET, WinForms a Console.
### Je Aspose.Finance for .NET k použití zdarma?
 Aspose.Finance for .NET je komerční knihovna. Můžete si stáhnout bezplatnou zkušební verzi, abyste mohli vyhodnotit její funkce, a licence lze zakoupit od[tady](https://purchase.aspose.com/buy).
### Podporuje Aspose.Finance for .NET jiné formáty finančního výkaznictví kromě XBRL?
Aspose.Finance for .NET se primárně zaměřuje na funkce související s XBRL. Aspose však nabízí další knihovny pro práci s různými finančními formáty.
### Jak mohu získat podporu pro Aspose.Finance pro .NET?
 Podporu pro Aspose.Finance pro .NET můžete získat prostřednictvím[oficiální fórum](https://forum.aspose.com/c/finance/43)kde můžete klást otázky a komunikovat s ostatními uživateli a pracovníky podpory.
### Mohu získat dočasnou licenci pro Aspose.Finance pro .NET?
 Ano, dočasné licence pro Aspose.Finance pro .NET jsou k dispozici pro testovací účely. Můžete získat jeden[tady](https://purchase.aspose.com/temporary-license/).