---
title: Utwórz plik żądania transakcji bankowej OFX
linktitle: Utwórz plik żądania transakcji bankowej OFX
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak utworzyć plik żądania transakcji bankowej OFX za pomocą Aspose.Finance dla .NET, korzystając z naszego szczegółowego przewodnika krok po kroku. #Aspose #Finanse
type: docs
weight: 12
url: /pl/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Utworzenie pliku żądania transakcji bankowej OFX może wydawać się trudne, ale przy odpowiednich narzędziach i wskazówkach może być prostym procesem. W tym samouczku przeprowadzimy Cię przez każdy etap generowania pliku żądania transakcji bankowej OFX przy użyciu Aspose.Finance dla .NET. Omówimy wymagania wstępne, niezbędne przestrzenie nazw i udostępnimy szczegółowy przewodnik krok po kroku, dzięki któremu będziesz mógł łatwo wykonać wszystkie czynności.
## Warunki wstępne
Zanim przejdziemy do samouczka, musisz przygotować kilka rzeczy:
1.  Visual Studio: Upewnij się, że na komputerze jest zainstalowany program Visual Studio. Można go pobrać z[oficjalna strona internetowa](https://visualstudio.microsoft.com/).
2.  Aspose.Finance dla .NET: Potrzebujesz biblioteki Aspose.Finance dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/finance/net/).
3. Podstawowa znajomość języka C#: Zrozumienie podstaw programowania w języku C# pomoże Ci postępować zgodnie z przykładami kodu.
Po spełnieniu tych wymagań wstępnych możesz zacząć!
## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw. Te przestrzenie nazw są kluczowe dla dostępu do klas i metod wymaganych do utworzenia pliku żądania transakcji bankowej OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Krok 1: Skonfiguruj katalog roboczy
Zanim zaczniemy tworzyć plik żądania OFX, musimy określić katalog wyjściowy, w którym plik zostanie zapisany.
```csharp
string outputDir = "Your Output Directory";
```
 Zastępować`"Your Output Directory"` ze ścieżką do katalogu, w którym chcesz zapisać wygenerowany plik.
## Krok 2: Utwórz dokument żądania OFX
 Następnie musimy utworzyć instancję`OfxRequestDocument` klasa. Ta klasa będzie służyć jako kontener dla naszego żądania OFX.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Krok 3: Skonfiguruj żądanie wpisania
Żądanie wpisania jest niezbędne do uwierzytelnienia użytkownika i zainicjowania sesji OFX. Skonfigurujemy wiadomość z żądaniem logowania i wypełnimy ją niezbędnymi szczegółami, takimi jak data klienta, identyfikator użytkownika, hasło i informacje o instytucji finansowej.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Krok 4: Skonfiguruj wiadomość dotyczącą żądania banku
Teraz, gdy żądanie logowania jest skonfigurowane, przejdziemy do tworzenia wiadomości z żądaniem banku. Wiadomość ta będzie zawierać dane rachunku bankowego oraz prośbę o wyciąg z transakcji.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Krok 5: Dołącz szczegóły transakcji
 Aby pobrać konkretne transakcje, musimy określić zakres dat oraz czy uwzględnić transakcje w żądaniu. Odbywa się to poprzez ustawienie`IncTransaction` obiekt.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Krok 6: Zapisz dokument żądania OFX
Na koniec zapiszemy dokument żądania OFX w formacie XML i SGML. Zapewnia to kompatybilność z różnymi systemami, które mogą używać dowolnego formatu.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Krok 7: Potwierdź pomyślne wykonanie
Aby potwierdzić pomyślne wykonanie procesu, możemy wydrukować komunikat na konsolę.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Wniosek
Tworzenie pliku żądania transakcji bankowej OFX przy użyciu Aspose.Finance dla .NET jest metodycznym procesem obejmującym skonfigurowanie dokumentu żądania, skonfigurowanie komunikatów logowania i żądań bankowych, określenie szczegółów transakcji i zapisanie dokumentu. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz efektywnie generować pliki żądań OFX dostosowane do Twoich konkretnych potrzeb.
## Często zadawane pytania
### 1. Co to jest plik OFX?
Plik OFX (Open Financial Exchange) to standardowy format używany do wymiany danych finansowych pomiędzy instytucjami i użytkownikami. Jest szeroko stosowany do wyciągów bankowych, transakcji i innych działań finansowych.
### 2. Czy mogę używać Aspose.Finance dla .NET z innymi językami programowania?
Aspose.Finance dla .NET jest specjalnie zaprojektowany do użytku z językami .NET, takimi jak C#. Można go jednak używać w dowolnym środowisku obsługiwanym przez platformę .NET.
### 3. Czy dostępna jest bezpłatna wersja próbna Aspose.Finance dla .NET?
Tak, możesz pobrać bezpłatną wersję próbną Aspose.Finance dla .NET z[Tutaj](https://releases.aspose.com/).
### 4. Jak uzyskać wsparcie dla Aspose.Finance dla .NET?
 Możesz uzyskać wsparcie od społeczności Aspose i zespołu technicznego za ich pośrednictwem[forum wsparcia](https://forum.aspose.com/c/finance/43).
### 5. Czy mogę uzyskać tymczasową licencję na Aspose.Finance dla .NET?
 Tak, Aspose oferuje[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) które możesz wykorzystać do oceny produktu.