---
title: Tạo tệp yêu cầu giao dịch ngân hàng OFX
linktitle: Tạo tệp yêu cầu giao dịch ngân hàng OFX
second_title: API Aspose.Finance .NET
description: Tìm hiểu cách tạo tệp yêu cầu giao dịch ngân hàng OFX bằng Aspose.Finance cho .NET với hướng dẫn từng bước chi tiết của chúng tôi. #Aspose #Tài chính
type: docs
weight: 12
url: /vi/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Việc tạo tệp yêu cầu giao dịch ngân hàng OFX có vẻ khó khăn nhưng với các công cụ và hướng dẫn phù hợp, đây có thể là một quy trình đơn giản. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước tạo tệp yêu cầu giao dịch ngân hàng OFX bằng Aspose.Finance cho .NET. Chúng tôi sẽ đề cập đến các điều kiện tiên quyết, các không gian tên cần thiết và cung cấp hướng dẫn chi tiết từng bước để đảm bảo bạn có thể làm theo dễ dàng.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, có một số điều bạn cần chuẩn bị sẵn:
1.  Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy tính của mình. Bạn có thể tải nó xuống từ[Trang web chính thức](https://visualstudio.microsoft.com/).
2.  Aspose.Finance cho .NET: Bạn cần thư viện Aspose.Finance cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/finance/net/).
3. Kiến thức cơ bản về C#: Hiểu những điều cơ bản về lập trình C# sẽ giúp bạn theo dõi các ví dụ về mã.
Khi bạn đã có những điều kiện tiên quyết này, bạn đã sẵn sàng để bắt đầu!
## Nhập không gian tên
Đầu tiên, hãy nhập các không gian tên cần thiết. Các không gian tên này rất quan trọng để truy cập các lớp và phương thức cần thiết để tạo tệp yêu cầu giao dịch ngân hàng OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Bước 1: Thiết lập thư mục làm việc
Trước khi bắt đầu tạo tệp yêu cầu OFX, chúng ta cần chỉ định thư mục đầu ra nơi tệp sẽ được lưu.
```csharp
string outputDir = "Your Output Directory";
```
 Thay thế`"Your Output Directory"` với đường dẫn đến thư mục mà bạn muốn lưu tệp đã tạo.
## Bước 2: Tạo tài liệu yêu cầu OFX
 Tiếp theo, chúng ta cần tạo một thể hiện của`OfxRequestDocument` lớp học. Lớp này sẽ đóng vai trò là nơi chứa yêu cầu OFX của chúng tôi.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Bước 3: Thiết lập yêu cầu đăng nhập
Yêu cầu đăng nhập là cần thiết để xác thực người dùng và bắt đầu phiên OFX. Chúng tôi sẽ thiết lập thông báo yêu cầu đăng nhập và điền vào đó các chi tiết cần thiết như ngày khách hàng, ID người dùng, mật khẩu và thông tin tổ chức tài chính.
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
## Bước 4: Thiết lập tin nhắn yêu cầu ngân hàng
Bây giờ yêu cầu đăng nhập đã được thiết lập, chúng ta sẽ chuyển sang tạo thông báo yêu cầu ngân hàng. Tin nhắn này sẽ chứa thông tin chi tiết về tài khoản ngân hàng và yêu cầu sao kê giao dịch.
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
## Bước 5: Bao gồm chi tiết giao dịch
 Để truy xuất các giao dịch cụ thể, chúng tôi cần chỉ định phạm vi ngày và liệu có bao gồm các giao dịch trong yêu cầu hay không. Điều này được thực hiện bằng cách thiết lập`IncTransaction` sự vật.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Bước 6: Lưu tài liệu yêu cầu OFX
Cuối cùng, chúng tôi sẽ lưu tài liệu yêu cầu OFX ở cả định dạng XML và SGML. Điều này đảm bảo khả năng tương thích với các hệ thống khác nhau có thể sử dụng một trong hai định dạng.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Bước 7: Xác nhận thực hiện thành công
Để xác nhận rằng quá trình đã thực hiện thành công, chúng ta có thể in một thông báo ra bàn điều khiển.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Phần kết luận
Tạo tệp yêu cầu giao dịch ngân hàng OFX bằng Aspose.Finance cho .NET là một quy trình có phương pháp bao gồm thiết lập tài liệu yêu cầu, định cấu hình thông báo đăng nhập và yêu cầu ngân hàng, chỉ định chi tiết giao dịch và lưu tài liệu. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể tạo các tệp yêu cầu OFX phù hợp với nhu cầu cụ thể của mình một cách hiệu quả.
## Câu hỏi thường gặp
### 1. Tệp OFX là gì?
Tệp OFX (Trao đổi tài chính mở) là định dạng chuẩn được sử dụng để trao đổi dữ liệu tài chính giữa các tổ chức và người dùng. Nó được sử dụng rộng rãi cho các báo cáo ngân hàng, giao dịch và các hoạt động tài chính khác.
### 2. Tôi có thể sử dụng Aspose.Finance cho .NET với các ngôn ngữ lập trình khác không?
Aspose.Finance cho .NET được thiết kế đặc biệt để sử dụng với các ngôn ngữ .NET như C#. Tuy nhiên, bạn có thể sử dụng nó trong mọi môi trường được .NET hỗ trợ.
### 3. Có bản dùng thử miễn phí Aspose.Finance cho .NET không?
Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Finance cho .NET từ[đây](https://releases.aspose.com/).
### 4. Làm cách nào để nhận được hỗ trợ cho Aspose.Finance cho .NET?
 Bạn có thể nhận được hỗ trợ từ cộng đồng Aspose và nhóm kỹ thuật thông qua họ[diễn đàn hỗ trợ](https://forum.aspose.com/c/finance/43).
### 5. Tôi có thể lấy giấy phép tạm thời cho Aspose.Finance cho .NET không?
 Có, Aspose cung cấp một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) mà bạn có thể sử dụng để đánh giá sản phẩm.