---
title: Dodaj pozycję do dokumentu XBRL
linktitle: Dodaj pozycję do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak dodawać elementy do dokumentów XBRL za pomocą Aspose.Finance dla .NET. Uprość raportowanie finansowe w aplikacjach .NET. #Aspose #Finanse
type: docs
weight: 13
url: /pl/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) stał się standardowym formatem sprawozdawczości finansowej, umożliwiającym sprawne i dokładne przekazywanie danych finansowych. Aspose.Finance dla .NET zapewnia solidną funkcjonalność do pracy z dokumentami XBRL w aplikacjach .NET. W tym samouczku omówimy kroki dodawania elementu do dokumentu XBRL przy użyciu Aspose.Finance dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
### 1. Zainstaluj Aspose.Finance dla .NET
 Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj Aspose.Finance dla .NET z[oficjalna strona internetowa](https://releases.aspose.com/finance/net/). Postępuj zgodnie z instrukcjami instalacji, aby skonfigurować bibliotekę w środowisku .NET.
### 2. Skonfiguruj swoje środowisko programistyczne
Upewnij się, że masz działające środowisko programistyczne do programowania .NET. Będziesz potrzebować kompatybilnego IDE, takiego jak Visual Studio, wraz ze środowiskiem .NET zainstalowanym w twoim systemie.
## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw do aplikacji .NET, aby skorzystać z funkcjonalności zapewnianej przez Aspose.Finance dla .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Teraz podzielmy przykładowy kod na wiele kroków:
## Krok 1: Zdefiniuj katalogi źródłowe i wyjściowe
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Zastępować`"Your Source Directory"` I`"Your Output Directory"` ze ścieżkami odpowiednio do katalogów źródłowych i wyjściowych.
## Krok 2: Utwórz dokument i instancję XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Zainicjuj dokument XBRL i instancję, z którą chcesz pracować.
## Krok 3: Dodaj odniesienie do schematu
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://przykład.com/xbrl/taxonomy");
```
Dodaj odwołanie do schematu do instancji XBRL, podając ścieżkę do pliku schematu i określając szczegóły przestrzeni nazw.
## Krok 4: Zdefiniuj kontekst i encję
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Utwórz kontekst i encję dla instancji XBRL, określając okres i szczegóły encji.
## Krok 5: Dodaj jednostkę
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Zdefiniuj jednostkę dla instancji XBRL, podając kwalifikowane nazwy miary.
## Krok 6: Dodaj element
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
Dodaj element do instancji XBRL, określając jego koncepcję, kontekst, jednostkę, precyzję i wartość.
## Krok 7: Zapisz dokument
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Zapisz dokument XBRL w katalogu wyjściowym.
## Wniosek
Dodawanie pozycji do dokumentu XBRL jest niezbędne do dokładnego przedstawienia danych finansowych. Aspose.Finance dla .NET upraszcza ten proces, udostępniając kompleksowe API do pracy z dokumentami XBRL w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę używać Aspose.Finance dla .NET z dowolną aplikacją .NET?
Tak, Aspose.Finance dla .NET jest kompatybilny z dowolną aplikacją .NET, w tym ASP.NET, WinForms i aplikacjami konsolowymi.
### Czy korzystanie z Aspose.Finance dla .NET jest darmowe?
 Aspose.Finance dla .NET jest biblioteką komercyjną. Możesz pobrać bezpłatną wersję próbną, aby ocenić jej funkcje, a licencje można kupić[Tutaj](https://purchase.aspose.com/buy).
### Czy Aspose.Finance dla .NET obsługuje inne formaty raportowania finansowego poza XBRL?
Aspose.Finance dla .NET skupia się przede wszystkim na funkcjonalnościach związanych z XBRL. Jednak Aspose oferuje inne biblioteki do pracy z różnymi formatami finansowymi.
### Jak mogę uzyskać wsparcie dla Aspose.Finance dla .NET?
 Możesz uzyskać wsparcie dla Aspose.Finance dla .NET poprzez[oficjalne forum](https://forum.aspose.com/c/finance/43)gdzie możesz zadawać pytania i kontaktować się z innymi użytkownikami oraz personelem pomocniczym.
### Czy mogę uzyskać tymczasową licencję na Aspose.Finance dla .NET?
 Tak, tymczasowe licencje dla Aspose.Finance dla .NET są dostępne do celów testowych. Możesz taki otrzymać[Tutaj](https://purchase.aspose.com/temporary-license/).