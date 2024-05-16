---
title: XBRL Belgesine Dipnot Bağlantısı Ekleme
linktitle: XBRL Belgesine Dipnot Bağlantısı Ekleme
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET kullanarak XBRL belgelerine dipnot bağlantılarının nasıl ekleneceğini öğrenin. Finansal raporları ek bağlamla zahmetsizce geliştirin.
type: docs
weight: 12
url: /tr/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Bir XBRL belgesine dipnot bağlantısı eklemek, belirli veri noktalarına yönelik ek bağlam veya açıklamalar sağlamak açısından çok önemlidir. Bu eğitimde Aspose.Finance for .NET'i kullanarak süreci adım adım anlatacağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.Finance for .NET: Aspose.Finance for .NET'i sisteminize yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/finance/net/).
  
2. Geliştirme Ortamı: .NET Framework veya .NET Core ile ayarlanmış bir geliştirme ortamına sahip olun.
## Ad Alanlarını İçe Aktar:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Adım 1: Kaynak ve Çıkış Dizinlerini Ayarlayın
İlk olarak kaynak ve çıktı dosyalarının dizinlerini belirtin:
```csharp
// Kaynak dizini
string sourceDir = "Your Source Directory";
// Çıkış dizini
string outputDir = "Your Output Directory";
```
## Adım 2: Bir XBRL Belgesi ve Örneği Oluşturun
Bir XBRL belgesini ve örneğini başlatın:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 3. Adım: Şema Referansları Ekleme
XBRL örneğine şema referansları ekleyin:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Adım 4: Bağlamı Tanımlayın
XBRL örneğinin içeriğini tanımlayın:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## 5. Adım: Dipnot Bağlantısı Ekleyin
XBRL örneğine bir dipnot bağlantısı oluşturun ve ekleyin:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## Adım 6: Belgeyi Kaydedin
Değiştirilen XBRL belgesini kaydedin:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Çözüm
Aspose.Finance for .NET ile XBRL belgesine dipnot bağlantısı eklemek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, mali raporlarınıza ek bağlam veya açıklamaları sorunsuz bir şekilde dahil edebilirsiniz.
## SSS
### Tek bir XBRL belgesine birden fazla dipnot bağlantısı ekleyebilir miyim?
Evet, her ek bağlantı için bu eğitimde özetlenen adımları tekrarlayarak birden fazla dipnot bağlantısı ekleyebilirsiniz.
### Aspose.Finance for .NET hem .NET Framework hem de .NET Core ile uyumlu mu?
Evet, Aspose.Finance for .NET hem .NET Framework hem de .NET Core ortamlarını destekler.
### Aspose.Finance for .NET için nasıl geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance for .NET XBRL doğrulama desteği sağlıyor mu?
Evet, Aspose.Finance for .NET, endüstri standartlarına uygunluğu sağlamak amacıyla XBRL doğrulaması için kapsamlı destek sunuyor.
### Aspose.Finance for .NET için ek kaynakları ve desteği nerede bulabilirim?
 Ziyaret edebilirsiniz[Aspose.Finance for .NET forumu](https://forum.aspose.com/c/finance/43) destek ve erişim belgeleri için[Burada](https://reference.aspose.com/finance/net/).