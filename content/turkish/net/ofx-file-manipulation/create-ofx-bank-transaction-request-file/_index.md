---
title: OFX Banka İşlem Talep Dosyası Oluştur
linktitle: OFX Banka İşlem Talep Dosyası Oluştur
second_title: Aspose.Finance .NET API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Finance for .NET'i kullanarak OFX banka işlemi istek dosyasını nasıl oluşturacağınızı öğrenin. #Aspose #Finans
type: docs
weight: 12
url: /tr/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
OFX banka işlemi istek dosyası oluşturmak göz korkutucu görünebilir, ancak doğru araçlar ve rehberlikle basit bir süreç olabilir. Bu eğitimde, Aspose.Finance for .NET'i kullanarak OFX banka işlemi istek dosyası oluşturmanın her adımında size yol göstereceğiz. Önkoşulları ve gerekli ad alanlarını ele alacağız ve kolayca takip edebilmeniz için ayrıntılı, adım adım bir kılavuz sunacağız.
## Önkoşullar
Eğiticiye dalmadan önce, hazır olmanız gereken birkaç şey var:
1.  Visual Studio: Bilgisayarınızda Visual Studio'nun kurulu olduğundan emin olun. adresinden indirebilirsiniz.[resmi internet sitesi](https://visualstudio.microsoft.com/).
2.  Aspose.Finance for .NET: Aspose.Finance for .NET kütüphanesine ihtiyacınız var. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/finance/net/).
3. Temel C# Bilgisi: C# programlamanın temellerini anlamak, kod örneklerini takip etmenize yardımcı olacaktır.
Bu önkoşulları yerine getirdikten sonra başlamaya hazırsınız!
## Ad Alanlarını İçe Aktar
Öncelikle gerekli ad alanlarını içe aktaralım. Bu ad alanları, OFX banka işlem istek dosyasını oluşturmak için gereken sınıflara ve yöntemlere erişim açısından çok önemlidir.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## 1. Adım: Çalışma Dizinini Ayarlayın
OFX request dosyasını oluşturmaya başlamadan önce dosyanın kaydedileceği çıktı dizinini belirtmemiz gerekiyor.
```csharp
string outputDir = "Your Output Directory";
```
 Yer değiştirmek`"Your Output Directory"` oluşturulan dosyayı kaydetmek istediğiniz dizinin yolu ile birlikte.
## Adım 2: OFX Talep Belgesini Oluşturun
 Daha sonra, örneğinin bir örneğini oluşturmamız gerekiyor.`OfxRequestDocument` sınıf. Bu sınıf OFX isteğimiz için konteyner görevi görecek.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## 3. Adım: Oturum Açma İsteğini Ayarlayın
Oturum açma isteği, kullanıcının kimliğini doğrulamak ve OFX oturumunu başlatmak için gereklidir. Oturum açma isteği mesajını ayarlayacağız ve müşteri tarihi, kullanıcı kimliği, şifre ve finansal kurum bilgileri gibi gerekli ayrıntılarla dolduracağız.
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
## Adım 4: Banka Talep Mesajını Ayarlayın
Artık oturum açma isteği ayarlandığına göre banka istek mesajını oluşturmaya geçeceğiz. Bu mesaj banka hesabının ayrıntılarını ve işlem ekstresi talebini içerecektir.
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
## 5. Adım: İşlem Ayrıntılarını Ekleyin
 Belirli işlemleri almak için tarih aralığını ve işlemlerin isteğe dahil edilip edilmeyeceğini belirtmemiz gerekir. Bu, kurulumun yapılmasıyla yapılır.`IncTransaction` nesne.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Adım 6: OFX Talep Belgesini Kaydedin
Son olarak OFX istek belgesini hem XML hem de SGML formatlarında kaydedeceğiz. Bu, her iki formatı da kullanabilen farklı sistemlerle uyumluluğu sağlar.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Adım 7: Başarılı Yürütmeyi Onaylayın
İşlemin başarıyla yürütüldüğünü doğrulamak için konsola bir mesaj yazdırabiliriz.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Çözüm
Aspose.Finance for .NET kullanarak OFX banka işlemi istek dosyası oluşturmak, bir istek belgesinin ayarlanmasını, oturum açma ve banka istek mesajlarının yapılandırılmasını, işlem ayrıntılarının belirlenmesini ve belgenin kaydedilmesini içeren metodik bir süreçtir. Bu adım adım kılavuzu izleyerek, özel ihtiyaçlarınıza göre uyarlanmış OFX istek dosyalarını verimli bir şekilde oluşturabilirsiniz.
## SSS
### 1. OFX dosyası nedir?
OFX (Açık Finansal Değişim) dosyası, kurumlar ve kullanıcılar arasında finansal veri alışverişi için kullanılan standart bir formattır. Banka hesap özetleri, işlemler ve diğer finansal faaliyetler için yaygın olarak kullanılır.
### 2. Aspose.Finance for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Finance for .NET, C# gibi .NET dilleriyle kullanılmak üzere özel olarak tasarlanmıştır. Ancak .NET destekli herhangi bir ortamda kullanabilirsiniz.
### 3. Aspose.Finance for .NET'in ücretsiz deneme sürümü mevcut mu?
Evet, Aspose.Finance for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### 4. Aspose.Finance for .NET desteğini nasıl alabilirim?
 Aspose topluluğu ve teknik ekibinden destek alabilirsiniz.[destek Forumu](https://forum.aspose.com/c/finance/43).
### 5. Aspose.Finance for .NET için geçici lisans alabilir miyim?
 Evet, Aspose şunları sunuyor:[geçici lisans](https://purchase.aspose.com/temporary-license/) Ürünü değerlendirmek için kullanabilirsiniz.