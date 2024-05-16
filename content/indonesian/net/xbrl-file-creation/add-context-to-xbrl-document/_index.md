---
title: Tambahkan Konteks ke Dokumen XBRL
linktitle: Tambahkan Konteks ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara menambahkan konteks ke dokumen XBRL di .NET menggunakan Aspose.Finance untuk pelaporan keuangan yang efisien. #Aspose #Keuangan #XBRL
type: docs
weight: 11
url: /id/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Perkenalan
Dalam bidang pelaporan keuangan, XBRL (eXtensible Business Reporting Language) memainkan peran penting dalam standarisasi pertukaran informasi bisnis. Menambahkan konteks ke dokumen XBRL sangat penting untuk memastikan integritas dan relevansi data yang dikandungnya. Dengan Aspose.Finance untuk .NET, proses ini menjadi efisien dan efisien, memungkinkan pengembang memasukkan konteks ke dalam dokumen XBRL mereka dengan lancar.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Aspose.Finance for .NET Library: Unduh dan instal perpustakaan Aspose.Finance for .NET dari[rilis](https://releases.aspose.com/finance/net/).
2. Lingkungan Pengembangan .NET: Pastikan Anda memiliki lingkungan pengembangan .NET yang berfungsi di mesin Anda.
3. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# akan sangat membantu dalam mengikuti contoh.
## Impor Namespace
Dalam proyek C# Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh Aspose.Finance untuk .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Langkah 1: Tetapkan Direktori Output
Sebelum menambahkan konteks ke dokumen XBRL, tentukan direktori keluaran tempat dokumen yang dimodifikasi akan disimpan:
```csharp
string outputDir = "Your Output Directory";
```
 Mengganti`"Your Output Directory"` dengan jalur yang diinginkan di sistem Anda.
## Langkah 2: Buat Dokumen XBRL
 Buat contoh sebuah`XbrlDocument` keberatan untuk bekerja dengan dokumen XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
Objek ini mewakili dokumen XBRL yang akan dimanipulasi.
## Langkah 3: Tambahkan Instans XBRL
Tambahkan instance XBRL ke dokumen. Setiap instance berisi data untuk periode pelaporan tertentu:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Langkah ini menginisialisasi instance XBRL dalam dokumen.
## Langkah 4: Tentukan Periode Konteks dan Entitas
Buat periode konteks dan entitas untuk instance XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Tentukan periode dan rincian entitas sesuai dengan kebutuhan pelaporan Anda.
## Langkah 5: Buat Konteks
Buatlah konteks menggunakan periode dan entitas yang ditentukan pada langkah sebelumnya:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Konteks ini merangkum informasi temporal dan terkait entitas.
## Langkah 6: Tambahkan Konteks ke Instans XBRL
Kaitkan konteks yang dibuat pada langkah sebelumnya dengan instance XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
Langkah ini menghubungkan konteks ke instance XBRL, memberikan informasi kontekstual yang relevan ke data.
## Langkah 7: Simpan Dokumen
Simpan dokumen XBRL yang dimodifikasi ke direktori keluaran yang ditentukan:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Ini menyelesaikan proses, menyimpan dokumen XBRL dengan konteks tambahan.
## Kesimpulan
Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif menambahkan konteks ke dokumen XBRL menggunakan Aspose.Finance untuk .NET. Hal ini meningkatkan kejelasan dan kegunaan data keuangan, memfasilitasi analisis dan pelaporan yang akurat.
## FAQ
### Bisakah Aspose.Finance for .NET menangani dokumen XBRL berukuran besar?
Aspose.Finance untuk .NET dioptimalkan untuk menangani dokumen XBRL dengan berbagai ukuran, termasuk kumpulan data besar.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Finance untuk .NET?
Ya, Anda dapat mengunduh versi uji coba gratis dari situs resmi Aspose.
### Apakah Aspose.Finance for .NET mendukung standar pelaporan keuangan lain selain XBRL?
Aspose.Finance terutama berfokus pada fungsionalitas terkait XBRL tetapi juga menyediakan dukungan untuk format keuangan lainnya.
### Dapatkah saya menyesuaikan informasi konteks sesuai dengan kebutuhan spesifik saya?
Tentu saja, Aspose.Finance untuk .NET menawarkan fleksibilitas untuk menyesuaikan informasi konteks agar sesuai dengan kebutuhan Anda.
### Di mana saya dapat menemukan dukungan atau sumber daya tambahan untuk Aspose.Finance untuk .NET?
Anda dapat mengunjungi forum Aspose.Finance untuk mendapatkan bantuan dari komunitas atau menjelajahi dokumentasi untuk panduan komprehensif.