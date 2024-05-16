---
title: Tambahkan Item ke Dokumen XBRL
linktitle: Tambahkan Item ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara menambahkan item ke dokumen XBRL menggunakan Aspose.Finance untuk .NET. Sederhanakan pelaporan keuangan di aplikasi .NET Anda. #Aspose #Keuangan
type: docs
weight: 13
url: /id/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) telah menjadi format standar pelaporan keuangan, memungkinkan komunikasi data keuangan yang efisien dan akurat. Aspose.Finance for .NET menyediakan fungsionalitas yang kuat untuk bekerja dengan dokumen XBRL di aplikasi .NET Anda. Dalam tutorial ini, kita akan memandu langkah-langkah untuk menambahkan item ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
### 1. Instal Aspose.Finance untuk .NET
 Jika Anda belum melakukannya, unduh dan instal Aspose.Finance untuk .NET dari[situs web resmi](https://releases.aspose.com/finance/net/). Ikuti petunjuk instalasi untuk menyiapkan perpustakaan di lingkungan .NET Anda.
### 2. Siapkan Lingkungan Pengembangan Anda
Pastikan Anda memiliki lingkungan pengembangan yang berfungsi untuk pengembangan .NET. Anda memerlukan IDE yang kompatibel seperti Visual Studio, bersama dengan kerangka .NET yang diinstal pada sistem Anda.
## Impor Namespace
Pertama, impor namespace yang diperlukan ke aplikasi .NET Anda untuk memanfaatkan fungsionalitas yang disediakan oleh Aspose.Finance untuk .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Sekarang mari kita pecahkan kode contoh menjadi beberapa langkah:
## Langkah 1: Tentukan Direktori Sumber dan Output
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Mengganti`"Your Source Directory"` Dan`"Your Output Directory"` dengan masing-masing jalur ke direktori sumber dan keluaran Anda.
## Langkah 2: Buat Dokumen dan Instance XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inisialisasi dokumen dan instance XBRL yang akan digunakan.
## Langkah 3: Tambahkan Referensi Skema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Tambahkan referensi skema ke instance XBRL, berikan jalur ke file skema dan tentukan detail namespace.
## Langkah 4: Tentukan Konteks dan Entitas
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Buat konteks dan entitas untuk instans XBRL, tentukan periode dan detail entitas.
## Langkah 5: Tambahkan Unit
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Tentukan unit untuk instance XBRL, tentukan nama ukuran yang memenuhi syarat.
## Langkah 6: Tambahkan Barang
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
Tambahkan item ke instance XBRL, tentukan konsep, konteks, unit, presisi, dan nilainya.
## Langkah 7: Simpan Dokumen
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Simpan dokumen XBRL ke direktori keluaran.
## Kesimpulan
Menambahkan item ke dokumen XBRL sangat penting untuk merepresentasikan data keuangan secara akurat. Aspose.Finance for .NET menyederhanakan proses ini dengan menyediakan API komprehensif untuk bekerja dengan dokumen XBRL di aplikasi .NET.
## FAQ
### Bisakah saya menggunakan Aspose.Finance untuk .NET dengan aplikasi .NET apa pun?
Ya, Aspose.Finance untuk .NET kompatibel dengan aplikasi .NET apa pun, termasuk aplikasi ASP.NET, WinForms, dan Konsol.
### Apakah Aspose.Finance untuk .NET gratis untuk digunakan?
 Aspose.Finance untuk .NET adalah perpustakaan komersial. Anda dapat mengunduh versi uji coba gratis untuk mengevaluasi fitur-fiturnya, dan lisensinya dapat dibeli[Di Sini](https://purchase.aspose.com/buy).
### Apakah Aspose.Finance for .NET mendukung format pelaporan keuangan lain selain XBRL?
Aspose.Finance untuk .NET terutama berfokus pada fungsionalitas terkait XBRL. Namun, Aspose menawarkan perpustakaan lain untuk bekerja dengan format keuangan yang berbeda.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Finance untuk .NET?
 Anda bisa mendapatkan dukungan untuk Aspose.Finance untuk .NET melalui[forum resmi](https://forum.aspose.com/c/finance/43)tempat Anda dapat mengajukan pertanyaan dan berinteraksi dengan pengguna lain serta staf pendukung.
### Bisakah saya mendapatkan lisensi sementara Aspose.Finance untuk .NET?
 Ya, lisensi sementara untuk Aspose.Finance untuk .NET tersedia untuk tujuan pengujian. Anda bisa mendapatkannya[Di Sini](https://purchase.aspose.com/temporary-license/).