---
title: Tambahkan Referensi Peran ke Dokumen XBRL
linktitle: Tambahkan Referensi Peran ke Dokumen XBRL
second_title: Aspose.Keuangan .NET API
description: Pelajari cara menambahkan referensi peran ke dokumen XBRL menggunakan Aspose.Finance untuk .NET. Sederhanakan pelaporan keuangan di aplikasi .NET Anda dengan tutorial ini.
type: docs
weight: 14
url: /id/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) telah menjadi standar pertukaran informasi bisnis, khususnya dalam pelaporan keuangan. Aspose.Finance for .NET menyederhanakan pekerjaan dengan dokumen XBRL dalam aplikasi .NET. Tutorial ini akan memandu Anda melalui proses penambahan referensi peran ke dokumen XBRL menggunakan Aspose.Finance untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
### 1. Instal Aspose.Finance untuk .NET
Pastikan Anda telah menginstal Aspose.Finance for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dari[rilis](https://releases.aspose.com/finance/net/) dan ikuti petunjuk instalasi.
### 2. Siapkan Lingkungan Pengembangan Anda
Pastikan Anda memiliki lingkungan pengembangan yang berfungsi untuk pengembangan .NET. Ini termasuk IDE yang kompatibel seperti Visual Studio dan kerangka .NET yang diinstal pada sistem Anda.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam aplikasi .NET Anda untuk mengakses fungsionalitas yang disediakan oleh Aspose.Finance untuk .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Langkah 4: Ambil Jenis Peran dan Tambahkan Referensi Peran
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Ambil tipe peran menggunakan URI-nya dan tambahkan referensi peran ke instance XBRL.
## Langkah 5: Simpan Dokumen
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Simpan dokumen XBRL ke direktori keluaran.
## Kesimpulan
Menambahkan referensi peran ke dokumen XBRL sangat penting untuk menentukan peran berbagai elemen dalam dokumen. Aspose.Finance for .NET menyediakan cara mudah untuk menyelesaikan tugas ini, memberdayakan pengembang untuk bekerja secara efisien dengan dokumen XBRL dalam aplikasi .NET mereka.
## FAQ
### Bisakah saya menggunakan Aspose.Finance untuk .NET dengan aplikasi .NET apa pun?
Ya, Aspose.Finance untuk .NET kompatibel dengan aplikasi .NET apa pun, termasuk aplikasi ASP.NET, WinForms, dan Konsol.
### Apakah Aspose.Finance untuk .NET gratis untuk digunakan?
 Aspose.Finance untuk .NET adalah perpustakaan komersial. Anda dapat mengunduh versi uji coba gratis untuk mengevaluasi fitur-fiturnya, dan lisensinya dapat dibeli[Di Sini](https://purchase.aspose.com/buy).
### Apakah Aspose.Finance for .NET mendukung format pelaporan keuangan lain selain XBRL?
Aspose.Finance untuk .NET terutama berfokus pada fungsionalitas terkait XBRL. Namun, Aspose menawarkan perpustakaan lain untuk bekerja dengan format keuangan yang berbeda.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Finance untuk .NET?
 Anda bisa mendapatkan dukungan untuk Aspose.Finance untuk .NET melalui[forum](https://forum.aspose.com/c/finance/43)tempat Anda dapat mengajukan pertanyaan dan berinteraksi dengan pengguna lain serta staf pendukung.
### Bisakah saya mendapatkan lisensi sementara Aspose.Finance untuk .NET?
 Ya, lisensi sementara untuk Aspose.Finance untuk .NET tersedia untuk tujuan pengujian. Anda bisa mendapatkannya[Di Sini](https://purchase.aspose.com/temporary-license/).