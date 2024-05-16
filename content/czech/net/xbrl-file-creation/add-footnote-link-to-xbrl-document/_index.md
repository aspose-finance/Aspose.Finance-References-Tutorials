---
title: Přidat odkaz na poznámku pod čarou do dokumentu XBRL
linktitle: Přidat odkaz na poznámku pod čarou do dokumentu XBRL
second_title: Aspose.Finance .NET API
description: Naučte se přidávat odkazy na poznámky pod čarou do dokumentů XBRL pomocí Aspose.Finance for .NET. Vylepšete finanční zprávy o další kontext bez námahy.
type: docs
weight: 12
url: /cs/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Přidání odkazu na poznámku pod čarou do dokumentu XBRL je zásadní pro poskytnutí dalšího kontextu nebo vysvětlení pro konkrétní datové body. V tomto tutoriálu projdeme procesem krok za krokem pomocí Aspose.Finance for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Finance for .NET: Ujistěte se, že jste na svůj systém nainstalovali Aspose.Finance for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/finance/net/).
  
2. Vývojové prostředí: Nechte si nastavit vývojové prostředí s rozhraním .NET Framework nebo .NET Core.
## Importovat jmenné prostory:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Krok 1: Nastavte zdrojové a výstupní adresáře
Nejprve zadejte adresáře pro zdrojové a výstupní soubory:
```csharp
// Zdrojový adresář
string sourceDir = "Your Source Directory";
// Výstupní adresář
string outputDir = "Your Output Directory";
```
## Krok 2: Vytvořte dokument a instanci XBRL
Inicializujte dokument a instanci XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Krok 3: Přidejte odkazy na schéma
Přidejte odkazy schématu do instance XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Krok 4: Definujte kontext
Definujte kontext pro instanci XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Krok 5: Přidejte odkaz na poznámku pod čarou
Vytvořte a přidejte odkaz na poznámku pod čarou do instance XBRL:
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
## Krok 6: Uložte dokument
Uložte upravený dokument XBRL:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Závěr
Přidání odkazu na poznámku pod čarou do dokumentu XBRL je s Aspose.Finance pro .NET jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete do svých finančních výkazů bez problémů začlenit další kontext nebo vysvětlení.
## Nejčastější dotazy
### Mohu přidat více odkazů na poznámky pod čarou do jednoho dokumentu XBRL?
Ano, můžete přidat více odkazů na poznámky pod čarou opakováním kroků uvedených v tomto kurzu pro každý další odkaz.
### Je Aspose.Finance for .NET kompatibilní s .NET Framework i .NET Core?
Ano, Aspose.Finance for .NET podporuje prostředí .NET Framework i .NET Core.
### Jak mohu získat dočasnou licenci pro Aspose.Finance pro .NET?
 Dočasnou licenci můžete získat od[tady](https://purchase.aspose.com/temporary-license/).
### Poskytuje Aspose.Finance for .NET podporu pro ověřování XBRL?
Ano, Aspose.Finance for .NET nabízí komplexní podporu pro ověřování XBRL pro zajištění souladu s průmyslovými standardy.
### Kde najdu další zdroje a podporu pro Aspose.Finance pro .NET?
 Můžete navštívit[Aspose.Finance for .NET fórum](https://forum.aspose.com/c/finance/43) pro podporu a přístupovou dokumentaci[tady](https://reference.aspose.com/finance/net/).