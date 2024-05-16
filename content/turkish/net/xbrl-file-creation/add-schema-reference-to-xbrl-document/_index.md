---
title: XBRL Belgesine Şema Referansı Ekleme
linktitle: XBRL Belgesine Şema Referansı Ekleme
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET kullanarak XBRL belgelerine şema referanslarının nasıl ekleneceğini öğrenin. Finansal veri işleme sürecinizi bugün kolaylaştırın!
type: docs
weight: 15
url: /tr/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Aspose.Finance for .NET ile tanışın
Aspose.Finance for .NET, .NET uygulamaları içindeki finansal belge ve verilerin işlenmesi ve işlenmesi için kapsamlı işlevler sağlayan güçlü bir kütüphanedir. İster muhasebe yazılımı, ister finansal analiz araçları, ister başka bir finansal uygulama geliştiriyor olun, Aspose.Finance for .NET, geliştirme sürecinizi kolaylaştırmak için çok çeşitli özellikler sunar.
## Önkoşullar
Aspose.Finance for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### 1. Visual Studio'yu yükleyin
Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Resmi Microsoft web sitesinden indirip yükleyebilirsiniz.
### 2. Aspose.Finance Lisansı Alın
Aspose.Finance for .NET'in tüm özelliklerinden yararlanmak için geçerli bir lisans almanız gerekir. adresinden lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy) veya test amacıyla geçici bir lisans almayı tercih edin.
### 3. Aspose.Finance for .NET'i İndirin ve Referans Alın
 Aspose.Finance for .NET kütüphanesini şu adresten indirin:[sürümler sayfası](https://releases.aspose.com/finance/net/) ve .NET projenizde buna referans verin.
### 4. Belgelere ve Desteğe Erişim
 Bakın[API belgeleri](https://reference.aspose.com/finance/net/) Aspose.Finance for .NET kullanımı hakkında ayrıntılı bilgi için. Ayrıca Aspose.Finance topluluğundan şu adreste yardım isteyebilirsiniz:[destek Forumu](https://forum.aspose.com/c/finance/43).
## Ad Alanlarını İçe Aktarma
Gerekli ad alanlarını .NET projenize aktararak başlayalım:
## Adım 1: Aspose.Finance Ad Alanını Ekleyin
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Bu ad alanı, XBRL belgeleri ve verileriyle çalışmaya yönelik sınıfları ve yöntemleri içerir.
Şimdi Aspose.Finance for .NET kullanarak bir XBRL belgesine şema referansının nasıl ekleneceğini anlamak için sağlanan örneği birden fazla adıma ayıralım.
## Adım 1: Kaynak ve Çıkış Dizinlerini Tanımlayın
```csharp
// Kaynak dizini
string sourceDir = "Your Source Directory";
// Çıkış dizini
string outputDir = "Your Output Directory";
```
 Yer değiştirmek`"Your Source Directory"` Ve`"Your Output Directory"`sırasıyla kaynak ve çıktı dizinlerinize giden gerçek yollarla.
## Adım 2: Bir XBRL Belgesi Oluşturun
```csharp
XbrlDocument document = new XbrlDocument();
```
Bu, XBRL belgesinin yeni bir örneğini oluşturur.
## 3. Adım: XBRL Örneklerine Erişin
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Bu, XBRL örnekleri koleksiyonunu belgeden alır ve ona yeni bir örnek ekler.
## Adım 4: Şema Referansı Ekle
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
 Bu, XBRL örneğine bir şema referansı ekler. Yer değiştirmek`"schema.xsd"` şema dosyanızın gerçek adıyla birlikte,`"example"` uygun bir önekle ve`"http://example.com/xbrl/taxonomy"` hedef ad alanı URI'si ile.
## Adım 5: Belgeyi Kaydedin
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Bu, değiştirilen XBRL belgesini belirtilen çıktı dizinine kaydeder.
## Çözüm
Sonuç olarak Aspose.Finance for .NET, .NET uygulamalarındaki finansal belge ve verilerin işlenmesi için güçlü bir çözüm sunuyor. Bu eğitimde özetlenen adımları takip ederek Aspose.Finance'ı projelerinize kolayca entegre edebilir ve XBRL belgelerini verimli bir şekilde yönetebilirsiniz.
## SSS
 (Sıkça Sorulan Sorular)
### 1. Aspose.Finance for .NET'i lisans olmadan kullanabilir miyim?
Hayır, Aspose.Finance for .NET'in tüm özelliklerinden yararlanmak için geçerli bir lisansa ihtiyacınız var. Ancak test amaçlı olarak geçici bir lisans alabilirsiniz.
### 2. Aspose.Finance muhasebe yazılımı oluşturmaya uygun mudur?
Evet, Aspose.Finance, finansal verilerin işlenmesi için kapsamlı işlevler sunarak onu muhasebe yazılımı ve ilgili uygulamalar oluşturmak için ideal kılar.
### 3. Aspose.Finance için nereden destek bulabilirim?
Resmi destek forumunda Aspose.Finance topluluğundan yardım alabilirsiniz.
### 4. Şema referans önekini özelleştirebilir miyim?
Evet, Aspose.Finance for .NET kullanarak bir XBRL belgesine şema referansı eklerken uygun bir önek seçebilirsiniz.
### 5. Aspose.Finance, XBRL'nin yanı sıra diğer finansal formatları da destekliyor mu?
Evet, Aspose.Finance çeşitli finansal formatları ve standartları destekleyerek çeşitli finansal uygulamalara kusursuz entegrasyon sağlar.