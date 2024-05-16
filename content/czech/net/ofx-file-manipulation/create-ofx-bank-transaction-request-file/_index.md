---
title: Vytvořte soubor požadavku bankovní transakce OFX
linktitle: Vytvořte soubor požadavku bankovní transakce OFX
second_title: Aspose.Finance .NET API
description: Naučte se, jak vytvořit soubor požadavku bankovní transakce OFX pomocí Aspose.Finance for .NET s naším podrobným průvodcem krok za krokem. #Apose #Finance
type: docs
weight: 12
url: /cs/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Vytvoření souboru žádosti o bankovní transakci OFX se může zdát skličující, ale se správnými nástroji a pokyny to může být přímočarý proces. V tomto tutoriálu vás provedeme každým krokem generování souboru požadavku bankovní transakce OFX pomocí Aspose.Finance for .NET. Pokryjeme předpoklady, potřebné jmenné prostory a poskytneme podrobného průvodce krok za krokem, abyste mohli snadno sledovat.
## Předpoklady
Než se pustíme do výukového programu, je třeba mít připraveno několik věcí:
1.  Visual Studio: Ujistěte se, že máte v počítači nainstalované Visual Studio. Můžete si jej stáhnout z[oficiální webové stránky](https://visualstudio.microsoft.com/).
2.  Aspose.Finance for .NET: Potřebujete knihovnu Aspose.Finance for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/finance/net/).
3. Základní znalosti C#: Pochopení základů programování v C# vám pomůže sledovat příklady kódu.
Jakmile splníte tyto předpoklady, jste připraveni začít!
## Import jmenných prostorů
Nejprve importujme potřebné jmenné prostory. Tyto jmenné prostory jsou klíčové pro přístup ke třídám a metodám potřebným k vytvoření souboru požadavku bankovní transakce OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Krok 1: Nastavte pracovní adresář
Než začneme vytvářet soubor požadavku OFX, musíme určit výstupní adresář, kam bude soubor uložen.
```csharp
string outputDir = "Your Output Directory";
```
 Nahradit`"Your Output Directory"` s cestou k adresáři, kam chcete vygenerovaný soubor uložit.
## Krok 2: Vytvořte dokument požadavku OFX
 Dále musíme vytvořit instanci`OfxRequestDocument` třída. Tato třída bude sloužit jako kontejner pro náš požadavek OFX.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Krok 3: Nastavte žádost o přihlášení
Požadavek na přihlášení je nezbytný pro ověření uživatele a zahájení relace OFX. Nastavíme zprávu s žádostí o přihlášení a vyplníme ji nezbytnými podrobnostmi, jako je datum klienta, ID uživatele, heslo a informace o finanční instituci.
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
## Krok 4: Nastavte zprávu bankovního požadavku
Nyní, když je požadavek na přihlášení nastaven, přejdeme k vytvoření zprávy bankovního požadavku. Tato zpráva bude obsahovat podrobnosti o bankovním účtu a žádost o výpis transakce.
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
## Krok 5: Zahrňte podrobnosti transakce
 Abychom mohli načíst konkrétní transakce, musíme určit časové období a zda do požadavku zahrnout transakce. To se provádí nastavením`IncTransaction` objekt.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Krok 6: Uložte dokument požadavku OFX
Nakonec uložíme dokument požadavku OFX ve formátu XML i SGML. To zajišťuje kompatibilitu s různými systémy, které mohou používat oba formáty.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Krok 7: Potvrďte úspěšné provedení
Abychom potvrdili, že proces byl úspěšně proveden, můžeme vytisknout zprávu do konzole.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Závěr
Vytvoření souboru požadavku na bankovní transakci OFX pomocí Aspose.Finance for .NET je metodický proces, který zahrnuje nastavení dokumentu požadavku, konfiguraci zpráv o přihlášení a požadavku banky, specifikaci podrobností transakce a uložení dokumentu. Podle tohoto podrobného průvodce můžete efektivně generovat soubory požadavků OFX přizpůsobené vašim konkrétním potřebám.
## Nejčastější dotazy
### 1. Co je soubor OFX?
Soubor OFX (Open Financial Exchange) je standardní formát používaný pro výměnu finančních dat mezi institucemi a uživateli. Je široce používán pro bankovní výpisy, transakce a další finanční aktivity.
### 2. Mohu používat Aspose.Finance pro .NET s jinými programovacími jazyky?
Aspose.Finance for .NET je speciálně navržen pro použití s jazyky .NET, jako je C#. Můžete jej však použít v jakémkoli prostředí s podporou .NET.
### 3. Je k dispozici bezplatná zkušební verze pro Aspose.Finance pro .NET?
Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Finance pro .NET z[tady](https://releases.aspose.com/).
### 4. Jak získám podporu pro Aspose.Finance pro .NET?
 Můžete získat podporu od komunity Aspose a technického týmu prostřednictvím jejich[Fórum podpory](https://forum.aspose.com/c/finance/43).
### 5. Mohu získat dočasnou licenci pro Aspose.Finance pro .NET?
 Ano, Aspose nabízí a[dočasná licence](https://purchase.aspose.com/temporary-license/) které můžete použít k hodnocení produktu.