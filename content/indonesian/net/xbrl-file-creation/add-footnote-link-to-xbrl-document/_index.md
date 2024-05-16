---
title: Tambahkan Tautan Catatan Kaki ke Dokumen XBRL
linktitle: Tambahkan Tautan Catatan Kaki ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara menambahkan tautan catatan kaki ke dokumen XBRL menggunakan Aspose.Finance untuk .NET. Sempurnakan laporan keuangan dengan konteks tambahan dengan mudah.
type: docs
weight: 12
url: /id/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Menambahkan link catatan kaki ke dokumen XBRL sangat penting untuk memberikan konteks tambahan atau penjelasan untuk poin data tertentu. Dalam tutorial ini, kita akan menjalani proses langkah demi langkah menggunakan Aspose.Finance untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Finance for .NET: Pastikan Anda telah menginstal Aspose.Finance for .NET di sistem Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/finance/net/).
  
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan dengan .NET Framework atau .NET Core.
## Impor Namespace:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Langkah 1: Tetapkan Direktori Sumber dan Output
Pertama, tentukan direktori untuk file sumber dan output:
```csharp
// Direktori sumber
string sourceDir = "Your Source Directory";
// Direktori keluaran
string outputDir = "Your Output Directory";
```
## Langkah 2: Buat Dokumen dan Instance XBRL
Inisialisasi dokumen dan instance XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Langkah 3: Tambahkan Referensi Skema
Tambahkan referensi skema ke instance XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Langkah 4: Tentukan Konteks
Tentukan konteks untuk instance XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Langkah 5: Tambahkan Tautan Catatan Kaki
Buat dan tambahkan tautan catatan kaki ke instance XBRL:
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
## Langkah 6: Simpan Dokumen
Simpan dokumen XBRL yang dimodifikasi:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Kesimpulan
Menambahkan tautan catatan kaki ke dokumen XBRL adalah proses yang mudah dengan Aspose.Finance untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah memasukkan konteks atau penjelasan tambahan ke dalam laporan keuangan Anda.
## FAQ
### Bisakah saya menambahkan beberapa tautan catatan kaki ke satu dokumen XBRL?
Ya, Anda dapat menambahkan beberapa tautan catatan kaki dengan mengulangi langkah-langkah yang diuraikan dalam tutorial ini untuk setiap tautan tambahan.
### Apakah Aspose.Finance for .NET kompatibel dengan .NET Framework dan .NET Core?
Ya, Aspose.Finance untuk .NET mendukung lingkungan .NET Framework dan .NET Core.
### Bagaimana saya bisa mendapatkan lisensi sementara Aspose.Finance untuk .NET?
 Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### Apakah Aspose.Finance for .NET menyediakan dukungan untuk validasi XBRL?
Ya, Aspose.Finance for .NET menawarkan dukungan komprehensif untuk validasi XBRL guna memastikan kepatuhan terhadap standar industri.
### Di mana saya dapat menemukan sumber daya tambahan dan dukungan untuk Aspose.Finance untuk .NET?
 Anda dapat mengunjungi[Aspose.Finance untuk forum .NET](https://forum.aspose.com/c/finance/43) untuk dukungan dan mengakses dokumentasi[Di Sini](https://reference.aspose.com/finance/net/).