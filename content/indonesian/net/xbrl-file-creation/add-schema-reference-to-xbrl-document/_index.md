---
title: Tambahkan Referensi Skema ke Dokumen XBRL
linktitle: Tambahkan Referensi Skema ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara menambahkan referensi skema ke dokumen XBRL menggunakan Aspose.Finance untuk .NET. Sederhanakan pemrosesan data keuangan Anda hari ini!
type: docs
weight: 15
url: /id/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Memperkenalkan Aspose.Finance untuk .NET
Aspose.Finance for .NET adalah perpustakaan canggih yang menyediakan fungsionalitas komprehensif untuk memproses dan memanipulasi dokumen dan data keuangan dalam aplikasi .NET. Baik Anda membuat perangkat lunak akuntansi, alat analisis keuangan, atau aplikasi keuangan lainnya, Aspose.Finance for .NET menawarkan beragam fitur untuk menyederhanakan proses pengembangan Anda.
## Prasyarat
Sebelum mulai menggunakan Aspose.Finance untuk .NET, pastikan Anda telah menyiapkan prasyarat berikut:
### 1. Instal Visual Studio
Pastikan Anda telah menginstal Visual Studio di sistem Anda. Anda dapat mengunduh dan menginstalnya dari situs resmi Microsoft.
### 2. Dapatkan Lisensi Aspose.Finance
Untuk memanfaatkan kemampuan penuh Aspose.Finance untuk .NET, Anda perlu memperoleh lisensi yang valid. Anda dapat membeli lisensi dari[Di Sini](https://purchase.aspose.com/buy) atau memilih lisensi sementara untuk tujuan pengujian.
### 3. Unduh dan Referensi Aspose.Finance untuk .NET
 Unduh perpustakaan Aspose.Finance untuk .NET dari[halaman rilis](https://releases.aspose.com/finance/net/) dan referensikan di proyek .NET Anda.
### 4. Akses Dokumentasi dan Dukungan
 Mengacu kepada[dokumentasi API](https://reference.aspose.com/finance/net/) untuk informasi mendetail tentang penggunaan Aspose.Finance untuk .NET. Selain itu, Anda dapat mencari bantuan dari komunitas Aspose.Finance di[forum dukungan](https://forum.aspose.com/c/finance/43).
## Mengimpor Namespace
Mari kita mulai dengan mengimpor namespace yang diperlukan ke proyek .NET Anda:
## Langkah 1: Tambahkan Namespace Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Namespace ini berisi kelas dan metode untuk bekerja dengan dokumen dan data XBRL.
Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk memahami cara menambahkan referensi skema ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
## Langkah 1: Tentukan Direktori Sumber dan Output
```csharp
// Direktori sumber
string sourceDir = "Your Source Directory";
// Direktori keluaran
string outputDir = "Your Output Directory";
```
 Mengganti`"Your Source Directory"` Dan`"Your Output Directory"`dengan jalur sebenarnya ke direktori sumber dan keluaran Anda masing-masing.
## Langkah 2: Buat Dokumen XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Ini menciptakan sebuah instance baru dari dokumen XBRL.
## Langkah 3: Akses Instans XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ini mengambil koleksi instance XBRL dari dokumen dan menambahkan instance baru ke dalamnya.
## Langkah 4: Tambahkan Referensi Skema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
 Ini menambahkan referensi skema ke instance XBRL. Mengganti`"schema.xsd"` dengan nama sebenarnya dari file skema Anda,`"example"` dengan awalan yang sesuai, dan`"http://example.com/xbrl/taxonomy"` dengan URI namespace target.
## Langkah 5: Simpan Dokumen
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Ini menyimpan dokumen XBRL yang dimodifikasi ke direktori keluaran yang ditentukan.
## Kesimpulan
Kesimpulannya, Aspose.Finance untuk .NET menawarkan solusi tangguh untuk menangani dokumen dan data keuangan dalam aplikasi .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan Aspose.Finance ke dalam proyek Anda dan memanipulasi dokumen XBRL secara efisien.
## FAQ
 (Pertanyaan yang Sering Diajukan)
### 1. Bisakah saya menggunakan Aspose.Finance untuk .NET tanpa lisensi?
Tidak, Anda memerlukan lisensi yang valid untuk memanfaatkan fitur lengkap Aspose.Finance untuk .NET. Namun, Anda bisa mendapatkan lisensi sementara untuk tujuan pengujian.
### 2. Apakah Aspose.Finance cocok untuk membangun software akuntansi?
Ya, Aspose.Finance menyediakan fungsionalitas komprehensif untuk memproses data keuangan, sehingga ideal untuk membangun perangkat lunak akuntansi dan aplikasi terkait.
### 3. Di mana saya dapat menemukan dukungan untuk Aspose.Finance?
Anda dapat mencari bantuan dari komunitas Aspose.Finance di forum dukungan resmi.
### 4. Dapatkah saya menyesuaikan awalan referensi skema?
Ya, Anda dapat memilih awalan yang sesuai saat menambahkan referensi skema ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
### 5. Apakah Aspose.Finance mendukung format keuangan lain selain XBRL?
Ya, Aspose.Finance mendukung berbagai format dan standar keuangan, memungkinkan integrasi tanpa hambatan ke dalam beragam aplikasi keuangan.