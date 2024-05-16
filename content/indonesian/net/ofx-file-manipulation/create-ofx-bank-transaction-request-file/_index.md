---
title: Buat File Permintaan Transaksi Bank OFX
linktitle: Buat File Permintaan Transaksi Bank OFX
second_title: Aspose.Keuangan .NET API
description: Pelajari cara membuat file permintaan transaksi bank OFX menggunakan Aspose.Finance untuk .NET dengan panduan langkah demi langkah kami yang terperinci. #Aspose #Keuangan
type: docs
weight: 12
url: /id/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Membuat file permintaan transaksi bank OFX mungkin tampak menakutkan, namun dengan alat dan panduan yang tepat, ini bisa menjadi proses yang mudah. Dalam tutorial ini, kami akan memandu Anda melalui setiap langkah pembuatan file permintaan transaksi bank OFX menggunakan Aspose.Finance untuk .NET. Kami akan membahas prasyarat, namespace yang diperlukan, dan memberikan panduan langkah demi langkah yang mendetail untuk memastikan Anda dapat mengikutinya dengan mudah.
## Prasyarat
Sebelum kita mendalami tutorialnya, ada beberapa hal yang perlu Anda siapkan:
1.  Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Anda dapat mengunduhnya dari[situs web resmi](https://visualstudio.microsoft.com/).
2.  Aspose.Finance untuk .NET: Anda memerlukan perpustakaan Aspose.Finance untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/finance/net/).
3. Pengetahuan Dasar C#: Memahami dasar-dasar pemrograman C# akan membantu Anda mengikuti contoh kode.
Setelah Anda memiliki prasyarat ini, Anda siap untuk memulai!
## Impor Namespace
Pertama, mari impor namespace yang diperlukan. Namespace ini sangat penting untuk mengakses kelas dan metode yang diperlukan untuk membuat file permintaan transaksi bank OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Langkah 1: Siapkan Direktori Kerja
Sebelum kita mulai membuat file permintaan OFX, kita perlu menentukan direktori keluaran dimana file akan disimpan.
```csharp
string outputDir = "Your Output Directory";
```
 Mengganti`"Your Output Directory"` dengan jalur ke direktori tempat Anda ingin menyimpan file yang dihasilkan.
## Langkah 2: Buat Dokumen Permintaan OFX
 Selanjutnya, kita perlu membuat sebuah instance dari`OfxRequestDocument` kelas. Kelas ini akan berfungsi sebagai wadah untuk permintaan OFX kami.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Langkah 3: Siapkan Permintaan Masuk
Permintaan masuk sangat penting untuk mengautentikasi pengguna dan memulai sesi OFX. Kami akan menyiapkan pesan permintaan masuk dan mengisinya dengan detail yang diperlukan seperti tanggal klien, ID pengguna, kata sandi, dan informasi lembaga keuangan.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Langkah 4: Siapkan Pesan Permintaan Bank
Sekarang setelah permintaan masuk sudah diatur, kita akan melanjutkan ke pembuatan pesan permintaan bank. Pesan ini akan berisi rincian rekening bank dan permintaan laporan transaksi.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Langkah 5: Sertakan Detail Transaksi
 Untuk mengambil transaksi tertentu, kita perlu menentukan rentang tanggal dan apakah akan menyertakan transaksi dalam permintaan. Hal ini dilakukan dengan menyiapkan`IncTransaction` obyek.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Langkah 6: Simpan Dokumen Permintaan OFX
Terakhir, kami akan menyimpan dokumen permintaan OFX dalam format XML dan SGML. Hal ini memastikan kompatibilitas dengan sistem berbeda yang mungkin menggunakan format mana pun.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Langkah 7: Konfirmasikan Eksekusi yang Berhasil
Untuk mengonfirmasi bahwa proses berhasil dijalankan, kita dapat mencetak pesan ke konsol.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Kesimpulan
Membuat file permintaan transaksi bank OFX menggunakan Aspose.Finance untuk .NET adalah proses metodis yang melibatkan penyiapan dokumen permintaan, mengonfigurasi pesan masuk dan permintaan bank, menentukan detail transaksi, dan menyimpan dokumen. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat secara efisien membuat file permintaan OFX yang disesuaikan dengan kebutuhan spesifik Anda.
## FAQ
### 1. Apa itu file OFX?
File OFX (Open Financial Exchange) adalah format standar yang digunakan untuk pertukaran data keuangan antara institusi dan pengguna. Ini banyak digunakan untuk laporan bank, transaksi, dan aktivitas keuangan lainnya.
### 2. Bisakah saya menggunakan Aspose.Finance for .NET dengan bahasa pemrograman lain?
Aspose.Finance untuk .NET dirancang khusus untuk digunakan dengan bahasa .NET seperti C#. Namun, Anda dapat menggunakannya di lingkungan mana pun yang mendukung .NET.
### 3. Apakah tersedia uji coba gratis untuk Aspose.Finance untuk .NET?
Ya, Anda dapat mengunduh uji coba gratis Aspose.Finance untuk .NET dari[Di Sini](https://releases.aspose.com/).
### 4. Bagaimana cara mendapatkan dukungan Aspose.Finance untuk .NET?
 Anda bisa mendapatkan dukungan dari komunitas Aspose dan tim teknis melalui mereka[forum dukungan](https://forum.aspose.com/c/finance/43).
### 5. Bisakah saya mendapatkan lisensi sementara Aspose.Finance untuk .NET?
 Ya, Aspose menawarkan a[izin sementara](https://purchase.aspose.com/temporary-license/) yang dapat Anda gunakan untuk mengevaluasi produk.