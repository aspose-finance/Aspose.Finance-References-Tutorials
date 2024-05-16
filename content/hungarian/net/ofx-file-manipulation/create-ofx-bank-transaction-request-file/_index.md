---
title: Hozzon létre OFX banki tranzakciókérés fájlt
linktitle: Hozzon létre OFX banki tranzakciókérés fájlt
second_title: Aspose.Finance .NET API
description: Részletes, lépésenkénti útmutatónkból megtudhatja, hogyan hozhat létre OFX banki tranzakciókérés-fájlt az Aspose.Finance for .NET használatával. #Aspose #Pénzügyek
type: docs
weight: 12
url: /hu/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Egy OFX banki tranzakciókérés-fájl létrehozása ijesztőnek tűnhet, de megfelelő eszközökkel és útmutatásokkal ez egyszerű folyamat lehet. Ebben az oktatóanyagban végigvezetjük az OFX banki tranzakciókérés-fájl létrehozásának minden lépésén az Aspose.Finance for .NET használatával. Leírjuk az előfeltételeket, a szükséges névtereket, és részletes, lépésről lépésre útmutatót adunk, hogy könnyen követhesse.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, néhány dolgot meg kell határoznia:
1.  Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a számítógépére. Letöltheti a[hivatalos honlapján](https://visualstudio.microsoft.com/).
2.  Aspose.Finance for .NET: Szüksége van az Aspose.Finance for .NET könyvtárra. Letöltheti innen[itt](https://releases.aspose.com/finance/net/).
3. Alapvető C# ismeretek: A C# programozás alapjainak megértése segít a kódpéldák követésében.
Ha ezek az előfeltételek adottak, készen áll a kezdésre!
## Névterek importálása
Először is importáljuk a szükséges névtereket. Ezek a névterek kulcsfontosságúak az OFX banki tranzakciókérés fájl létrehozásához szükséges osztályok és metódusok eléréséhez.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## 1. lépés: Állítsa be a munkakönyvtárat
Mielőtt elkezdené az OFX kérésfájl létrehozását, meg kell adnunk a kimeneti könyvtárat, ahová a fájl mentésre kerül.
```csharp
string outputDir = "Your Output Directory";
```
 Cserélje ki`"Your Output Directory"` annak a könyvtárnak az elérési útjával, ahová a generált fájlt menteni szeretné.
## 2. lépés: Hozza létre az OFX-kérés dokumentumát
 Ezután létre kell hoznunk egy példányt a`OfxRequestDocument` osztály. Ez az osztály fog szolgálni az OFX kérésünk tárolójaként.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## 3. lépés: Állítsa be a bejelentkezési kérelmet
bejelentkezési kérelem elengedhetetlen a felhasználó hitelesítéséhez és az OFX munkamenet elindításához. Beállítjuk a bejelentkezési kérelmet, és feltöltjük a szükséges adatokkal, például az ügyfél dátumával, felhasználói azonosítójával, jelszavával és pénzintézeti adataival.
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
## 4. lépés: Állítsa be a Bank Request üzenetet
Most, hogy a bejelentkezési kérelem be van állítva, továbblépünk a banki kérelmet tartalmazó üzenet létrehozására. Ez az üzenet tartalmazza a bankszámla adatait és a tranzakciós kivonat kérését.
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
## 5. lépés: Adja meg a tranzakció részleteit
 Konkrét tranzakciók lekéréséhez meg kell adnunk a dátumtartományt, és azt, hogy szerepeljenek-e a tranzakciók a kérelemben. Ez úgy történik, hogy beállítja a`IncTransaction` tárgy.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## 6. lépés: Mentse el az OFX-kérés dokumentumát
Végül elmentjük az OFX kérelem dokumentumot XML és SGML formátumban is. Ez biztosítja a kompatibilitást a különböző rendszerekkel, amelyek bármelyik formátumot használhatják.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## 7. lépés: Erősítse meg a sikeres végrehajtást
folyamat sikeres végrehajtásának megerősítésére egy üzenetet nyomtathatunk a konzolra.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Következtetés
Az OFX banki tranzakciókérés-fájl létrehozása az Aspose.Finance for .NET használatával egy módszeres folyamat, amely magában foglalja egy kérési dokumentum beállítását, a bejelentkezési és banki kérés üzenetek konfigurálását, a tranzakció részleteinek megadását és a dokumentum mentését. Ennek a lépésről-lépésre szóló útmutatónak a követésével hatékonyan hozhat létre az Ön egyedi igényeihez szabott OFX-kérés fájlokat.
## GYIK
### 1. Mi az OFX fájl?
Az OFX (Open Financial Exchange) fájl egy szabványos formátum, amelyet az intézmények és a felhasználók közötti pénzügyi adatok cseréjére használnak. Széles körben használják bankszámlakivonatokhoz, tranzakciókhoz és egyéb pénzügyi tevékenységekhez.
### 2. Használhatom az Aspose.Finance for .NET-et más programozási nyelvekkel?
Az Aspose.Finance for .NET kifejezetten a .NET nyelvekhez, például a C#-hoz készült. Használhatja azonban bármely .NET által támogatott környezetben.
### 3. Elérhető ingyenes próbaverzió az Aspose.Finance for .NET számára?
Igen, letöltheti az Aspose.Finance ingyenes próbaverzióját .NET-hez a webhelyről[itt](https://releases.aspose.com/).
### 4. Hogyan kaphatok támogatást az Aspose.Finance for .NET-hez?
 Támogatást kaphat az Aspose közösségtől és a technikai csapattól az ő rajtuk keresztül[támogatói fórum](https://forum.aspose.com/c/finance/43).
### 5. Kaphatok ideiglenes licencet az Aspose.Finance for .NET számára?
 Igen, az Aspose kínál a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) amelyek segítségével értékelheti a terméket.