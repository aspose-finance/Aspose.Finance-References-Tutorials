---
title: Thêm đơn vị vào tài liệu XBRL
linktitle: Thêm đơn vị vào tài liệu XBRL
second_title: API Aspose.Finance .NET
description: Tìm hiểu cách thêm đơn vị vào tài liệu XBRL một cách dễ dàng với Aspose.Finance cho .NET. Hãy nâng cao khả năng xử lý dữ liệu tài chính của bạn ngay hôm nay!
type: docs
weight: 16
url: /vi/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Chào mừng bạn đến với thế giới của Aspose.Finance dành cho .NET - cửa ngõ để bạn thao tác tài liệu tài chính hiệu quả trong các ứng dụng .NET. Cho dù bạn đang xây dựng phần mềm kế toán, công cụ phân tích tài chính hay bất kỳ ứng dụng tài chính nào khác, Aspose.Finance cho .NET đều trang bị cho bạn một bộ tính năng toàn diện để hợp lý hóa quá trình phát triển của bạn.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào việc khai thác sức mạnh của Aspose.Finance cho .NET, hãy đảm bảo rằng chúng ta có sẵn các điều kiện tiên quyết cần thiết:
### 1. Cài đặt Visual Studio
Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. Nếu không, bạn có thể tải xuống và cài đặt nó từ trang web chính thức của Microsoft.
### 2. Xin giấy phép
 Để khai thác toàn bộ tiềm năng của Aspose.Finance cho .NET, bạn cần có giấy phép hợp lệ. Bạn có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy) hoặc chọn giấy phép tạm thời cho mục đích thử nghiệm.
### 3. Tải xuống và tham khảo Aspose.Finance cho .NET
 Tải xuống thư viện Aspose.Finance cho .NET từ[trang phát hành](https://releases.aspose.com/finance/net/) và tham chiếu nó trong dự án .NET của bạn.
### 4. Truy cập tài liệu và hỗ trợ
 Tham khảo đến[tài liệu](https://reference.aspose.com/finance/net/)để biết thông tin chi tiết về cách sử dụng Aspose.Finance cho .NET. Ngoài ra, bạn có thể tìm kiếm sự trợ giúp từ cộng đồng Aspose.Finance trên[diễn đàn hỗ trợ](https://forum.aspose.com/c/finance/43).
## Nhập không gian tên
Bây giờ, hãy nhập các vùng tên cần thiết vào dự án .NET của bạn:
## Bước 1: Thêm không gian tên Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Không gian tên này chứa các lớp và phương thức cần thiết để làm việc với các tài liệu và dữ liệu XBRL.
Hãy chia ví dụ được cung cấp thành nhiều bước để hiểu cách thêm đơn vị vào tài liệu XBRL bằng Aspose.Finance cho .NET.
## Bước 1: Xác định thư mục đầu ra
```csharp
// Thư mục đầu ra
string outputDir = "Your Output Directory";
```
 Thay thế`"Your Output Directory"` với đường dẫn thực tế đến thư mục đầu ra mong muốn của bạn.
## Bước 2: Tạo tài liệu XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Điều này khởi tạo một phiên bản mới của tài liệu XBRL.
## Bước 3: Truy cập phiên bản XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Thao tác này truy xuất tập hợp các phiên bản XBRL từ tài liệu và thêm một phiên bản mới vào đó.
## Bước 4: Thêm đơn vị
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Điều này tạo ra một đơn vị đo lường mới (trong trường hợp này là USD) và thêm nó vào phiên bản XBRL. Bạn có thể điều chỉnh mã tiền tệ và URI vùng tên nếu cần.
## Bước 5: Lưu tài liệu
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Thao tác này sẽ lưu tài liệu XBRL đã sửa đổi vào thư mục đầu ra được chỉ định.
## Phần kết luận
Tóm lại, Aspose.Finance cho .NET trao quyền cho các nhà phát triển dễ dàng thao tác các tài liệu và dữ liệu tài chính trong các ứng dụng .NET của họ. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch Aspose.Finance cho .NET vào các dự án của mình và nâng cao khả năng xử lý tài chính của chúng.
## Câu hỏi thường gặp
### 1. Tôi có thể sử dụng Aspose.Finance cho .NET mà không cần giấy phép không?
Không, cần có giấy phép hợp lệ để mở khóa toàn bộ tính năng của Aspose.Finance cho .NET. Tuy nhiên, giấy phép tạm thời có sẵn cho mục đích thử nghiệm.
### 2. Aspose.Finance for .NET có phù hợp để xây dựng phần mềm kế toán không?
Có, Aspose.Finance for .NET cung cấp các chức năng mạnh mẽ được thiết kế riêng để xây dựng phần mềm kế toán và các ứng dụng tài chính liên quan.
### 3. Tôi có thể tìm hỗ trợ cho Aspose.Finance cho .NET ở đâu?
Bạn có thể tìm kiếm sự trợ giúp từ cộng đồng Aspose.Finance trên diễn đàn hỗ trợ.
### 4. Tôi có thể tùy chỉnh đơn vị đo trong tài liệu XBRL không?
Có, bạn có thể tạo và thêm đơn vị đo lường tùy chỉnh vào tài liệu XBRL bằng Aspose.Finance cho .NET.
### 5. Aspose.Finance cho .NET có hỗ trợ nhiều loại tiền tệ không?
Có, Aspose.Finance for .NET hỗ trợ nhiều loại tiền tệ, cho phép xử lý dữ liệu tài chính linh hoạt.