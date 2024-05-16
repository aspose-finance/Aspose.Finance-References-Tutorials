---
title: XBRL 문서에 컨텍스트 추가
linktitle: XBRL 문서에 컨텍스트 추가
second_title: Aspose.Finance.NET API
description: 간소화된 재무 보고를 위해 Aspose.Finance를 사용하여 .NET에서 XBRL 문서에 컨텍스트를 추가하는 방법을 알아보세요. #Aspose #금융 #XBRL
type: docs
weight: 11
url: /ko/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## 소개
재무 보고 영역에서 XBRL(eXtensible Business Reporting Language)은 비즈니스 정보 교환을 표준화하는 데 중추적인 역할을 합니다. XBRL 문서에 컨텍스트를 추가하는 것은 포함된 데이터의 무결성과 관련성을 보장하는 데 중요합니다. .NET용 Aspose.Finance를 사용하면 이 프로세스가 간소화되고 효율적이 되어 개발자가 XBRL 문서에 컨텍스트를 원활하게 통합할 수 있습니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. .NET 라이브러리용 Aspose.Finance: 다음에서 .NET 라이브러리용 Aspose.Finance를 다운로드하고 설치하세요.[릴리스](https://releases.aspose.com/finance/net/).
2. .NET 개발 환경: 컴퓨터에 작동하는 .NET 개발 환경이 설정되어 있는지 확인하세요.
3. C#의 기본 이해: C# 프로그래밍 언어에 익숙하면 예제를 따라가는 데 도움이 됩니다.
## 네임스페이스 가져오기
C# 프로젝트에서 Aspose.Finance for .NET에서 제공하는 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 1단계: 출력 디렉터리 설정
XBRL 문서에 컨텍스트를 추가하기 전에 수정된 문서가 저장될 출력 디렉터리를 지정합니다.
```csharp
string outputDir = "Your Output Directory";
```
 바꾸다`"Your Output Directory"` 시스템에서 원하는 경로로.
## 2단계: XBRL 문서 생성
 인스턴스화`XbrlDocument` XBRL 문서에 사용할 객체:
```csharp
XbrlDocument document = new XbrlDocument();
```
이 객체는 조작될 XBRL 문서를 나타냅니다.
## 3단계: XBRL 인스턴스 추가
문서에 XBRL 인스턴스를 추가합니다. 각 인스턴스에는 특정 보고 기간에 대한 데이터가 포함됩니다.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
이 단계에서는 문서 내에서 XBRL 인스턴스를 초기화합니다.
## 4단계: 컨텍스트 기간 및 엔터티 정의
XBRL 인스턴스에 대한 컨텍스트 기간 및 엔티티를 생성합니다.
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
보고 요구 사항에 따라 기간 및 엔터티 세부 정보를 지정합니다.
## 5단계: 컨텍스트 생성
이전 단계에서 정의한 기간과 엔터티를 사용하여 컨텍스트를 구성합니다.
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
이 컨텍스트는 임시 및 엔터티 관련 정보를 캡슐화합니다.
## 6단계: XBRL 인스턴스에 컨텍스트 추가
이전 단계에서 생성된 컨텍스트를 XBRL 인스턴스와 연결합니다.
```csharp
xbrlInstance.Contexts.Add(context);
```
이 단계에서는 컨텍스트를 XBRL 인스턴스에 연결하여 데이터에 관련 컨텍스트 정보를 제공합니다.
## 7단계: 문서 저장
수정된 XBRL 문서를 지정된 출력 디렉토리에 저장합니다.
```csharp
document.Save(outputDir + @"document3.xbrl");
```
그러면 추가된 컨텍스트와 함께 XBRL 문서가 저장되어 프로세스가 마무리됩니다.
## 결론
다음 단계를 수행하면 Aspose.Finance for .NET을 사용하여 XBRL 문서에 컨텍스트를 효과적으로 추가할 수 있습니다. 이는 재무 데이터의 명확성과 유용성을 향상시켜 정확한 분석과 보고를 촉진합니다.
## 자주 묻는 질문
### .NET용 Aspose.Finance는 대규모 XBRL 문서를 처리할 수 있습니까?
.NET용 Aspose.Finance는 대규모 데이터 세트를 포함하여 다양한 크기의 XBRL 문서를 처리하도록 최적화되어 있습니다.
### .NET용 Aspose.Finance에 사용할 수 있는 평가판이 있습니까?
예, 공식 Aspose 웹사이트에서 무료 평가판을 다운로드할 수 있습니다.
### .NET용 Aspose.Finance는 XBRL 외에 다른 재무 보고 표준을 지원합니까?
Aspose.Finance는 주로 XBRL 관련 기능에 중점을 두고 있지만 다른 재무 형식에 대한 지원도 제공합니다.
### 특정 요구 사항에 따라 컨텍스트 정보를 사용자 정의할 수 있습니까?
물론 .NET용 Aspose.Finance는 필요에 맞게 컨텍스트 정보를 사용자 정의할 수 있는 유연성을 제공합니다.
### .NET용 Aspose.Finance에 대한 추가 지원이나 리소스는 어디서 찾을 수 있나요?
Aspose.Finance 포럼을 방문하여 커뮤니티의 도움을 받거나 문서에서 포괄적인 지침을 탐색할 수 있습니다.