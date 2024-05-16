---
title: XBRL Belgesine Rol Referansı Ekleme
linktitle: XBRL Belgesine Rol Referansı Ekleme
second_title: Aspose.Finance .NET API'si
description: Aspose.Finance for .NET kullanarak XBRL belgelerine nasıl rol referansları ekleyeceğinizi öğrenin. Bu öğreticiyle .NET uygulamalarınızdaki finansal raporlamayı basitleştirin.
type: docs
weight: 14
url: /tr/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language), özellikle finansal raporlamada ticari bilgi alışverişinde bir standart haline geldi. Aspose.Finance for .NET, .NET uygulamalarında XBRL belgeleriyle çalışmayı kolaylaştırır. Bu eğitim, Aspose.Finance for .NET kullanarak bir XBRL belgesine rol referansı ekleme sürecinde size rehberlik edecektir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### 1. Aspose.Finance for .NET'i yükleyin
Geliştirme ortamınızda Aspose.Finance for .NET'in kurulu olduğundan emin olun. Henüz yapmadıysanız, şuradan indirin:[Salıverme](https://releases.aspose.com/finance/net/) ve kurulum talimatlarını takip edin.
### 2. Geliştirme Ortamınızı Kurun
.NET geliştirme için çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun. Buna Visual Studio gibi uyumlu bir IDE ve sisteminizde yüklü olan .NET çerçevesi de dahildir.
## Ad Alanlarını İçe Aktar
Aspose.Finance for .NET tarafından sağlanan işlevselliğe erişmek için gerekli ad alanlarını .NET uygulamanıza aktararak başlayın.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## 4. Adım: Rol Türünü Alın ve Rol Referansı Ekleyin
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
URI'sini kullanarak rol türünü alın ve XBRL örneğine bir rol referansı ekleyin.
## Adım 5: Belgeyi Kaydet
```csharp
document.Save(outputDir + @"document7.xbrl");
```
XBRL belgesini çıktı dizinine kaydedin.
## Çözüm
XBRL belgelerine rol referansları eklemek, belge içindeki çeşitli öğelerin rollerini tanımlamak için çok önemlidir. Aspose.Finance for .NET, geliştiricilerin .NET uygulamalarında XBRL belgeleriyle verimli bir şekilde çalışmasına olanak tanıyarak bu görevi gerçekleştirmenin basit bir yolunu sunar.
## SSS
### Aspose.Finance for .NET'i herhangi bir .NET uygulamasıyla kullanabilir miyim?
Evet, Aspose.Finance for .NET; ASP.NET, WinForms ve Console uygulamaları da dahil olmak üzere tüm .NET uygulamalarıyla uyumludur.
### Aspose.Finance for .NET'in kullanımı ücretsiz mi?
 Aspose.Finance for .NET ticari bir kütüphanedir. Özelliklerini değerlendirmek için ücretsiz deneme sürümünü indirebilir ve lisansları şu adresten satın alabilirsiniz:[Burada](https://purchase.aspose.com/buy).
### Aspose.Finance for .NET, XBRL'nin yanı sıra diğer finansal raporlama formatlarını da destekliyor mu?
Aspose.Finance for .NET öncelikle XBRL ile ilgili işlevselliğe odaklanır. Ancak Aspose, farklı finansal formatlarla çalışmak için başka kütüphaneler de sunuyor.
### Aspose.Finance for .NET için nasıl destek alabilirim?
 Aspose.Finance for .NET için destek alabilirsiniz.[forum](https://forum.aspose.com/c/finance/43)Soru sorabileceğiniz ve diğer kullanıcılarla ve destek personeliyle etkileşimde bulunabileceğiniz yer.
### Aspose.Finance for .NET için geçici bir lisans alabilir miyim?
 Evet, Aspose.Finance for .NET'in geçici lisansları test amaçlı olarak mevcuttur. Bir tane alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).