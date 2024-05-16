---
title: XBRL 문서에 각주 링크 추가
linktitle: XBRL 문서에 각주 링크 추가
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 XBRL 문서에 각주 링크를 추가하는 방법을 알아보세요. 추가 컨텍스트를 통해 재무 보고서를 쉽게 향상할 수 있습니다.
type: docs
weight: 12
url: /ko/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
특정 데이터 포인트에 대한 추가 컨텍스트나 설명을 제공하려면 XBRL 문서에 각주 링크를 추가하는 것이 중요합니다. 이 튜토리얼에서는 .NET용 Aspose.Finance를 사용하여 프로세스를 단계별로 안내합니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Finance: 시스템에 .NET용 Aspose.Finance가 설치되어 있는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/finance/net/).
  
2. 개발 환경: .NET Framework 또는 .NET Core를 사용하여 개발 환경을 설정합니다.
## 네임스페이스 가져오기:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 1단계: 소스 및 출력 디렉터리 설정
먼저 소스 및 출력 파일의 디렉터리를 지정합니다.
```csharp
// 소스 디렉터리
string sourceDir = "Your Source Directory";
// 출력 디렉토리
string outputDir = "Your Output Directory";
```
## 2단계: XBRL 문서 및 인스턴스 생성
XBRL 문서 및 인스턴스를 초기화합니다.
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 3단계: 스키마 참조 추가
XBRL 인스턴스에 스키마 참조를 추가합니다.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## 4단계: 컨텍스트 정의
XBRL 인스턴스에 대한 컨텍스트를 정의합니다.
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## 5단계: 각주 링크 추가
XBRL 인스턴스에 대한 각주 링크를 생성하고 추가합니다.
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
## 6단계: 문서 저장
수정된 XBRL 문서를 저장합니다.
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## 결론
XBRL 문서에 각주 링크를 추가하는 것은 Aspose.Finance for .NET을 사용하는 간단한 프로세스입니다. 이 튜토리얼에 설명된 단계를 따르면 추가 컨텍스트나 설명을 재무 보고서에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### 단일 XBRL 문서에 여러 각주 링크를 추가할 수 있습니까?
예, 각 추가 링크에 대해 이 튜토리얼에 설명된 단계를 반복하여 여러 각주 링크를 추가할 수 있습니다.
### .NET용 Aspose.Finance는 .NET Framework 및 .NET Core와 모두 호환됩니까?
예, .NET용 Aspose.Finance는 .NET Framework와 .NET Core 환경을 모두 지원합니다.
### .NET용 Aspose.Finance의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득하실 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### .NET용 Aspose.Finance는 XBRL 검증을 지원합니까?
예, .NET용 Aspose.Finance는 업계 표준 준수를 보장하기 위해 XBRL 검증에 대한 포괄적인 지원을 제공합니다.
### .NET용 Aspose.Finance에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[.NET 포럼용 Aspose.Finance](https://forum.aspose.com/c/finance/43) 지원 및 액세스 문서[여기](https://reference.aspose.com/finance/net/).