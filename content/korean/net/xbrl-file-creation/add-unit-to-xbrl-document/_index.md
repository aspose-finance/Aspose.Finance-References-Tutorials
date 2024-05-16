---
title: XBRL 문서에 단위 추가
linktitle: XBRL 문서에 단위 추가
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 XBRL 문서에 단위를 쉽게 추가하는 방법을 알아보세요. 오늘 귀하의 금융 데이터 처리 능력을 강화하십시오!
type: docs
weight: 16
url: /ko/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
.NET 애플리케이션 내에서 효율적인 재무 문서 조작을 위한 관문인 Aspose.Finance for .NET의 세계에 오신 것을 환영합니다. 회계 소프트웨어, 재무 분석 도구 또는 기타 금융 애플리케이션을 구축하는 경우 Aspose.Finance for .NET은 개발 프로세스를 간소화하는 포괄적인 기능 세트를 제공합니다.
## 전제 조건
.NET용 Aspose.Finance의 강력한 기능을 활용하기 전에 필요한 전제 조건이 갖추어져 있는지 확인하겠습니다.
### 1. 비주얼 스튜디오 설치
시스템에 Visual Studio가 설치되어 있는지 확인하세요. 그렇지 않은 경우 Microsoft 공식 웹사이트에서 다운로드하여 설치할 수 있습니다.
### 2. 라이센스 취득
 .NET용 Aspose.Finance의 잠재력을 최대한 활용하려면 유효한 라이센스가 필요합니다. 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy) 또는 테스트 목적으로 임시 라이선스를 선택하세요.
### 3. .NET용 Aspose.Finance 다운로드 및 참조
 다음에서 .NET용 Aspose.Finance 라이브러리를 다운로드하세요.[릴리스 페이지](https://releases.aspose.com/finance/net/) .NET 프로젝트에서 참조하세요.
### 4. 문서 및 지원 액세스
 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/finance/net/).NET용 Aspose.Finance 활용에 대한 자세한 내용은 또한 Aspose.Finance 커뮤니티에서 도움을 구할 수 있습니다.[지원 포럼](https://forum.aspose.com/c/finance/43).
## 네임스페이스 가져오기
이제 필요한 네임스페이스를 .NET 프로젝트로 가져오겠습니다.
## 1단계: Aspose.Finance 네임스페이스 추가
```csharp
using Aspose.Finance.Xbrl;
using System;
```
이 네임스페이스에는 XBRL 문서 및 데이터 작업에 필수적인 클래스와 메소드가 포함되어 있습니다.
.NET용 Aspose.Finance를 사용하여 XBRL 문서에 단위를 추가하는 방법을 이해하기 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
// 출력 디렉토리
string outputDir = "Your Output Directory";
```
 바꾸다`"Your Output Directory"` 원하는 출력 디렉토리의 실제 경로를 사용하십시오.
## 2단계: XBRL 문서 생성
```csharp
XbrlDocument document = new XbrlDocument();
```
그러면 XBRL 문서의 새 인스턴스가 초기화됩니다.
## 3단계: XBRL 인스턴스에 액세스
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
그러면 문서에서 XBRL 인스턴스 컬렉션을 검색하고 여기에 새 인스턴스를 추가합니다.
## 4단계: 단위 추가
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
그러면 새 측정 단위(이 경우 USD)가 생성되어 XBRL 인스턴스에 추가됩니다. 필요에 따라 통화 코드와 네임스페이스 URI를 조정할 수 있습니다.
## 5단계: 문서 저장
```csharp
document.Save(outputDir + @"document4.xbrl");
```
이렇게 하면 수정된 XBRL 문서가 지정된 출력 디렉터리에 저장됩니다.
## 결론
결론적으로 .NET용 Aspose.Finance는 개발자가 .NET 애플리케이션 내에서 재무 문서와 데이터를 손쉽게 조작할 수 있도록 해줍니다. 이 튜토리얼에 설명된 단계를 따르면 Aspose.Finance for .NET을 프로젝트에 원활하게 통합하고 재무 처리 기능을 향상시킬 수 있습니다.
## 자주 묻는 질문
### 1. 라이선스 없이 .NET용 Aspose.Finance를 사용할 수 있나요?
아니요, .NET용 Aspose.Finance의 전체 기능을 잠금 해제하려면 유효한 라이센스가 필요합니다. 그러나 테스트 목적으로 임시 라이센스를 사용할 수 있습니다.
### 2. Aspose.Finance for .NET은 회계 소프트웨어 구축에 적합합니까?
예, Aspose.Finance for .NET은 회계 소프트웨어 및 관련 금융 애플리케이션 구축에 맞춰진 강력한 기능을 제공합니다.
### 3. .NET용 Aspose.Finance에 대한 지원은 어디서 찾을 수 있나요?
지원 포럼에서 Aspose.Finance 커뮤니티로부터 도움을 구할 수 있습니다.
### 4. XBRL 문서에서 측정 단위를 사용자 정의할 수 있습니까?
예, Aspose.Finance for .NET을 사용하여 XBRL 문서에 사용자 정의 측정 단위를 생성하고 추가할 수 있습니다.
### 5. .NET용 Aspose.Finance는 여러 통화를 지원합니까?
예, .NET용 Aspose.Finance는 다양한 통화를 지원하므로 다양한 금융 데이터 처리가 가능합니다.