---
title: XBRL 문서에 역할 참조 추가
linktitle: XBRL 문서에 역할 참조 추가
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 XBRL 문서에 역할 참조를 추가하는 방법을 알아보세요. 이 튜토리얼을 통해 .NET 애플리케이션의 재무 보고를 단순화하세요.
type: docs
weight: 14
url: /ko/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL(eXtensible Business Reporting Language)은 특히 재무 보고에서 비즈니스 정보 교환을 위한 표준이 되었습니다. .NET용 Aspose.Finance는 .NET 애플리케이션에서 XBRL 문서 작업을 단순화합니다. 이 튜토리얼은 .NET용 Aspose.Finance를 사용하여 XBRL 문서에 역할 참조를 추가하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
### 1. .NET용 Aspose.Finance 설치
개발 환경에 Aspose.Finance for .NET이 설치되어 있는지 확인하세요. 아직 다운로드하지 않았다면 다음에서 다운로드하세요.[릴리스](https://releases.aspose.com/finance/net/) 설치 지침을 따르십시오.
### 2. 개발 환경 설정
.NET 개발을 위한 작업 개발 환경이 있는지 확인하세요. 여기에는 시스템에 설치된 Visual Studio 및 .NET Framework와 같은 호환 IDE가 포함됩니다.
## 네임스페이스 가져오기
Aspose.Finance for .NET에서 제공하는 기능에 액세스하려면 필요한 네임스페이스를 .NET 애플리케이션으로 가져오는 것부터 시작하세요.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## 4단계: 역할 유형 검색 및 역할 참조 추가
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
해당 URI를 사용하여 역할 유형을 검색하고 XBRL 인스턴스에 역할 참조를 추가합니다.
## 5단계: 문서 저장
```csharp
document.Save(outputDir + @"document7.xbrl");
```
XBRL 문서를 출력 디렉터리에 저장합니다.
## 결론
XBRL 문서에 역할 참조를 추가하는 것은 문서 내의 다양한 요소의 역할을 정의하는 데 중요합니다. .NET용 Aspose.Finance는 이 작업을 수행하는 간단한 방법을 제공하여 개발자가 .NET 애플리케이션에서 XBRL 문서를 효율적으로 작업할 수 있도록 지원합니다.
## 자주 묻는 질문
### 모든 .NET 애플리케이션에서 Aspose.Finance for .NET을 사용할 수 있나요?
예, .NET용 Aspose.Finance는 ASP.NET, WinForms 및 콘솔 애플리케이션을 포함한 모든 .NET 애플리케이션과 호환됩니다.
### .NET용 Aspose.Finance는 무료로 사용할 수 있나요?
 .NET용 Aspose.Finance는 상용 라이브러리입니다. 무료 평가판을 다운로드하여 기능을 평가할 수 있으며 라이센스는 다음에서 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### .NET용 Aspose.Finance는 XBRL 외에 다른 재무 보고 형식을 지원합니까?
.NET용 Aspose.Finance는 주로 XBRL 관련 기능에 중점을 둡니다. 그러나 Aspose는 다양한 금융 형식으로 작업할 수 있는 다른 라이브러리를 제공합니다.
### .NET용 Aspose.Finance에 대한 지원을 어떻게 받을 수 있나요?
 다음을 통해 .NET용 Aspose.Finance에 대한 지원을 받을 수 있습니다.[법정](https://forum.aspose.com/c/finance/43)에서 질문을 하고 다른 사용자 및 지원 담당자와 상호 작용할 수 있습니다.
### .NET용 Aspose.Finance에 대한 임시 라이선스를 얻을 수 있나요?
 예, .NET용 Aspose.Finance의 임시 라이선스를 테스트 목적으로 사용할 수 있습니다. 하나를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).