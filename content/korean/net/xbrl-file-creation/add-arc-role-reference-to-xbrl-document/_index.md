---
title: XBRL 문서에 ARC 역할 참조 추가
linktitle: XBRL 문서에 ARC 역할 참조 추가
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 XBRL 문서를 효율적으로 조작하는 방법을 알아보세요. 단계별 지침을 통해 손쉽게 ARC 역할 참조를 추가하세요.
type: docs
weight: 10
url: /ko/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## 소개
재무 데이터 관리 및 보고 분야에서 XBRL(eXtensible Business Reporting Language)은 중요한 역할을 합니다. 이는 재무 정보가 전달되고 교환되는 방식을 표준화하여 일관성, 정확성 및 효율성을 보장합니다. 그러나 특히 특정 역할과 참조를 통합할 때 XBRL 문서를 조작하려면 기본 메커니즘에 대한 미묘한 이해가 필요합니다. 이 자습서에서는 .NET용 Aspose.Finance를 사용하여 XBRL 문서에 ARC 역할 참조를 추가하는 작업 중 하나에 중점을 둡니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
### 환경설정
1.  .NET용 Aspose.Finance 설치: 다음에서 .NET용 Aspose.Finance 라이브러리를 다운로드하여 설치하세요.[릴리스](https://releases.aspose.com/finance/net/).
   
2. 개발 환경: Visual Studio 또는 기타 선호하는 IDE를 사용하여 개발 환경을 설정합니다.
## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 가져와야 합니다.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 1단계: 소스 및 출력 디렉터리 정의
계속하기 전에 XBRL 파일이 위치하고 저장될 소스 및 출력 디렉터리를 각각 지정합니다.
```csharp
// 소스 디렉터리
string sourceDir = "Your Source Directory";
// 출력 디렉토리
string outputDir = "Your Output Directory";
```
## 2단계: XBRL 문서 생성
 인스턴스화`XbrlDocument` XBRL 데이터로 작업할 개체입니다.
```csharp
XbrlDocument document = new XbrlDocument();
```
## 3단계: XbrlInstance 컬렉션에 액세스
문서 내의 XBRL 인스턴스 컬렉션에 액세스합니다.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## 4단계: XbrlInstance 추가
컬렉션에 새 XBRL 인스턴스를 추가합니다.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 5단계: 스키마 참조 추가
소스 디렉터리, 네임스페이스 접두사 및 URI를 지정하여 XBRL 인스턴스에 스키마 참조를 포함합니다.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## 6단계: ArcroleType 검색
 검색`ArcroleType` 특정 URI를 기반으로 합니다.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## 7단계: ArcroleReference 추가
 만약`ArcroleType` 발견되면`ArcroleReference` XBRL 인스턴스의 아크롤 참조에 추가합니다.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## 8단계: 문서 저장
수정된 XBRL 문서를 지정된 출력 디렉토리에 저장합니다.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## 결론
이 튜토리얼에서는 .NET용 Aspose.Finance를 사용하여 XBRL 문서에 ARC 역할 참조를 추가하는 방법을 살펴보았습니다. 이러한 단계별 지침을 따르고 Aspose.Finance의 기능을 활용하면 XBRL 데이터를 효율적으로 관리하고 조작하여 특정 요구 사항을 충족할 수 있습니다.
## 자주 묻는 질문
### XBRL이란 무엇입니까?
XBRL은 비즈니스 및 재무 데이터의 전자 통신을 위한 표준화된 언어인 eXtensible Business Reporting Language의 약자입니다.
### XBRL이 중요한 이유는 무엇입니까?
XBRL은 재무 정보 교환 및 분석에서 일관성, 정확성 및 효율성을 보장하여 규제 기관, 분석가 및 기업에 이익을 줍니다.
### Aspose.Finance는 복잡한 XBRL 작업을 처리할 수 있습니까?
예, Aspose.Finance는 역할 참조 및 분류 관리와 같은 복잡한 작업 처리를 포함하여 XBRL 문서 작업을 위한 강력한 기능을 제공합니다.
### Aspose.Finance는 다른 .NET 라이브러리와 호환됩니까?
예, Aspose.Finance는 다른 .NET 라이브러리와 원활하게 통합되어 재무 데이터 조작 및 보고에 대한 광범위한 지원을 제공합니다.
### Aspose.Finance에 대한 추가 지원은 어디서 찾을 수 있나요?
 추가 지원을 받으려면 다음을 방문하세요.[Aspose.Finance 지원 페이지](https://forum.aspose.com/c/finance/43).