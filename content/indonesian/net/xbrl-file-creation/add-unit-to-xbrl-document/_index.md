---
title: Tambahkan Unit ke Dokumen XBRL
linktitle: Tambahkan Unit ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara menambahkan unit ke dokumen XBRL dengan mudah menggunakan Aspose.Finance untuk .NET. Tingkatkan kemampuan pemrosesan data keuangan Anda hari ini!
type: docs
weight: 16
url: /id/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Selamat datang di dunia Aspose.Finance untuk .NET - gerbang Anda menuju manipulasi dokumen keuangan yang efisien dalam aplikasi .NET. Baik Anda membuat perangkat lunak akuntansi, alat analisis keuangan, atau aplikasi keuangan lainnya, Aspose.Finance for .NET membekali Anda dengan serangkaian fitur komprehensif untuk menyederhanakan proses pengembangan Anda.
## Prasyarat
Sebelum kita mendalami pemanfaatan kekuatan Aspose.Finance untuk .NET, pastikan kita memiliki prasyarat yang diperlukan:
### 1. Instalasi Visual Studio
Pastikan Anda telah menginstal Visual Studio di sistem Anda. Jika belum, Anda dapat mengunduh dan menginstalnya dari situs resmi Microsoft.
### 2. Dapatkan Lisensi
 Untuk membuka potensi penuh Aspose.Finance untuk .NET, Anda memerlukan lisensi yang valid. Anda dapat membeli lisensi dari[Di Sini](https://purchase.aspose.com/buy) atau memilih lisensi sementara untuk tujuan pengujian.
### 3. Unduh dan Referensi Aspose.Finance untuk .NET
 Unduh perpustakaan Aspose.Finance untuk .NET dari[halaman rilis](https://releases.aspose.com/finance/net/) dan referensikan di proyek .NET Anda.
### 4. Akses Dokumentasi dan Dukungan
 Mengacu kepada[dokumentasi](https://reference.aspose.com/finance/net/)untuk informasi detail tentang penggunaan Aspose.Finance untuk .NET. Selain itu, Anda dapat mencari bantuan dari komunitas Aspose.Finance di[forum dukungan](https://forum.aspose.com/c/finance/43).
## Mengimpor Namespace
Sekarang, mari impor namespace yang diperlukan ke proyek .NET Anda:
## Langkah 1: Tambahkan Namespace Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Namespace ini berisi kelas dan metode yang penting untuk bekerja dengan dokumen dan data XBRL.
Mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk memahami cara menambahkan unit ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
## Langkah 1: Tentukan Direktori Output
```csharp
// Direktori keluaran
string outputDir = "Your Output Directory";
```
 Mengganti`"Your Output Directory"` dengan jalur sebenarnya ke direktori keluaran yang Anda inginkan.
## Langkah 2: Buat Dokumen XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Ini menginisialisasi contoh baru dari dokumen XBRL.
## Langkah 3: Akses Instans XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ini mengambil koleksi instance XBRL dari dokumen dan menambahkan instance baru ke dalamnya.
## Langkah 4: Tambahkan Unit
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Ini menciptakan satuan ukuran baru (dalam hal ini, USD) dan menambahkannya ke instance XBRL. Anda dapat menyesuaikan kode mata uang dan URI namespace sesuai kebutuhan.
## Langkah 5: Simpan Dokumen
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Ini menyimpan dokumen XBRL yang dimodifikasi ke direktori keluaran yang ditentukan.
## Kesimpulan
Kesimpulannya, Aspose.Finance for .NET memberdayakan pengembang untuk dengan mudah memanipulasi dokumen dan data keuangan dalam aplikasi .NET mereka. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan Aspose.Finance untuk .NET ke dalam proyek Anda dan meningkatkan kemampuan pemrosesan keuangannya.
## FAQ
### 1. Bisakah saya menggunakan Aspose.Finance untuk .NET tanpa lisensi?
Tidak, lisensi yang valid diperlukan untuk membuka fitur lengkap Aspose.Finance untuk .NET. Namun, lisensi sementara tersedia untuk tujuan pengujian.
### 2. Apakah Aspose.Finance for .NET cocok untuk membangun perangkat lunak akuntansi?
Ya, Aspose.Finance untuk .NET menyediakan fungsionalitas tangguh yang disesuaikan untuk membangun perangkat lunak akuntansi dan aplikasi keuangan terkait.
### 3. Di mana saya dapat menemukan dukungan untuk Aspose.Finance untuk .NET?
Anda dapat mencari bantuan dari komunitas Aspose.Finance di forum dukungan.
### 4. Bisakah saya menyesuaikan satuan ukuran dalam dokumen XBRL?
Ya, Anda dapat membuat dan menambahkan satuan ukuran khusus ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
### 5. Apakah Aspose.Finance untuk .NET mendukung banyak mata uang?
Ya, Aspose.Finance untuk .NET mendukung banyak mata uang, memungkinkan pemrosesan data keuangan serbaguna.