---
title: XBRL 문서에 스키마 참조 추가
linktitle: XBRL 문서에 스키마 참조 추가
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 XBRL 문서에 스키마 참조를 추가하는 방법을 알아보세요. 지금 바로 금융 데이터 처리를 간소화하세요!
type: docs
weight: 15
url: /ko/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## .NET용 Aspose.Finance 소개
Aspose.Finance for .NET은 .NET 애플리케이션 내에서 금융 문서와 데이터를 처리하고 조작하기 위한 포괄적인 기능을 제공하는 강력한 라이브러리입니다. 회계 소프트웨어, 재무 분석 도구 또는 기타 금융 애플리케이션을 구축하는 경우 Aspose.Finance for .NET은 개발 프로세스를 간소화할 수 있는 광범위한 기능을 제공합니다.
## 전제 조건
.NET용 Aspose.Finance를 사용하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
### 1. 비주얼 스튜디오 설치
시스템에 Visual Studio가 설치되어 있는지 확인하십시오. 마이크로소프트 공식 홈페이지에서 다운로드하여 설치할 수 있습니다.
### 2. Aspose.Finance 라이센스 취득
.NET용 Aspose.Finance의 모든 기능을 활용하려면 유효한 라이센스를 취득해야 합니다. 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy) 또는 테스트 목적으로 임시 라이선스를 선택하세요.
### 3. .NET용 Aspose.Finance 다운로드 및 참조
 다음에서 .NET용 Aspose.Finance 라이브러리를 다운로드하세요.[릴리스 페이지](https://releases.aspose.com/finance/net/) .NET 프로젝트에서 참조하세요.
### 4. 문서 및 지원 액세스
 다음을 참조하세요.[API 문서](https://reference.aspose.com/finance/net/) .NET용 Aspose.Finance 사용에 대한 자세한 내용은 또한 Aspose.Finance 커뮤니티에서 도움을 구할 수 있습니다.[지원 포럼](https://forum.aspose.com/c/finance/43).
## 네임스페이스 가져오기
필요한 네임스페이스를 .NET 프로젝트로 가져오는 것부터 시작해 보겠습니다.
## 1단계: Aspose.Finance 네임스페이스 추가
```csharp
using Aspose.Finance.Xbrl;
using System;
```
이 네임스페이스에는 XBRL 문서 및 데이터 작업을 위한 클래스와 메소드가 포함되어 있습니다.
이제 제공된 예제를 여러 단계로 나누어 .NET용 Aspose.Finance를 사용하여 XBRL 문서에 스키마 참조를 추가하는 방법을 이해하겠습니다.
## 1단계: 소스 및 출력 디렉터리 정의
```csharp
// 소스 디렉터리
string sourceDir = "Your Source Directory";
// 출력 디렉토리
string outputDir = "Your Output Directory";
```
 바꾸다`"Your Source Directory"` 그리고`"Your Output Directory"`소스 및 출력 디렉터리에 대한 실제 경로를 각각 사용합니다.
## 2단계: XBRL 문서 생성
```csharp
XbrlDocument document = new XbrlDocument();
```
그러면 XBRL 문서의 새 인스턴스가 생성됩니다.
## 3단계: XBRL 인스턴스에 액세스
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
그러면 문서에서 XBRL 인스턴스 컬렉션을 검색하고 여기에 새 인스턴스를 추가합니다.
## 4단계: 스키마 참조 추가
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
 그러면 XBRL 인스턴스에 스키마 참조가 추가됩니다. 바꾸다`"schema.xsd"` 스키마 파일의 실제 이름,`"example"` 적절한 접두사를 사용하고`"http://example.com/xbrl/taxonomy"` 대상 네임스페이스 URI를 사용합니다.
## 5단계: 문서 저장
```csharp
document.Save(outputDir + @"document2.xbrl");
```
이렇게 하면 수정된 XBRL 문서가 지정된 출력 디렉터리에 저장됩니다.
## 결론
결론적으로 Aspose.Finance for .NET은 .NET 애플리케이션에서 재무 문서 및 데이터를 처리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 Aspose.Finance를 프로젝트에 쉽게 통합하고 XBRL 문서를 효율적으로 조작할 수 있습니다.
## 자주 묻는 질문
 (자주 묻는 질문)
### 1. 라이선스 없이 .NET용 Aspose.Finance를 사용할 수 있나요?
아니요, .NET용 Aspose.Finance의 모든 기능을 활용하려면 유효한 라이센스가 필요합니다. 그러나 테스트 목적으로 임시 라이센스를 얻을 수 있습니다.
### 2. Aspose.Finance는 회계 소프트웨어 구축에 적합합니까?
예, Aspose.Finance는 재무 데이터 처리를 위한 포괄적인 기능을 제공하므로 회계 소프트웨어 및 관련 애플리케이션을 구축하는 데 이상적입니다.
### 3. Aspose.Finance에 대한 지원은 어디서 찾을 수 있나요?
공식 지원 포럼에서 Aspose.Finance 커뮤니티의 도움을 구할 수 있습니다.
### 4. 스키마 참조 접두사를 맞춤설정할 수 있나요?
예, .NET용 Aspose.Finance를 사용하여 XBRL 문서에 스키마 참조를 추가할 때 적합한 접두사를 선택할 수 있습니다.
### 5. Aspose.Finance는 XBRL 외에 다른 금융 형식을 지원합니까?
예, Aspose.Finance는 다양한 금융 형식과 표준을 지원하여 다양한 금융 애플리케이션에 원활하게 통합할 수 있습니다.