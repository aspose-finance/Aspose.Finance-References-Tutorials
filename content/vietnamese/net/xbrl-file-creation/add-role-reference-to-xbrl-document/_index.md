---
title: Thêm tham chiếu vai trò vào tài liệu XBRL
linktitle: Thêm tham chiếu vai trò vào tài liệu XBRL
second_title: API Aspose.Finance .NET
description: Tìm hiểu cách thêm tham chiếu vai trò vào tài liệu XBRL bằng Aspose.Finance cho .NET. Đơn giản hóa việc báo cáo tài chính trong các ứng dụng .NET của bạn bằng hướng dẫn này.
type: docs
weight: 14
url: /vi/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (Ngôn ngữ báo cáo doanh nghiệp mở rộng) đã trở thành một tiêu chuẩn để trao đổi thông tin doanh nghiệp, đặc biệt là trong báo cáo tài chính. Aspose.Finance for .NET đơn giản hóa việc làm việc với các tài liệu XBRL trong các ứng dụng .NET. Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm tham chiếu vai trò vào tài liệu XBRL bằng Aspose.Finance cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Finance cho .NET
Đảm bảo bạn đã cài đặt Aspose.Finance for .NET trong môi trường phát triển của mình. Nếu bạn chưa có, hãy tải xuống từ[phát hành](https://releases.aspose.com/finance/net/) và làm theo hướng dẫn cài đặt.
### 2. Thiết lập môi trường phát triển của bạn
Đảm bảo bạn có môi trường phát triển làm việc để phát triển .NET. Điều này bao gồm một IDE tương thích như Visual Studio và .NET framework được cài đặt trên hệ thống của bạn.
## Nhập không gian tên
Bắt đầu bằng cách nhập các vùng tên cần thiết vào ứng dụng .NET của bạn để truy cập chức năng do Aspose.Finance cung cấp cho .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
## Bước 1: Xác định thư mục nguồn và đầu ra
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Thay thế`"Your Source Directory"` Và`"Your Output Directory"` với các đường dẫn tương ứng đến thư mục nguồn và đầu ra của bạn.
## Bước 2: Tạo tài liệu và phiên bản XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Khởi tạo một tài liệu và phiên bản XBRL để làm việc.
## Bước 3: Thêm tham chiếu lược đồ
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Thêm tham chiếu lược đồ vào phiên bản XBRL, cung cấp đường dẫn đến tệp lược đồ và chỉ định chi tiết vùng tên.
## Bước 4: Truy xuất loại vai trò và thêm tham chiếu vai trò
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Truy xuất loại vai trò bằng URI của nó và thêm tham chiếu vai trò vào phiên bản XBRL.
## Bước 5: Lưu tài liệu
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Lưu tài liệu XBRL vào thư mục đầu ra.
## Phần kết luận
Việc thêm tham chiếu vai trò vào tài liệu XBRL là rất quan trọng để xác định vai trò của các thành phần khác nhau trong tài liệu. Aspose.Finance cho .NET cung cấp một cách đơn giản để hoàn thành nhiệm vụ này, trao quyền cho các nhà phát triển làm việc hiệu quả với các tài liệu XBRL trong ứng dụng .NET của họ.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Finance cho .NET với bất kỳ ứng dụng .NET nào không?
Có, Aspose.Finance cho .NET tương thích với mọi ứng dụng .NET, bao gồm các ứng dụng ASP.NET, WinForms và Console.
### Aspose.Finance cho .NET có được sử dụng miễn phí không?
 Aspose.Finance cho .NET là một thư viện thương mại. Bạn có thể tải xuống phiên bản dùng thử miễn phí để đánh giá các tính năng của nó và có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy).
### Aspose.Finance cho .NET có hỗ trợ các định dạng báo cáo tài chính khác ngoài XBRL không?
Aspose.Finance cho .NET chủ yếu tập trung vào chức năng liên quan đến XBRL. Tuy nhiên, Aspose cung cấp các thư viện khác để làm việc với các định dạng tài chính khác nhau.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Finance cho .NET?
 Bạn có thể nhận hỗ trợ cho Aspose.Finance cho .NET thông qua[diễn đàn](https://forum.aspose.com/c/finance/43)nơi bạn có thể đặt câu hỏi và tương tác với những người dùng khác cũng như nhân viên hỗ trợ.
### Tôi có thể xin giấy phép tạm thời cho Aspose.Finance cho .NET không?
 Có, giấy phép tạm thời cho Aspose.Finance cho .NET có sẵn cho mục đích thử nghiệm. Bạn có thể có được một[đây](https://purchase.aspose.com/temporary-license/).