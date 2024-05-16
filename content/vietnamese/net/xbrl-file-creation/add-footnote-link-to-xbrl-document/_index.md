---
title: Thêm liên kết chú thích cuối trang vào tài liệu XBRL
linktitle: Thêm liên kết chú thích cuối trang vào tài liệu XBRL
second_title: API Aspose.Finance .NET
description: Tìm hiểu cách thêm liên kết chú thích cuối trang vào tài liệu XBRL bằng Aspose.Finance cho .NET. Dễ dàng nâng cao báo cáo tài chính với bối cảnh bổ sung.
type: docs
weight: 12
url: /vi/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Việc thêm liên kết chú thích cuối trang vào tài liệu XBRL là rất quan trọng để cung cấp thêm ngữ cảnh hoặc giải thích cho các điểm dữ liệu cụ thể. Trong hướng dẫn này, chúng ta sẽ hướng dẫn từng bước quy trình bằng cách sử dụng Aspose.Finance cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Finance for .NET: Đảm bảo bạn đã cài đặt Aspose.Finance for .NET trên hệ thống của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/finance/net/).
  
2. Môi trường phát triển: Có môi trường phát triển được thiết lập với .NET Framework hoặc .NET Core.
## Nhập không gian tên:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Bước 1: Đặt thư mục nguồn và đầu ra
Đầu tiên, chỉ định thư mục cho tệp nguồn và tệp đầu ra:
```csharp
// Thư mục nguồn
string sourceDir = "Your Source Directory";
// Thư mục đầu ra
string outputDir = "Your Output Directory";
```
## Bước 2: Tạo tài liệu và phiên bản XBRL
Khởi tạo một tài liệu và phiên bản XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Bước 3: Thêm tài liệu tham khảo lược đồ
Thêm tham chiếu lược đồ vào phiên bản XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Bước 4: Xác định bối cảnh
Xác định bối cảnh cho phiên bản XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Bước 5: Thêm liên kết chú thích cuối trang
Tạo và thêm liên kết chú thích cuối trang vào phiên bản XBRL:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## Bước 6: Lưu tài liệu
Lưu tài liệu XBRL đã sửa đổi:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Phần kết luận
Thêm liên kết chú thích cuối trang vào tài liệu XBRL là một quá trình đơn giản với Aspose.Finance cho .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể kết hợp liền mạch bối cảnh hoặc giải thích bổ sung vào báo cáo tài chính của mình.
## Câu hỏi thường gặp
### Tôi có thể thêm nhiều liên kết chú thích cuối trang vào một tài liệu XBRL không?
Có, bạn có thể thêm nhiều liên kết chú thích cuối trang bằng cách lặp lại các bước được nêu trong hướng dẫn này cho mỗi liên kết bổ sung.
### Aspose.Finance cho .NET có tương thích với cả .NET Framework và .NET Core không?
Có, Aspose.Finance for .NET hỗ trợ cả môi trường .NET Framework và .NET Core.
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Finance cho .NET?
 Bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance cho .NET có hỗ trợ xác thực XBRL không?
Có, Aspose.Finance for .NET cung cấp hỗ trợ toàn diện cho việc xác thực XBRL để đảm bảo tuân thủ các tiêu chuẩn ngành.
### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Finance cho .NET ở đâu?
 Bạn có thể ghé thăm[Aspose.Finance cho diễn đàn .NET](https://forum.aspose.com/c/finance/43) để được hỗ trợ và truy cập tài liệu[đây](https://reference.aspose.com/finance/net/).