---
title: Dodaj odniesienie do roli do dokumentu XBRL
linktitle: Dodaj odniesienie do roli do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak dodawać odniesienia do ról do dokumentów XBRL za pomocą Aspose.Finance dla .NET. Dzięki temu samouczkowi uprość raportowanie finansowe w aplikacjach .NET.
type: docs
weight: 14
url: /pl/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) stał się standardem wymiany informacji biznesowych, zwłaszcza w zakresie sprawozdawczości finansowej. Aspose.Finance dla .NET upraszcza pracę z dokumentami XBRL w aplikacjach .NET. Ten samouczek poprowadzi Cię przez proces dodawania odniesienia do roli do dokumentu XBRL przy użyciu Aspose.Finance dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Zainstaluj Aspose.Finance dla .NET
Upewnij się, że masz zainstalowany Aspose.Finance for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz go z[wydania](https://releases.aspose.com/finance/net/) i postępuj zgodnie z instrukcją instalacji.
### 2. Skonfiguruj swoje środowisko programistyczne
Upewnij się, że masz działające środowisko programistyczne do programowania .NET. Obejmuje to kompatybilne środowisko IDE, takie jak Visual Studio i środowisko .NET zainstalowane w systemie.
## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do aplikacji .NET, aby uzyskać dostęp do funkcjonalności zapewnianej przez Aspose.Finance dla .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Krok 4: Pobierz typ roli i dodaj odniesienie do roli
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Pobierz typ roli przy użyciu jej identyfikatora URI i dodaj odwołanie do roli do instancji XBRL.
## Krok 5: Zapisz dokument
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Zapisz dokument XBRL w katalogu wyjściowym.
## Wniosek
Dodanie odniesień do ról do dokumentów XBRL jest kluczowe dla zdefiniowania ról różnych elementów w dokumencie. Aspose.Finance dla .NET zapewnia prosty sposób wykonania tego zadania, umożliwiając programistom efektywną pracę z dokumentami XBRL w ich aplikacjach .NET.
## Często zadawane pytania
### Czy mogę używać Aspose.Finance dla .NET z dowolną aplikacją .NET?
Tak, Aspose.Finance dla .NET jest kompatybilny z dowolną aplikacją .NET, w tym ASP.NET, WinForms i aplikacjami konsolowymi.
### Czy korzystanie z Aspose.Finance dla .NET jest darmowe?
 Aspose.Finance dla .NET jest biblioteką komercyjną. Możesz pobrać bezpłatną wersję próbną, aby ocenić jej funkcje, a licencje można kupić[Tutaj](https://purchase.aspose.com/buy).
### Czy Aspose.Finance dla .NET obsługuje inne formaty raportowania finansowego poza XBRL?
Aspose.Finance dla .NET skupia się przede wszystkim na funkcjonalnościach związanych z XBRL. Jednak Aspose oferuje inne biblioteki do pracy z różnymi formatami finansowymi.
### Jak mogę uzyskać wsparcie dla Aspose.Finance dla .NET?
 Możesz uzyskać wsparcie dla Aspose.Finance dla .NET poprzez[forum](https://forum.aspose.com/c/finance/43)gdzie możesz zadawać pytania i kontaktować się z innymi użytkownikami oraz personelem pomocniczym.
### Czy mogę uzyskać tymczasową licencję na Aspose.Finance dla .NET?
 Tak, tymczasowe licencje dla Aspose.Finance dla .NET są dostępne do celów testowych. Możesz taki otrzymać[Tutaj](https://purchase.aspose.com/temporary-license/).