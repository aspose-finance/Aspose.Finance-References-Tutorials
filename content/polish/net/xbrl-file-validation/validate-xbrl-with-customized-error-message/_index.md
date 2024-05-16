---
title: Sprawdź poprawność XBRL za pomocą niestandardowego komunikatu o błędzie
linktitle: Sprawdź poprawność XBRL za pomocą niestandardowego komunikatu o błędzie
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak sprawdzać instancje XBRL za pomocą Aspose.Finance dla .NET, korzystając ze szczegółowego przewodnika krok po kroku. Bez wysiłku zapewnij dokładność i zgodność swoich danych finansowych.
type: docs
weight: 12
url: /pl/net/xbrl-file-validation/validate-xbrl-with-customized-error-message/
---
## Wstęp
świecie sprawozdawczości finansowej dokładność i zgodność nie podlegają negocjacjom. Programiści pracujący z dokumentami eXtensible Business Reporting Language (XBRL) muszą upewnić się, że dokumenty te spełniają wszystkie wymagania dotyczące sprawdzania poprawności, aby zachować integralność danych. Aspose.Finance dla .NET oferuje potężne narzędzia do skutecznego zarządzania i sprawdzania instancji XBRL. Ten kompleksowy przewodnik przeprowadzi Cię przez proces sprawdzania poprawności dokumentów XBRL i dostosowywania komunikatów o błędach za pomocą Aspose.Finance dla .NET. Pod koniec tego samouczka będziesz mieć pewność, że dane XBRL są dokładne i zgodne ze standardami sprawozdawczości finansowej.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnijmy się, że masz niezbędne narzędzia i konfigurację:
### Środowisko programistyczne .NET
Upewnij się, że na komputerze skonfigurowano środowisko programistyczne .NET. Jeśli nie, pobierz i zainstaluj najnowszą wersję pakietu .NET SDK z oficjalnej witryny Microsoft.
### Aspose.Finance dla .NET
Pobierz i zainstaluj Aspose.Finance dla .NET z oficjalnego linku do pobrania podanego poniżej:
[Pobierz Aspose.Finance dla .NET](https://releases.aspose.com/finance/net/)
### Instancja XBRL
Przygotuj plik instancji XBRL, który chcesz sprawdzić za pomocą Aspose.Finance dla .NET. Upewnij się, że masz ścieżkę pliku gotową do odniesienia w kodzie.
## Importuj przestrzenie nazw
Aby uzyskać dostęp do funkcjonalności Aspose.Finance, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu .NET. Wykonaj następujące kroki:
## Krok 1: Otwórz swój projekt .NET
Uruchom projekt .NET w preferowanym zintegrowanym środowisku programistycznym (IDE), takim jak Visual Studio.
## Krok 2: Dodaj referencje Aspose.Finance
Dodaj odniesienie do Aspose.Finance dla .NET w swoim projekcie. Możesz to zrobić, pobierając bibliotekę i odwołując się do niej lokalnie lub używając Menedżera pakietów NuGet, aby zainstalować ją bezpośrednio w projekcie.
## Krok 3: Importuj przestrzenie nazw
Zaimportuj wymagane przestrzenie nazw na początku pliku kodu. Te przestrzenie nazw zapewniają dostęp do klas i metod potrzebnych do pracy z dokumentami XBRL.
```csharp
using Aspose.Finance.Xbrl;
using Aspose.Finance.Xbrl.Validator;
using System;
```
## Sprawdź poprawność XBRL za pomocą niestandardowego komunikatu o błędzie
Teraz, gdy mamy skonfigurowane środowisko i zaimportowane niezbędne przestrzenie nazw, przejdźmy do procesu sprawdzania poprawności instancji XBRL i dostosowywania komunikatów o błędach przy użyciu Aspose.Finance dla .NET.
## Krok 1: Zdefiniuj katalog źródłowy
 Zacznij od zdefiniowania ścieżki katalogu, w którym znajduje się plik instancji XBRL. Zastępować`"Your Source Directory"` z rzeczywistą ścieżką do pliku.
```csharp
string sourceDir = "Your Source Directory";
```
## Krok 2: Utwórz obiekt XbrlDocument
 Stworzyć`XbrlDocument` obiekt, podając ścieżkę do pliku instancji XBRL.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## Krok 3: Uzyskaj dostęp do instancji XBRL
 Uzyskaj dostęp do instancji XBRL z dokumentu za pomocą`XbrlInstances` nieruchomość.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## Krok 4: Zweryfikuj instancję XBRL
 Wywołaj`Validate()` metoda na`XbrlInstance` obiekt w celu sprawdzenia instancji XBRL.
```csharp
xbrlInstance.Validate();
```
## Krok 5: Radź sobie z błędami walidacji za pomocą niestandardowych komunikatów
Jeśli w instancji XBRL występują błędy sprawdzania poprawności, pobierz je i obsłuż, dostarczając dostosowane komunikaty o błędach.
```csharp
if (xbrlInstance.ValidationErrors.Count > 0)
{
    foreach (ValidationError validationError in xbrlInstance.ValidationErrors)
    {
        if (validationError.Code == ValidationErrorCode.ContextPeriodStartAfterEnd)
        {
            ContextValidationError contextValidationError = validationError as ContextValidationError;
            Console.WriteLine("Validation error: end date is before start date in context " + contextValidationError.Object.Id);
        }
        else
        {
            Console.WriteLine("Find validation error: " + validationError.Message);
        }
    }
}
```
## Krok 6: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika, że proces walidacji został pomyślnie wykonany.
```csharp
Console.WriteLine("ValidateXBRLWithCustomizedErrorMessage executed successfully.");
```
Wykonując te kroki, pomyślnie sprawdziłeś instancję XBRL i dostosowane komunikaty o błędach przy użyciu Aspose.Finance dla .NET.
## Wniosek
W tym samouczku zbadaliśmy proces sprawdzania poprawności instancji XBRL przy użyciu Aspose.Finance dla .NET i dostosowywania komunikatów o błędach w celu zapewnienia bardziej szczegółowych i konkretnych informacji zwrotnych. Dzięki dostarczonemu przewodnikowi krok po kroku możesz bez wysiłku zapewnić integralność i zgodność danych XBRL w aplikacjach .NET.
## Często zadawane pytania
### Co to jest XBRL?
XBRL, czyli eXtensible Business Reporting Language, to ustandaryzowany format elektronicznej komunikacji danych biznesowych i finansowych.
### Dlaczego sprawdzanie poprawności instancji XBRL jest ważne?
Walidacja instancji XBRL gwarantuje, że zawarte w nich dane finansowe są zgodne z taksonomią XBRL i spełniają wymogi regulacyjne, minimalizując błędy i zapewniając spójność.
### Czy Aspose.Finance może efektywnie obsługiwać duże instancje XBRL?
Tak, Aspose.Finance dla .NET jest zoptymalizowany pod kątem wydajności i może efektywnie obsługiwać duże instancje XBRL, zapewniając szybkie i niezawodne możliwości walidacji.
### Czy istnieją jakieś standardy zgodności obsługiwane przez Aspose.Finance w zakresie walidacji XBRL?
Tak, Aspose.Finance dla .NET obsługuje różne standardy zgodności i wymagania regulacyjne, umożliwiając programistom sprawdzanie instancji XBRL zgodnie z określonymi wytycznymi.
### Czy błędy walidacji można dostosować w Aspose.Finance?
Tak, Aspose.Finance dla .NET zapewnia elastyczność dostosowywania błędów sprawdzania poprawności i obsługi ich programowo, umożliwiając programistom wdrożenie dostosowanej logiki obsługi błędów w razie potrzeby.