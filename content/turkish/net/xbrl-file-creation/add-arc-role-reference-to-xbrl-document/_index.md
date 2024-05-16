---
title: XBRL Belgesine ARC Rolü Referansı Ekleme
linktitle: XBRL Belgesine ARC Rolü Referansı Ekleme
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET'i kullanarak XBRL belgelerini verimli bir şekilde nasıl yöneteceğinizi öğrenin. Adım adım rehberlikle ARC Rol Referanslarını zahmetsizce ekleyin.
type: docs
weight: 10
url: /tr/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## giriiş
Finansal veri yönetimi ve raporlama dünyasında, Genişletilebilir İşletme Raporlama Dili (XBRL) çok önemli bir rol oynamaktadır. Finansal bilgilerin iletilme ve değiştirilme şeklini standartlaştırarak tutarlılık, doğruluk ve verimlilik sağlar. Bununla birlikte, XBRL belgelerini değiştirmek, özellikle belirli rolleri ve referansları dahil ederken, altta yatan mekanizmaların ayrıntılı bir şekilde anlaşılmasını gerektirir. Bu eğitim böyle bir göreve odaklanıyor: Aspose.Finance for .NET kullanarak bir XBRL belgesine ARC Rol Referansı eklemek.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### Ortam Kurulumu
1.  Aspose.Finance for .NET'i yükleyin: Aspose.Finance for .NET kitaplığını indirip yükleyin.[Salıverme](https://releases.aspose.com/finance/net/).
   
2. Geliştirme Ortamı: Geliştirme ortamınızı Visual Studio veya tercih edilen herhangi bir IDE ile kurun.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# kodunuza aktardığınızdan emin olun:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Adım 1: Kaynak ve Çıkış Dizinlerini Tanımlayın
Devam etmeden önce sırasıyla XBRL dosyalarınızın bulunacağı ve kaydedileceği kaynak ve çıktı dizinlerini belirtin.
```csharp
// Kaynak dizini
string sourceDir = "Your Source Directory";
// Çıkış dizini
string outputDir = "Your Output Directory";
```
## Adım 2: Bir XBRL Belgesi Oluşturun
 Bir örneği oluşturun`XbrlDocument` XBRL verileriyle çalışacak nesne.
```csharp
XbrlDocument document = new XbrlDocument();
```
## 3. Adım: XbrlInstance Koleksiyonuna Erişin
Belgedeki XBRL örnekleri koleksiyonuna erişin.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## 4. Adım: XbrlInstance'ı ekleyin
Koleksiyona yeni bir XBRL örneği ekleyin.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Adım 5: Şema Referansı Ekle
XBRL örneğine kaynak dizini, ad alanı önekini ve URI'yi belirten bir şema referansı ekleyin.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Adım 6: ArcroleType'ı Alın
 Geri al`ArcroleType` belirli bir URI'ye dayalıdır.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Adım 7: ArcroleReference'ı ekleyin
 Eğer`ArcroleType` bulunursa, bir tane oluşturun`ArcroleReference` ve bunu XBRL örneğinin arkrole referanslarına ekleyin.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Adım 8: Belgeyi Kaydedin
Değiştirilen XBRL belgesini belirtilen çıktı dizinine kaydedin.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Çözüm
Bu eğitimde, Aspose.Finance for .NET kullanarak bir XBRL belgesine ARC Rol Referansının nasıl ekleneceğini araştırdık. Bu adım adım talimatları izleyerek ve Aspose.Finance'ın yeteneklerinden yararlanarak, özel gereksinimlerinizi karşılamak için XBRL verilerini verimli bir şekilde yönetebilir ve değiştirebilirsiniz.
## SSS
### XBRL nedir?
XBRL, ticari ve finansal verilerin elektronik iletişimi için standartlaştırılmış bir dil olan eXtensible Business Reporting Language anlamına gelir.
### XBRL neden önemlidir?
XBRL, mali bilgilerin alışverişinde ve analizinde tutarlılık, doğruluk ve verimlilik sağlayarak düzenleyicilere, analistler ve işletmelere fayda sağlar.
### Aspose.Finance karmaşık XBRL görevlerini yerine getirebilir mi?
Evet, Aspose.Finance, XBRL belgeleriyle çalışmak için, rol referansları ve sınıflandırma yönetimi gibi karmaşık görevlerin yerine getirilmesi de dahil olmak üzere güçlü işlevsellik sunar.
### Aspose.Finance diğer .NET kütüphaneleriyle uyumlu mu?
Evet, Aspose.Finance diğer .NET kitaplıklarıyla sorunsuz bir şekilde bütünleşerek finansal veri manipülasyonu ve raporlaması için kapsamlı destek sağlar.
### Aspose.Finance için nereden ek destek bulabilirim?
 Ek destek için şu adresi ziyaret edin:[Aspose.Finance destek sayfası](https://forum.aspose.com/c/finance/43).