---
title: XBRL 문서에 항목 추가
linktitle: XBRL 문서에 항목 추가
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 XBRL 문서에 항목을 추가하는 방법을 알아보세요. .NET 애플리케이션에서 재무 보고를 단순화합니다. #양도 #금융
type: docs
weight: 13
url: /ko/net/xbrl-file-creation/add-item-to-xbrl-document/
---
XBRL(Extensible Business Reporting Language)은 재무 보고의 표준 형식이 되어 재무 데이터의 효율적이고 정확한 통신을 가능하게 합니다. .NET용 Aspose.Finance는 .NET 애플리케이션에서 XBRL 문서로 작업할 수 있는 강력한 기능을 제공합니다. 이 자습서에서는 .NET용 Aspose.Finance를 사용하여 XBRL 문서에 항목을 추가하는 단계를 안내합니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 Aspose.Finance 설치
 아직 설치하지 않았다면 다음에서 Aspose.Finance for .NET을 다운로드하여 설치하세요.[공식 웹 사이트](https://releases.aspose.com/finance/net/). 설치 지침에 따라 .NET 환경에서 라이브러리를 설정하세요.
### 2. 개발 환경 설정
.NET 개발을 위한 작업 개발 환경이 있는지 확인하세요. 시스템에 설치된 .NET 프레임워크와 함께 Visual Studio와 같은 호환 가능한 IDE가 필요합니다.
## 네임스페이스 가져오기
먼저 Aspose.Finance for .NET에서 제공하는 기능을 활용하려면 필요한 네임스페이스를 .NET 애플리케이션으로 가져옵니다.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#이제 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 소스 및 출력 디렉터리 정의
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 바꾸다`"Your Source Directory"` 그리고`"Your Output Directory"` 각각 소스 및 출력 디렉터리의 경로를 사용합니다.
## 2단계: XBRL 문서 및 인스턴스 생성
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
작업할 XBRL 문서 및 인스턴스를 초기화합니다.
## 3단계: 스키마 참조 추가
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
XBRL 인스턴스에 스키마 참조를 추가하여 스키마 파일에 대한 경로를 제공하고 네임스페이스 세부 정보를 지정합니다.
## 4단계: 컨텍스트 및 엔터티 정의
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
기간 및 엔터티 세부 정보를 지정하여 XBRL 인스턴스에 대한 컨텍스트 및 엔터티를 생성합니다.
## 5단계: 단위 추가
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
측정값 정규화된 이름을 지정하여 XBRL 인스턴스의 단위를 정의합니다.
## 6단계: 항목 추가
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
개념, 컨텍스트, 단위, 정밀도 및 값을 지정하여 XBRL 인스턴스에 항목을 추가합니다.
## 7단계: 문서 저장
```csharp
document.Save(outputDir + @"document5.xbrl");
```
XBRL 문서를 출력 디렉터리에 저장합니다.
## 결론
재무 데이터를 정확하게 표현하려면 XBRL 문서에 항목을 추가하는 것이 필수적입니다. .NET용 Aspose.Finance는 .NET 애플리케이션에서 XBRL 문서로 작업할 수 있는 포괄적인 API를 제공하여 이 프로세스를 단순화합니다.
## 자주 묻는 질문
### 모든 .NET 애플리케이션에서 Aspose.Finance for .NET을 사용할 수 있나요?
예, .NET용 Aspose.Finance는 ASP.NET, WinForms 및 콘솔 애플리케이션을 포함한 모든 .NET 애플리케이션과 호환됩니다.
### .NET용 Aspose.Finance는 무료로 사용할 수 있나요?
 .NET용 Aspose.Finance는 상용 라이브러리입니다. 무료 평가판을 다운로드하여 기능을 평가할 수 있으며 라이센스는 다음에서 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### .NET용 Aspose.Finance는 XBRL 외에 다른 재무 보고 형식을 지원합니까?
.NET용 Aspose.Finance는 주로 XBRL 관련 기능에 중점을 둡니다. 그러나 Aspose는 다양한 금융 형식으로 작업할 수 있는 다른 라이브러리를 제공합니다.
### .NET용 Aspose.Finance에 대한 지원을 어떻게 받을 수 있나요?
 다음을 통해 .NET용 Aspose.Finance에 대한 지원을 받을 수 있습니다.[공식 포럼](https://forum.aspose.com/c/finance/43)에서 질문을 하고 다른 사용자 및 지원 담당자와 상호 작용할 수 있습니다.
### .NET용 Aspose.Finance에 대한 임시 라이선스를 얻을 수 있나요?
 예, .NET용 Aspose.Finance의 임시 라이선스를 테스트 목적으로 사용할 수 있습니다. 하나를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).