---
title: XBRL Belgesine Öğe Ekle
linktitle: XBRL Belgesine Öğe Ekle
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET kullanarak XBRL belgelerine nasıl öğe ekleyeceğinizi öğrenin. .NET uygulamalarınızda finansal raporlamayı basitleştirin. #Aspose #Finans
type: docs
weight: 13
url: /tr/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Genişletilebilir İşletme Raporlama Dili (XBRL), finansal verilerin verimli ve doğru şekilde iletilmesine olanak tanıyan, finansal raporlama için standart bir format haline geldi. Aspose.Finance for .NET, .NET uygulamalarınızda XBRL belgeleriyle çalışmak için güçlü işlevsellik sağlar. Bu eğitimde Aspose.Finance for .NET kullanarak bir XBRL belgesine öğe ekleme adımlarını anlatacağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. Aspose.Finance for .NET'i yükleyin
 Henüz yapmadıysanız Aspose.Finance for .NET'i şu adresten indirip yükleyin:[resmi internet sitesi](https://releases.aspose.com/finance/net/). Kitaplığı .NET ortamınızda kurmak için kurulum talimatlarını izleyin.
### 2. Geliştirme Ortamınızı Kurun
.NET geliştirme için çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun. Sisteminizde yüklü olan .NET çerçevesinin yanı sıra Visual Studio gibi uyumlu bir IDE'ye ihtiyacınız olacak.
## Ad Alanlarını İçe Aktar
Aspose.Finance for .NET tarafından sağlanan işlevsellikten yararlanmak için öncelikle gerekli ad alanlarını .NET uygulamanıza aktarın.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Şimdi örnek kodu birden fazla adıma ayıralım:
## Adım 1: Kaynak ve Çıkış Dizinlerini Tanımlayın
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Yer değiştirmek`"Your Source Directory"` Ve`"Your Output Directory"` sırasıyla kaynak ve çıktı dizinlerinize giden yollarla.
## Adım 2: Bir XBRL Belgesi ve Örneği Oluşturun
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Üzerinde çalışılacak bir XBRL belgesini ve örneğini başlatın.
## 3. Adım: Şema Referansı Ekle
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
XBRL örneğine, şema dosyasının yolunu sağlayarak ve ad alanı ayrıntılarını belirterek bir şema referansı ekleyin.
## Adım 4: Bağlamı ve Varlığı Tanımlayın
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
XBRL örneği için dönem ve varlık ayrıntılarını belirterek bir bağlam ve varlık oluşturun.
## Adım 5: Birim Ekle
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
XBRL örneği için ölçü nitelikli adları belirterek bir birim tanımlayın.
## Adım 6: Öğe Ekle
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
XBRL örneğine kavramını, bağlamını, birimini, kesinliğini ve değerini belirterek bir öğe ekleyin.
## Adım 7: Belgeyi Kaydet
```csharp
document.Save(outputDir + @"document5.xbrl");
```
XBRL belgesini çıktı dizinine kaydedin.
## Çözüm
Bir XBRL belgesine öğe eklemek, mali verilerin doğru bir şekilde temsil edilmesi açısından önemlidir. Aspose.Finance for .NET, .NET uygulamalarındaki XBRL belgeleriyle çalışmak için kapsamlı bir API sağlayarak bu süreci basitleştirir.
## SSS
### Aspose.Finance for .NET'i herhangi bir .NET uygulamasıyla kullanabilir miyim?
Evet, Aspose.Finance for .NET; ASP.NET, WinForms ve Console uygulamaları da dahil olmak üzere tüm .NET uygulamalarıyla uyumludur.
### Aspose.Finance for .NET'in kullanımı ücretsiz mi?
 Aspose.Finance for .NET ticari bir kütüphanedir. Özelliklerini değerlendirmek için ücretsiz deneme sürümünü indirebilir ve lisansları şu adresten satın alabilirsiniz:[Burada](https://purchase.aspose.com/buy).
### Aspose.Finance for .NET, XBRL'nin yanı sıra diğer finansal raporlama formatlarını da destekliyor mu?
Aspose.Finance for .NET öncelikle XBRL ile ilgili işlevselliğe odaklanır. Ancak Aspose, farklı finansal formatlarla çalışmak için başka kütüphaneler de sunuyor.
### Aspose.Finance for .NET için nasıl destek alabilirim?
 Aspose.Finance for .NET için destek alabilirsiniz.[resmi forum](https://forum.aspose.com/c/finance/43)Soru sorabileceğiniz ve diğer kullanıcılarla ve destek personeliyle etkileşimde bulunabileceğiniz yer.
### Aspose.Finance for .NET için geçici bir lisans alabilir miyim?
 Evet, Aspose.Finance for .NET'in geçici lisansları test amaçlı olarak mevcuttur. Bir tane alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).