---
title: Tambahkan Referensi Peran ARC ke Dokumen XBRL
linktitle: Tambahkan Referensi Peran ARC ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara memanipulasi dokumen XBRL secara efisien menggunakan Aspose.Finance untuk .NET. Tambahkan Referensi Peran ARC dengan mudah dengan panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Perkenalan
Dalam dunia pengelolaan dan pelaporan data keuangan, eXtensible Business Reporting Language (XBRL) memainkan peran penting. Ini menstandardisasi cara informasi keuangan dikomunikasikan dan dipertukarkan, memastikan konsistensi, keakuratan, dan efisiensi. Namun, memanipulasi dokumen XBRL, terutama ketika menggabungkan peran dan referensi tertentu, memerlukan pemahaman yang berbeda tentang mekanisme yang mendasarinya. Tutorial ini berfokus pada satu tugas tersebut: menambahkan Referensi Peran ARC ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
### Pengaturan Lingkungan
1.  Instal Aspose.Finance for .NET: Unduh dan instal perpustakaan Aspose.Finance for .NET dari[rilis](https://releases.aspose.com/finance/net/).
   
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan Anda dengan Visual Studio atau IDE pilihan lainnya.
## Impor Namespace
Pastikan untuk mengimpor namespace yang diperlukan dalam kode C# Anda:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Langkah 1: Tentukan Direktori Sumber dan Output
Sebelum melanjutkan, tentukan direktori sumber dan keluaran di mana file XBRL Anda akan ditempatkan dan disimpan.
```csharp
// Direktori sumber
string sourceDir = "Your Source Directory";
// Direktori keluaran
string outputDir = "Your Output Directory";
```
## Langkah 2: Buat Dokumen XBRL
 Buat contoh sebuah`XbrlDocument` objek untuk bekerja dengan data XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Langkah 3: Akses Koleksi XbrlInstance
Akses koleksi instance XBRL dalam dokumen.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Langkah 4: Tambahkan XbrlInstance
Tambahkan instance XBRL baru ke koleksi.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Langkah 5: Tambahkan Referensi Skema
Sertakan referensi skema dalam contoh XBRL, tentukan direktori sumber, awalan namespace, dan URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Langkah 6: Ambil ArcroleType
 Ambil`ArcroleType` berdasarkan URI tertentu.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Langkah 7: Tambahkan ArcroleReference
 Jika`ArcroleType` ditemukan, buatlah`ArcroleReference` dan menambahkannya ke referensi arcrole instance XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Langkah 8: Simpan Dokumen
Simpan dokumen XBRL yang dimodifikasi ke direktori keluaran yang ditentukan.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara menambahkan Referensi Peran ARC ke dokumen XBRL menggunakan Aspose.Finance untuk .NET. Dengan mengikuti petunjuk langkah demi langkah ini dan memanfaatkan kemampuan Aspose.Finance, Anda dapat mengelola dan memanipulasi data XBRL secara efisien untuk memenuhi kebutuhan spesifik Anda.
## FAQ
### Apa itu XBRL?
XBRL adalah singkatan dari eXtensible Business Reporting Language, bahasa standar untuk komunikasi elektronik data bisnis dan keuangan.
### Mengapa XBRL penting?
XBRL memastikan konsistensi, akurasi, dan efisiensi dalam pertukaran dan analisis informasi keuangan, sehingga menguntungkan regulator, analis, dan bisnis.
### Bisakah Aspose.Finance menangani tugas XBRL yang kompleks?
Ya, Aspose.Finance menawarkan fungsionalitas yang kuat untuk bekerja dengan dokumen XBRL, termasuk menangani tugas-tugas kompleks seperti referensi peran dan manajemen taksonomi.
### Apakah Aspose.Finance kompatibel dengan perpustakaan .NET lainnya?
Ya, Aspose.Finance terintegrasi secara mulus dengan perpustakaan .NET lainnya, memberikan dukungan ekstensif untuk manipulasi dan pelaporan data keuangan.
### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Finance?
 Untuk dukungan tambahan, kunjungi[Halaman dukungan Aspose.Finance](https://forum.aspose.com/c/finance/43).