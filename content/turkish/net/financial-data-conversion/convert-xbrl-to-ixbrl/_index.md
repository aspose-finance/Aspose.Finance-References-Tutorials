---
title: XBRL'yi iXBRL'ye Kolayca Dönüştürün
linktitle: XBRL'yi iXBRL'ye dönüştür
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET ile XBRL'yi kolayca iXBRL'ye dönüştürün. Sorunsuz bir geçiş için adım adım kılavuzumuzu izleyin. #Aspose #Finans
type: docs
weight: 10
url: /tr/net/financial-data-conversion/convert-xbrl-to-ixbrl/
---
## Aspose.Finance for .NET'i kullanarak XBRL'yi iXBRL'ye dönüştürün
Günümüzün veri odaklı dünyasında, finans profesyonellerinin, verilerin hem makine tarafından hem de insan tarafından okunabilir olmasını sağlamak için genellikle XBRL (eXtensible Business Reporting Language) dosyalarını iXBRL (Satır İçi XBRL) formatına dönüştürmeleri gerekir. Bunu başarmak için sağlam bir çözüm arıyorsanız Aspose.Finance for .NET mükemmel bir seçimdir. Bu kılavuz, ortamınızı ayarlamaktan dosyalarınızı başarılı bir şekilde dönüştürmeye kadar süreç boyunca size adım adım yol gösterecektir.
## Önkoşullar
Dönüşüm sürecine dalmadan önce neye ihtiyacınız olduğunu gözden geçirelim:
1. Temel .NET Bilgisi: C# ve .NET çerçevesine aşinalık çok önemlidir.
2. Aspose.Finance for .NET: Aspose.Finance for .NET kitaplığını indirip yüklemeniz gerekecek.
3. XBRL Dosyaları: Dönüştürmeyi düşündüğünüz XBRL dosyalarına sahip olduğunuzdan emin olun.
4. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı.
## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını projenize aktarmanız gerekir. Bu, Aspose.Finance tarafından sağlanan işlevlere erişmenizi sağlar.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## 1. Adım: Çalışma Dizinlerini Ayarlayın
Öncelikle kaynak XBRL dosyalarınız ve çıktı iXBRL dosyalarınız için dizinleri belirtmeniz gerekir.
```csharp
// Çalışma dizinleri
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
## Adım 2: XBRL Belgesini Yükleyin
 Daha sonra XBRL belgenizi aşağıdaki komutu kullanarak yükleyeceksiniz:`XbrlDocument` Aspose.Finance tarafından sağlanan sınıf.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
 Bu kod satırı yeni bir örneğini başlatır.`XbrlDocument` sınıf ve belirtilen XBRL dosyasını yükler.
## 3. Adım: Kaydetme Seçeneklerini Ayarlayın
Belgeyi farklı bir formata dönüştürmek için kaydetme seçeneklerini ayarlamanız gerekir. Bu eğitim için dosyayı iXBRL formatında kaydedeceğiz.
```csharp
SaveOptions saveOptions = new SaveOptions();
saveOptions.SaveFormat = SaveFormat.iXBRL;
```
 Burada,`SaveOptions` Belgeyi kaydetmek istediğiniz biçimi belirtmek için kullanılır.
## Adım 4: Dosyayı Kaydedin
Artık her şey ayarlandığına göre XBRL belgesini iXBRL dosyası olarak kaydedebilirsiniz.
```csharp
document.Save(outputDir + @"ConvertXbrlToiXbrl_out.ixbrl", saveOptions);
```
Bu komut, dönüştürülen dosyayı belirtilen çıktı dizinine kaydeder.
## Adım 5: Dönüşümü Onaylayın
Son olarak, bir başarı mesajı görüntüleyerek dönüşümü onaylayabilirsiniz.
```csharp
Console.WriteLine("ConvertXbrlToiXbrl executed successfully.");
```
## Çözüm
Tebrikler! Aspose.Finance for .NET'i kullanarak bir XBRL dosyasını başarıyla iXBRL'ye dönüştürdünüz. Bu güçlü kitaplık, dönüştürme sürecini basitleştirerek farklı finansal raporlama formatları arasında sorunsuz geçişlere olanak tanır. İster geliştirici ister finans uzmanı olun, bu araca hakim olmak hiç şüphesiz üretkenliğinizi ve verimliliğinizi artıracaktır.
## SSS
### 1. Aspose.Finance for .NET nedir?
Aspose.Finance for .NET, XBRL, iXBRL ve OFX gibi finansal formatları yönetmek için kapsamlı bir kütüphanedir. Geliştiricilerin finansal belgeleri programlı olarak oluşturmasına, okumasına ve değiştirmesine olanak tanır.
### 2. Satın almadan önce Aspose.Finance for .NET'i deneyebilir miyim?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Aspose sürümler sayfası](https://releases.aspose.com/finance/net/).
### 3. Aspose.Finance for .NET desteğini nasıl alabilirim?
 Ziyaret edebilirsiniz[Aspose.Finance destek forumu](https://forum.aspose.com/c/finance/43) Karşılaştığınız herhangi bir sorunla ilgili yardım için.
### 4. Aspose.Finance for .NET'in ana özellikleri nelerdir?
Aspose.Finance for .NET, çeşitli finansal formatları oluşturma, okuma ve dönüştürme yeteneği, kapsamlı API yetenekleri ve güçlü hata yönetimi gibi çok çeşitli özellikler sunar.
### 5. Ayrıntılı belgeleri nerede bulabilirim?
 Ayrıntılı belgeler şu adreste mevcuttur:[Aspose.Finance dokümantasyon sayfası](https://reference.aspose.com/finance/net/).