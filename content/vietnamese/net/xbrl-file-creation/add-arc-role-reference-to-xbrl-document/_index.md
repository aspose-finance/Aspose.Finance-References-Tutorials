---
title: Thêm tham chiếu vai trò ARC vào tài liệu XBRL
linktitle: Thêm tham chiếu vai trò ARC vào tài liệu XBRL
second_title: API Aspose.Finance .NET
description: Tìm hiểu cách thao tác hiệu quả các tài liệu XBRL bằng Aspose.Finance cho .NET. Thêm tài liệu tham khảo vai trò ARC dễ dàng với hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Giới thiệu
Trong thế giới quản lý và báo cáo dữ liệu tài chính, Ngôn ngữ báo cáo kinh doanh mở rộng (XBRL) đóng một vai trò quan trọng. Nó tiêu chuẩn hóa cách thức truyền đạt và trao đổi thông tin tài chính, đảm bảo tính nhất quán, chính xác và hiệu quả. Tuy nhiên, việc thao tác các tài liệu XBRL, đặc biệt là khi kết hợp các vai trò và tham chiếu cụ thể, đòi hỏi sự hiểu biết sâu sắc về các cơ chế cơ bản. Hướng dẫn này tập trung vào một nhiệm vụ như vậy: thêm Tham chiếu vai trò ARC vào tài liệu XBRL bằng Aspose.Finance cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### Thiết lập môi trường
1.  Cài đặt Aspose.Finance cho .NET: Tải xuống và cài đặt thư viện Aspose.Finance cho .NET từ[phát hành](https://releases.aspose.com/finance/net/).
   
2. Môi trường phát triển: Thiết lập môi trường phát triển của bạn với Visual Studio hoặc bất kỳ IDE ưa thích nào khác.
## Nhập không gian tên
Đảm bảo nhập các không gian tên cần thiết trong mã C# của bạn:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Bước 1: Xác định thư mục nguồn và đầu ra
Trước khi tiếp tục, hãy chỉ định thư mục nguồn và đầu ra nơi các tệp XBRL của bạn sẽ được đặt và lưu tương ứng.
```csharp
// Thư mục nguồn
string sourceDir = "Your Source Directory";
// Thư mục đầu ra
string outputDir = "Your Output Directory";
```
## Bước 2: Tạo tài liệu XBRL
 Khởi tạo một`XbrlDocument` đối tượng làm việc với dữ liệu XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Bước 3: Truy cập Bộ sưu tập XbrlInstance
Truy cập bộ sưu tập các phiên bản XBRL trong tài liệu.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Bước 4: Thêm XbrlInstance
Thêm một phiên bản XBRL mới vào bộ sưu tập.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Bước 5: Thêm tham chiếu lược đồ
Bao gồm tham chiếu lược đồ trong phiên bản XBRL, chỉ định thư mục nguồn, tiền tố vùng tên và URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Bước 6: Truy xuất ArcroleType
 Truy xuất`ArcroleType` dựa trên một URI cụ thể.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Bước 7: Thêm ArcroleReference
 Nếu`ArcroleType` được tìm thấy, tạo một`ArcroleReference` và thêm nó vào các tham chiếu arcrole của cá thể XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Bước 8: Lưu tài liệu
Lưu tài liệu XBRL đã sửa đổi vào thư mục đầu ra được chỉ định.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách thêm Tham chiếu vai trò ARC vào tài liệu XBRL bằng Aspose.Finance cho .NET. Bằng cách làm theo các hướng dẫn từng bước này và tận dụng các khả năng của Aspose.Finance, bạn có thể quản lý và thao tác dữ liệu XBRL một cách hiệu quả để đáp ứng các yêu cầu cụ thể của mình.
## Câu hỏi thường gặp
### XBRL là gì?
XBRL là viết tắt của Ngôn ngữ báo cáo kinh doanh mở rộng, một ngôn ngữ được tiêu chuẩn hóa để giao tiếp điện tử về dữ liệu tài chính và kinh doanh.
### Tại sao XBRL lại quan trọng?
XBRL đảm bảo tính nhất quán, chính xác và hiệu quả trong việc trao đổi và phân tích thông tin tài chính, mang lại lợi ích cho các cơ quan quản lý, nhà phân tích và doanh nghiệp.
### Aspose.Finance có thể xử lý các tác vụ XBRL phức tạp không?
Có, Aspose.Finance cung cấp chức năng mạnh mẽ để làm việc với tài liệu XBRL, bao gồm xử lý các tác vụ phức tạp như tham chiếu vai trò và quản lý phân loại.
### Aspose.Finance có tương thích với các thư viện .NET khác không?
Có, Aspose.Finance tích hợp liền mạch với các thư viện .NET khác, cung cấp hỗ trợ rộng rãi cho việc báo cáo và thao tác dữ liệu tài chính.
### Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Finance ở đâu?
 Để được hỗ trợ thêm hãy truy cập[Trang hỗ trợ Aspose.Finance](https://forum.aspose.com/c/finance/43).