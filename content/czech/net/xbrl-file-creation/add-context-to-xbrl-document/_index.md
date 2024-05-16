---
title: Přidejte kontext do dokumentu XBRL
linktitle: Přidejte kontext do dokumentu XBRL
second_title: Aspose.Finance .NET API
description: Naučte se, jak přidat kontext do XBRL dokumentů v .NET pomocí Aspose.Finance pro zjednodušené finanční výkaznictví. #Apose #Finance #XBRL
type: docs
weight: 11
url: /cs/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Úvod
V oblasti finančního výkaznictví hraje XBRL (eXtensible Business Reporting Language) klíčovou roli při standardizaci výměny obchodních informací. Přidání kontextu k dokumentům XBRL je zásadní pro zajištění integrity a relevance dat, která obsahují. S Aspose.Finance for .NET se tento proces zjednodušuje a zefektivňuje a umožňuje vývojářům bezproblémově začlenit kontext do jejich dokumentů XBRL.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující předpoklady:
1. Knihovna Aspose.Finance for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Finance for .NET z[vydání](https://releases.aspose.com/finance/net/).
2. Vývojové prostředí .NET: Ujistěte se, že máte na svém počítači nastavené funkční vývojové prostředí .NET.
3. Základní porozumění C#: Znalost programovacího jazyka C# bude užitečná při následování spolu s příklady.
## Import jmenných prostorů
Ve svém projektu C# importujte potřebné jmenné prostory pro přístup k funkcím poskytovaným Aspose.Finance pro .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Krok 1: Nastavte výstupní adresář
Před přidáním kontextu do dokumentu XBRL určete výstupní adresář, kam bude upravený dokument uložen:
```csharp
string outputDir = "Your Output Directory";
```
 Nahradit`"Your Output Directory"` s požadovanou cestou ve vašem systému.
## Krok 2: Vytvořte dokument XBRL
 Instantovat an`XbrlDocument` objekt pro práci s dokumenty XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
Tento objekt představuje dokument XBRL, se kterým se bude manipulovat.
## Krok 3: Přidejte instanci XBRL
Přidejte do dokumentu instanci XBRL. Každá instance obsahuje údaje za konkrétní období přehledu:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Tento krok inicializuje instanci XBRL v dokumentu.
## Krok 4: Definujte kontextové období a entitu
Vytvořte kontextové období a entitu pro instanci XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Zadejte období a podrobnosti o entitě podle vašich požadavků na vykazování.
## Krok 5: Vytvořte kontext
Vytvořte kontext pomocí období a entity definované v předchozím kroku:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Tento kontext zapouzdřuje časové informace a informace související s entitami.
## Krok 6: Přidejte kontext do instance XBRL
Přidružte kontext vytvořený v předchozím kroku k instanci XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
Tento krok propojí kontext s instancí XBRL a poskytne relevantní kontextové informace k datům.
## Krok 7: Uložte dokument
Uložte upravený dokument XBRL do zadaného výstupního adresáře:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Tím se proces dokončí a uloží se dokument XBRL s přidaným kontextem.
## Závěr
Pomocí těchto kroků můžete efektivně přidávat kontext do dokumentů XBRL pomocí Aspose.Finance for .NET. To zvyšuje jasnost a použitelnost finančních dat, usnadňuje přesnou analýzu a výkaznictví.
## Nejčastější dotazy
### Dokáže Aspose.Finance for .NET zpracovat velké dokumenty XBRL?
Aspose.Finance for .NET je optimalizován pro zpracování dokumentů XBRL různých velikostí, včetně velkých datových sad.
### Je k dispozici zkušební verze pro Aspose.Finance pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi z oficiálních stránek Aspose.
### Podporuje Aspose.Finance for .NET další standardy finančního výkaznictví kromě XBRL?
Aspose.Finance se primárně zaměřuje na funkce související s XBRL, ale také poskytuje podporu pro další finanční formáty.
### Mohu upravit kontextové informace podle svých specifických požadavků?
Aspose.Finance for .NET samozřejmě nabízí flexibilitu pro přizpůsobení kontextových informací tak, aby vyhovovaly vašim potřebám.
### Kde najdu další podporu nebo zdroje pro Aspose.Finance for .NET?
Můžete navštívit fórum Aspose.Finance, kde získáte pomoc od komunity, nebo prozkoumat dokumentaci, kde najdete komplexní pokyny.