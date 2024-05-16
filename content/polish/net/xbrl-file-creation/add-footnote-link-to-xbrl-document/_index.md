---
title: Dodaj łącze do przypisu do dokumentu XBRL
linktitle: Dodaj łącze do przypisu do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak dodawać łącza do przypisów do dokumentów XBRL za pomocą Aspose.Finance dla .NET. Bez wysiłku wzbogacaj raporty finansowe o dodatkowy kontekst.
type: docs
weight: 12
url: /pl/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Dodanie łącza do przypisu do dokumentu XBRL ma kluczowe znaczenie dla zapewnienia dodatkowego kontekstu lub wyjaśnień dla określonych punktów danych. W tym samouczku przeprowadzimy krok po kroku proces przy użyciu Aspose.Finance dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1.  Aspose.Finance dla .NET: Upewnij się, że zainstalowałeś Aspose.Finance dla .NET w swoim systemie. Można go pobrać z[Tutaj](https://releases.aspose.com/finance/net/).
  
2. Środowisko programistyczne: skonfiguruj środowisko programistyczne z platformą .NET Framework lub .NET Core.
## Importuj przestrzenie nazw:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Krok 1: Ustaw katalogi źródłowe i wyjściowe
Najpierw określ katalogi dla plików źródłowych i wyjściowych:
```csharp
// Katalog źródłowy
string sourceDir = "Your Source Directory";
// Katalog wyjściowy
string outputDir = "Your Output Directory";
```
## Krok 2: Utwórz dokument i instancję XBRL
Zainicjuj dokument i instancję XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Krok 3: Dodaj odniesienia do schematu
Dodaj odniesienia do schematu do instancji XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://przykład.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Krok 4: Zdefiniuj kontekst
Zdefiniuj kontekst dla instancji XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Krok 5: Dodaj link do przypisu
Utwórz i dodaj łącze przypisu do instancji XBRL:
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
## Krok 6: Zapisz dokument
Zapisz zmodyfikowany dokument XBRL:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Wniosek
Dodawanie łącza do przypisu do dokumentu XBRL jest prostym procesem dzięki Aspose.Finance dla .NET. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo włączyć dodatkowy kontekst lub wyjaśnienia do swoich raportów finansowych.
## Często zadawane pytania
### Czy mogę dodać wiele łączy do przypisów do jednego dokumentu XBRL?
Tak, możesz dodać wiele łączy do przypisów, powtarzając kroki opisane w tym samouczku dla każdego dodatkowego łącza.
### Czy Aspose.Finance dla .NET jest kompatybilny zarówno z .NET Framework, jak i .NET Core?
Tak, Aspose.Finance dla .NET obsługuje środowiska .NET Framework i .NET Core.
### Jak mogę uzyskać tymczasową licencję na Aspose.Finance dla .NET?
 Licencję tymczasową można uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy Aspose.Finance dla .NET zapewnia obsługę sprawdzania poprawności XBRL?
Tak, Aspose.Finance dla .NET oferuje kompleksowe wsparcie dla walidacji XBRL w celu zapewnienia zgodności ze standardami branżowymi.
### Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Finance dla .NET?
 Możesz odwiedzić[Forum Aspose.Finance dla .NET](https://forum.aspose.com/c/finance/43) w celu uzyskania wsparcia i dostępu do dokumentacji[Tutaj](https://reference.aspose.com/finance/net/).