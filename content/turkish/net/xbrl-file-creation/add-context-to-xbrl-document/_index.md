---
title: XBRL Belgesine Bağlam Ekle
linktitle: XBRL Belgesine Bağlam Ekle
second_title: Aspose.Finance .NET API'si
description: Kolaylaştırılmış finansal raporlama için Aspose.Finance'ı kullanarak .NET'te XBRL belgelerine nasıl içerik ekleyeceğinizi öğrenin. #Aspose #Finans #XBRL
type: docs
weight: 11
url: /tr/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## giriiş
Finansal raporlama alanında XBRL (eXtensible Business Reporting Language), ticari bilgi alışverişinin standartlaştırılmasında önemli bir rol oynar. XBRL belgelerine bağlam eklemek, içerdikleri verilerin bütünlüğünü ve uygunluğunu sağlamak açısından çok önemlidir. Aspose.Finance for .NET ile bu süreç kolaylaştırılmış ve verimli hale geliyor ve geliştiricilerin bağlamı XBRL belgelerine sorunsuz bir şekilde dahil etmelerine olanak tanıyor.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Aspose.Finance for .NET Library: Aspose.Finance for .NET kitaplığını indirip yükleyin.[Salıverme](https://releases.aspose.com/finance/net/).
2. .NET Geliştirme Ortamı: Makinenizde çalışan bir .NET geliştirme ortamının kurulu olduğundan emin olun.
3. Temel C# Anlayışı: C# programlama diline aşinalık, örneklerle birlikte takip edilmesinde faydalı olacaktır.
## Ad Alanlarını İçe Aktar
Aspose.Finance for .NET tarafından sağlanan işlevselliğe erişmek için C# projenize gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Adım 1: Çıkış Dizinini Ayarlayın
XBRL belgesine bağlam eklemeden önce, değiştirilen belgenin kaydedileceği çıktı dizinini belirtin:
```csharp
string outputDir = "Your Output Directory";
```
 Yer değiştirmek`"Your Output Directory"` sisteminizde istediğiniz yolla.
## Adım 2: XBRL Belgesi Oluşturun
 Bir örneği oluşturun`XbrlDocument` XBRL belgeleriyle çalışacak nesne:
```csharp
XbrlDocument document = new XbrlDocument();
```
Bu nesne, işlenecek XBRL belgesini temsil eder.
## 3. Adım: XBRL Örneğini Ekleyin
Belgeye bir XBRL örneği ekleyin. Her örnek belirli bir raporlama dönemine ait verileri içerir:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Bu adım, belge içindeki bir XBRL örneğini başlatır.
## Adım 4: Bağlam Dönemini ve Varlığı Tanımlayın
XBRL örneği için bir bağlam dönemi ve varlık oluşturun:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Raporlama gereksinimlerinize göre dönem ve varlık ayrıntılarını belirtin.
## Adım 5: Bağlam Oluşturun
Önceki adımda tanımlanan dönemi ve varlığı kullanarak bir bağlam oluşturun:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Bu bağlam zamansal ve varlıkla ilgili bilgileri kapsar.
## 6. Adım: XBRL Örneğine Bağlam Ekleyin
Önceki adımda oluşturulan bağlamı XBRL örneğiyle ilişkilendirin:
```csharp
xbrlInstance.Contexts.Add(context);
```
Bu adım, bağlamı XBRL örneğine bağlayarak verilere ilgili bağlamsal bilgileri sağlar.
## Adım 7: Belgeyi Kaydedin
Değiştirilen XBRL belgesini belirtilen çıktı dizinine kaydedin:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Bu, XBRL belgesini eklenen içerikle birlikte kaydederek süreci tamamlar.
## Çözüm
Bu adımları izleyerek Aspose.Finance for .NET'i kullanarak XBRL belgelerine etkili bir şekilde içerik ekleyebilirsiniz. Bu, finansal verilerin netliğini ve kullanılabilirliğini artırarak doğru analiz ve raporlamayı kolaylaştırır.
## SSS
### Aspose.Finance for .NET büyük XBRL belgelerini işleyebilir mi?
Aspose.Finance for .NET, büyük veri kümeleri de dahil olmak üzere çeşitli boyutlardaki XBRL belgelerini işlemek için optimize edilmiştir.
### Aspose.Finance for .NET'in deneme sürümü mevcut mu?
Evet, resmi Aspose web sitesinden ücretsiz deneme sürümünü indirebilirsiniz.
### Aspose.Finance for .NET, XBRL'nin yanı sıra diğer finansal raporlama standartlarını da destekliyor mu?
Aspose.Finance öncelikle XBRL ile ilgili işlevlere odaklanır ancak aynı zamanda diğer finansal formatlar için de destek sağlar.
### Bağlam bilgilerini özel gereksinimlerime göre özelleştirebilir miyim?
Aspose.Finance for .NET kesinlikle bağlam bilgilerini ihtiyaçlarınıza uyacak şekilde özelleştirme esnekliği sunuyor.
### Aspose.Finance for .NET için nerede ek destek veya kaynak bulabilirim?
Topluluktan yardım almak için Aspose.Finance forumunu ziyaret edebilir veya kapsamlı rehberlik için belgeleri inceleyebilirsiniz.