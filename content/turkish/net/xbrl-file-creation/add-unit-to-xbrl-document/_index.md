---
title: XBRL Belgesine Birim Ekle
linktitle: XBRL Belgesine Birim Ekle
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET ile XBRL belgelerine zahmetsizce nasıl birim ekleyeceğinizi öğrenin. Finansal veri işleme yeteneklerinizi bugün geliştirin!
type: docs
weight: 16
url: /tr/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Aspose.Finance for .NET dünyasına hoş geldiniz; .NET uygulamalarında verimli finansal belge manipülasyonuna açılan kapınız. İster muhasebe yazılımı, ister finansal analiz araçları, ister başka bir finansal uygulama geliştiriyor olun, Aspose.Finance for .NET sizi geliştirme sürecinizi kolaylaştıracak kapsamlı özelliklerle donatır.
## Önkoşullar
Aspose.Finance for .NET'in gücünden yararlanmaya başlamadan önce gerekli önkoşulların mevcut olduğundan emin olalım:
### 1. Visual Studio Kurulumu
Sisteminizde Visual Studio'nun kurulu olduğundan emin olun. Değilse, resmi Microsoft web sitesinden indirip yükleyebilirsiniz.
### 2. Lisans Alın
 Aspose.Finance for .NET'in tüm potansiyelini açığa çıkarmak için geçerli bir lisansa ihtiyacınız var. adresinden lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy) veya test amacıyla geçici bir lisans almayı tercih edin.
### 3. Aspose.Finance for .NET'i İndirin ve Referans Alın
 Aspose.Finance for .NET kütüphanesini şu adresten indirin:[sürümler sayfası](https://releases.aspose.com/finance/net/) ve .NET projenizde buna referans verin.
### 4. Belgelere ve Desteğe Erişim
 Bakın[dokümantasyon](https://reference.aspose.com/finance/net/)Aspose.Finance for .NET kullanımına ilişkin ayrıntılı bilgi için. Ayrıca Aspose.Finance topluluğundan şu adreste yardım isteyebilirsiniz:[destek Forumu](https://forum.aspose.com/c/finance/43).
## Ad Alanlarını İçe Aktarma
Şimdi gerekli ad alanlarını .NET projenize aktaralım:
## Adım 1: Aspose.Finance Ad Alanını Ekleyin
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Bu ad alanı, XBRL belgeleri ve verileriyle çalışmak için gerekli olan sınıfları ve yöntemleri içerir.
Aspose.Finance for .NET kullanarak bir XBRL belgesine nasıl birim ekleneceğini anlamak için verilen örneği birden fazla adıma ayıralım.
## Adım 1: Çıkış Dizinini Tanımlayın
```csharp
// Çıkış dizini
string outputDir = "Your Output Directory";
```
 Yer değiştirmek`"Your Output Directory"` İstediğiniz çıktı dizininin gerçek yolu ile.
## Adım 2: Bir XBRL Belgesi Oluşturun
```csharp
XbrlDocument document = new XbrlDocument();
```
Bu, XBRL belgesinin yeni bir örneğini başlatır.
## 3. Adım: XBRL Örneklerine Erişin
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Bu, XBRL örnekleri koleksiyonunu belgeden alır ve ona yeni bir örnek ekler.
## Adım 4: Birim Ekle
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Bu, yeni bir ölçü birimi (bu durumda USD) oluşturur ve onu XBRL örneğine ekler. Para birimi kodunu ve ad alanı URI'sini gerektiği gibi ayarlayabilirsiniz.
## Adım 5: Belgeyi Kaydedin
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Bu, değiştirilen XBRL belgesini belirtilen çıktı dizinine kaydeder.
## Çözüm
Sonuç olarak Aspose.Finance for .NET, geliştiricilerin .NET uygulamaları içindeki finansal belgeleri ve verileri zahmetsizce işlemesine olanak tanıyor. Bu eğitimde özetlenen adımları takip ederek Aspose.Finance for .NET'i projelerinize sorunsuz bir şekilde entegre edebilir ve finansal işlem yeteneklerini geliştirebilirsiniz.
## SSS
### 1. Aspose.Finance for .NET'i lisans olmadan kullanabilir miyim?
Hayır, Aspose.Finance for .NET'in tüm özelliklerinin kilidini açmak için geçerli bir lisans gereklidir. Ancak test amaçlı geçici lisanslar mevcuttur.
### 2. Aspose.Finance for .NET muhasebe yazılımı oluşturmaya uygun mudur?
Evet, Aspose.Finance for .NET, muhasebe yazılımı ve ilgili finansal uygulamalar oluşturmaya yönelik güçlü işlevler sağlar.
### 3. Aspose.Finance for .NET desteğini nerede bulabilirim?
Destek forumunda Aspose.Finance topluluğundan yardım isteyebilirsiniz.
### 4. Bir XBRL belgesindeki ölçü birimini özelleştirebilir miyim?
Evet, Aspose.Finance for .NET'i kullanarak özel ölçü birimleri oluşturabilir ve XBRL belgelerine ekleyebilirsiniz.
### 5. Aspose.Finance for .NET birden fazla para birimini destekliyor mu?
Evet, Aspose.Finance for .NET birden fazla para birimini destekleyerek çok yönlü finansal veri işleme olanağı sağlar.