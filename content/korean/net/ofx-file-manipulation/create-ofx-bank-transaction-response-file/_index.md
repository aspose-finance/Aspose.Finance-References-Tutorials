---
title: OFX 은행 거래 응답 파일 생성
linktitle: OFX 은행 거래 응답 파일 생성
second_title: Aspose.Finance.NET API
description: .NET용 Aspose.Finance를 사용하여 OFX 은행 거래 응답 파일을 손쉽게 생성하는 방법을 알아보세요. 오늘 금융 데이터 교환을 간소화하세요!
type: docs
weight: 13
url: /ko/net/ofx-file-manipulation/create-ofx-bank-transaction-response-file/
---
## 소개
금융 데이터 처리 영역에서는 OFX(Open Financial Exchange) 은행 거래 응답 파일을 생성하는 것이 중요한 작업입니다. 이러한 파일은 거래 정보를 표준화된 형식으로 캡슐화하여 금융 기관과 소프트웨어 시스템 간의 원활한 교환을 촉진합니다. .NET용 Aspose.Finance는 .NET 프레임워크 내에서 OFX 은행 거래 응답 파일을 손쉽게 제작할 수 있는 강력한 솔루션을 제공합니다.
## 전제 조건
.NET용 Aspose.Finance를 사용하여 OFX 은행 거래 응답 파일 생성을 시작하기 전에 다음 전제 조건이 충족되는지 확인하세요.
### 1. .NET용 Aspose.Finance를 구하세요.
 먼저 공식 사이트에서 Aspose.Finance for .NET을 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/finance/net/).
### 2. 개발 환경 설정
호환 가능한 버전의 Visual Studio 및 .NET 프레임워크를 포함하여 적합한 개발 환경이 구성되어 있는지 확인하세요.
### 3. C#에 대한 기본 지식
이 자습서에서 설명하는 개념을 이해하려면 C# 프로그래밍 언어에 대한 기본적인 이해가 필요합니다.
## 네임스페이스 가져오기
.NET용 Aspose.Finance를 사용하여 OFX 은행 거래 응답 파일 제작을 시작하려면 필요한 네임스페이스를 가져옵니다.
## 1. Aspose.Finance 네임스페이스 가져오기
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
이제 제공된 예제를 여러 단계로 나누어 Aspose.Finance for .NET을 사용하여 OFX 은행 거래 응답 파일을 생성하는 과정을 안내해 보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDir = "Your Output Directory";
```
생성된 OFX 은행 거래 응답 파일을 저장할 디렉터리 경로를 지정합니다.
## 2단계: OFX 응답 문서 초기화
```csharp
OfxResponseDocument document = new OfxResponseDocument();
```
 새 인스턴스를 생성합니다.`OfxResponseDocument` OFX 응답 문서 구성을 시작하는 클래스입니다.
## 3단계: 로그인 응답 설정
```csharp
document.SignonResponseMessageSetV1 = new SignonResponseMessageSetV1();
```
 인스턴스화`SignonResponseMessageSetV1` OFX 문서 내에서 사인온 응답을 관리하는 클래스입니다.
## 4단계: 로그온 응답 세부 정보 설정
```csharp
SignonResponse signonResponse = new SignonResponse();
```
 새로 만들기`SignonResponse` 로그인 응답 세부정보를 캡슐화하는 개체입니다.
## 5단계: 로그온 응답 상태 설정
```csharp
signonResponse.Status = new Status();
signonResponse.Status.Code = "0";
signonResponse.Status.Severity = SeverityEnum.INFO;
signonResponse.Status.Message = "SUCCESS";
```
코드, 심각도 및 메시지를 지정하여 로그온 응답 상태를 구성합니다.
## 6단계: 금융 기관 세부정보 설정
```csharp
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
```
거래에 참여한 금융기관에 대한 정보를 제공하세요.
## 7단계: 세션 쿠키 설정
```csharp
signonResponse.SessionCookie = "11111111111111111";
```
인증 목적으로 세션 쿠키를 할당합니다.
## 8단계: 은행 응답 메시지 세트 추가
```csharp
document.BankResponseMessageSetV1 = new BankResponseMessageSetV1();
```
 인스턴스화`BankResponseMessageSetV1` 은행 응답 메시지를 관리하는 클래스입니다.
## 9단계: 명세서 거래 응답 추가
```csharp
StatementTransactionResponse stmtTransResponse = new StatementTransactionResponse();
document.BankResponseMessageSetV1.StatementTransactionResponses.Add(stmtTransResponse);
```
명세서 트랜잭션 응답 객체를 생성하고 이를 은행 응답 메시지 세트에 추가합니다.
## 10단계: 거래 세부정보 설정
```csharp
stmtTransResponse.TransactionUniqueId = "829631324";
stmtTransResponse.Status = new Status();
stmtTransResponse.Status.Code = "0";
stmtTransResponse.Status.Severity = SeverityEnum.INFO;
```
고유 식별자, 상태 등 거래별 세부정보를 구성합니다.
## 11단계: 은행 계좌 정보 추가
```csharp
stmtTransResponse.StatementResponse.BankAccountFrom = new BankAccount();
stmtTransResponse.StatementResponse.BankAccountFrom.BankId = "1111111";
stmtTransResponse.StatementResponse.BankAccountFrom.AccountId = "1111111111111";
stmtTransResponse.StatementResponse.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
거래에 관련된 은행 계좌에 대한 세부정보를 제공하세요.
## 12단계: 은행 거래 목록 추가
```csharp
stmtTransResponse.StatementResponse.BankTransactionList = new BankTransactionList();
stmtTransResponse.StatementResponse.BankTransactionList.StartDate = "20200601000000";
stmtTransResponse.StatementResponse.BankTransactionList.EndDate = "20200611000000";
```
은행 거래 목록을 생성하고 거래 시작일과 종료일을 지정합니다.
## 13단계: 명세서 거래 추가
```csharp
StatementTransaction transaction1 = new StatementTransaction();
//transaction1의 거래 내역
StatementTransaction transaction2 = new StatementTransaction();
// transaction2의 거래 세부정보
stmtTransResponse.StatementResponse.BankTransactionList.StatementTransactions.Add(transaction1);
stmtTransResponse.StatementResponse.BankTransactionList.StatementTransactions.Add(transaction2);
```
명세서 거래를 인스턴스화하고 세부정보를 입력한 후 은행 거래 목록에 추가합니다.
## 14단계: 원장 및 가용 잔액 설정
```csharp
stmtTransResponse.StatementResponse.LedgerBalance = new LedgerBalance();
stmtTransResponse.StatementResponse.LedgerBalance.BalanceAmount = "+2222.42";
stmtTransResponse.StatementResponse.LedgerBalance.DateAsOf = "20200611000000";
stmtTransResponse.StatementResponse.AvailableBalance = new AvailableBalance();
stmtTransResponse.StatementResponse.AvailableBalance.BalanceAmount = "+222222.42";
stmtTransResponse.StatementResponse.AvailableBalance.DateAsOf = "20200611000000";
```
은행 계좌와 연결된 원장 잔액과 사용 가능한 잔액을 지정합니다.
## 15단계: OFX 응답 파일 저장
```csharp
document.Save(outputDir + @"newOfxResponseBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxResponseBankStatement.sgml", OfxVersionEnum.V1x);
```
생성된 OFX 응답 파일을 각각 XML 및 SGML 형식으로 저장합니다.
## 결론
.NET용 Aspose.Finance를 사용하여 OFX 은행 거래 응답 파일을 생성하면 개발자가 금융 데이터 교환을 처리하는 간소화된 접근 방식을 얻을 수 있습니다. 이 문서에 설명된 단계별 가이드를 따르면 애플리케이션 요구 사항에 맞는 OFX 파일을 효율적으로 생성할 수 있습니다.
## 자주 묻는 질문
### 1. Aspose.Finance for .NET을 다른 금융 소프트웨어와 통합할 수 있나요?
예, Aspose.Finance for .NET은 다양한 금융 소프트웨어 솔루션과의 원활한 통합 기능을 제공하여 호환성과 상호 운용성을 보장합니다.
### 2. Aspose.Finance for .NET은 개인용과 기업용 모두에 적합합니까?
전적으로! 개인 개발자이든 대기업의 일원이든 상관없이 Aspose.Finance for .NET은 유연한 기능과 라이선스 옵션을 통해 다양한 사용자 요구 사항을 충족합니다.
### 3. Aspose.Finance for .NET을 사용하여 처리할 수 있는 거래 수에 제한이 있나요?
아니요, Aspose.Finance for .NET은 임의의 제한을 두지 않고 대량의 트랜잭션을 효율적으로 처리하도록 설계되었습니다. 몇 가지 거래를 처리하든 광범위한 금융 데이터를 관리하든 라이브러리는 최적의 성능과 확장성을 보장합니다.
### 4. Aspose.Finance for .NET에서 생성된 OFX 파일의 형식과 구조를 사용자 정의할 수 있습니까?
틀림없이! .NET용 Aspose.Finance는 광범위한 사용자 정의 옵션을 제공하므로 특정 요구 사항에 따라 OFX 파일의 형식, 구조 및 내용을 조정할 수 있습니다. 귀하의 애플리케이션이나 조직의 표준과 선호도에 맞게 다양한 매개변수를 쉽게 조정할 수 있습니다.
### 5. Aspose.Finance for .NET에 대한 기술 지원이 제공됩니까?
 예, .NET 사용자를 위한 Aspose.Finance에 대한 포괄적인 기술 지원이 제공됩니다. 당신은 액세스할 수 있습니다[법정](https://forum.aspose.com/c/finance/43) 도움을 구하고, 문제를 보고하고, 활발한 개발자 및 전문가 커뮤니티에 참여하세요.