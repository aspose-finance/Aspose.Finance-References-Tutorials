---
title: Thêm mục vào tài liệu XBRL
linktitle: Thêm mục vào tài liệu XBRL
second_title: API Aspose.Finance .NET
description: Tìm hiểu cách thêm các mục vào tài liệu XBRL bằng Aspose.Finance cho .NET. Đơn giản hóa việc báo cáo tài chính trong các ứng dụng .NET của bạn. #Aspose #Tài chính
type: docs
weight: 13
url: /vi/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Ngôn ngữ báo cáo kinh doanh mở rộng (XBRL) đã trở thành định dạng chuẩn cho báo cáo tài chính, cho phép truyền đạt dữ liệu tài chính hiệu quả và chính xác. Aspose.Finance for .NET cung cấp chức năng mạnh mẽ để hoạt động với các tài liệu XBRL trong ứng dụng .NET của bạn. Trong hướng dẫn này, chúng ta sẽ thực hiện các bước để thêm một mục vào tài liệu XBRL bằng Aspose.Finance cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Finance cho .NET
 Nếu bạn chưa có, hãy tải xuống và cài đặt Aspose.Finance cho .NET từ[Trang web chính thức](https://releases.aspose.com/finance/net/). Làm theo hướng dẫn cài đặt để thiết lập thư viện trong môi trường .NET của bạn.
### 2. Thiết lập môi trường phát triển của bạn
Đảm bảo bạn có môi trường phát triển hoạt động để phát triển .NET. Bạn sẽ cần một IDE tương thích như Visual Studio, cùng với .NET framework được cài đặt trên hệ thống của bạn.
## Nhập không gian tên
Trước tiên, hãy nhập các vùng tên cần thiết vào ứng dụng .NET của bạn để sử dụng chức năng do Aspose.Finance cung cấp cho .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Bây giờ hãy chia mã ví dụ thành nhiều bước:
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
## Bước 4: Xác định bối cảnh và thực thể
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Tạo bối cảnh và thực thể cho phiên bản XBRL, chỉ định chi tiết về khoảng thời gian và thực thể.
## Bước 5: Thêm đơn vị
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Xác định đơn vị cho phiên bản XBRL, chỉ định tên đủ điều kiện đo.
## Bước 6: Thêm mục
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
Thêm một mục vào phiên bản XBRL, chỉ định khái niệm, bối cảnh, đơn vị, độ chính xác và giá trị của nó.
## Bước 7: Lưu tài liệu
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Lưu tài liệu XBRL vào thư mục đầu ra.
## Phần kết luận
Việc thêm các mục vào tài liệu XBRL là điều cần thiết để thể hiện chính xác dữ liệu tài chính. Aspose.Finance for .NET đơn giản hóa quy trình này bằng cách cung cấp API toàn diện để hoạt động với các tài liệu XBRL trong các ứng dụng .NET.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Finance cho .NET với bất kỳ ứng dụng .NET nào không?
Có, Aspose.Finance cho .NET tương thích với mọi ứng dụng .NET, bao gồm các ứng dụng ASP.NET, WinForms và Console.
### Aspose.Finance cho .NET có được sử dụng miễn phí không?
 Aspose.Finance cho .NET là một thư viện thương mại. Bạn có thể tải xuống phiên bản dùng thử miễn phí để đánh giá các tính năng của nó và có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy).
### Aspose.Finance cho .NET có hỗ trợ các định dạng báo cáo tài chính khác ngoài XBRL không?
Aspose.Finance cho .NET chủ yếu tập trung vào chức năng liên quan đến XBRL. Tuy nhiên, Aspose cung cấp các thư viện khác để làm việc với các định dạng tài chính khác nhau.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Finance cho .NET?
 Bạn có thể nhận hỗ trợ cho Aspose.Finance cho .NET thông qua[diễn đàn chính thức](https://forum.aspose.com/c/finance/43)nơi bạn có thể đặt câu hỏi và tương tác với những người dùng khác cũng như nhân viên hỗ trợ.
### Tôi có thể xin giấy phép tạm thời cho Aspose.Finance cho .NET không?
 Có, giấy phép tạm thời cho Aspose.Finance cho .NET có sẵn cho mục đích thử nghiệm. Bạn có thể có được một[đây](https://purchase.aspose.com/temporary-license/).