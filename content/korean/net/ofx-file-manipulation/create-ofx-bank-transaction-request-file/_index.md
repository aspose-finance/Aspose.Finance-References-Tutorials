---
title: OFX 은행 거래 요청 파일 생성
linktitle: OFX 은행 거래 요청 파일 생성
second_title: Aspose.Finance.NET API
description: 자세한 단계별 가이드를 통해 .NET용 Aspose.Finance를 사용하여 OFX 은행 거래 요청 파일을 생성하는 방법을 알아보세요. #양도 #금융
type: docs
weight: 12
url: /ko/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
OFX 은행 거래 요청 파일을 생성하는 것은 어려워 보일 수 있지만 올바른 도구와 지침을 사용하면 간단한 프로세스가 될 수 있습니다. 이 튜토리얼에서는 .NET용 Aspose.Finance를 사용하여 OFX 은행 거래 요청 파일을 생성하는 각 단계를 안내합니다. 사전 요구 사항과 필요한 네임스페이스를 다루고, 쉽게 따라할 수 있도록 자세한 단계별 가이드를 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 준비해야 할 몇 가지 사항이 있습니다.
1.  Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[공식 웹 사이트](https://visualstudio.microsoft.com/).
2.  .NET용 Aspose.Finance: .NET용 Aspose.Finance 라이브러리가 필요합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/finance/net/).
3. 기본 C# 지식: C# 프로그래밍의 기본 사항을 이해하면 코드 예제를 따라가는 데 도움이 됩니다.
이러한 전제조건을 갖추고 나면 시작할 준비가 된 것입니다!
## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 가져오겠습니다. 이러한 네임스페이스는 OFX 은행 거래 요청 파일을 생성하는 데 필요한 클래스와 메서드에 액세스하는 데 중요합니다.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## 1단계: 작업 디렉터리 설정
OFX 요청 파일 생성을 시작하기 전에 파일이 저장될 출력 디렉터리를 지정해야 합니다.
```csharp
string outputDir = "Your Output Directory";
```
 바꾸다`"Your Output Directory"` 생성된 파일을 저장하려는 디렉터리의 경로를 사용하세요.
## 2단계: OFX 요청 문서 생성
 다음으로, 인스턴스를 생성해야 합니다.`OfxRequestDocument` 수업. 이 클래스는 OFX 요청의 컨테이너 역할을 합니다.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## 3단계: 로그인 요청 설정
사인온 요청은 사용자를 인증하고 OFX 세션을 시작하는 데 필수적입니다. 사인온 요청 메시지를 설정하고 클라이언트 날짜, 사용자 ID, 비밀번호, 금융 기관 정보 등 필요한 세부 정보를 입력합니다.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## 4단계: 은행 요청 메시지 설정
이제 사인온 요청이 설정되었으므로 은행 요청 메시지 작성으로 넘어갑니다. 이 메시지에는 은행 계좌 세부정보와 거래 명세서 요청이 포함됩니다.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## 5단계: 거래 세부정보 포함
 특정 거래를 검색하려면 날짜 범위와 요청에 거래를 포함할지 여부를 지정해야 합니다. 이는 다음을 설정하여 수행됩니다.`IncTransaction` 물체.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## 6단계: OFX 요청 문서 저장
마지막으로 OFX 요청 문서를 XML 및 SGML 형식으로 저장합니다. 이렇게 하면 두 형식 중 하나를 사용할 수 있는 다양한 시스템과의 호환성이 보장됩니다.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## 7단계: 성공적인 실행 확인
프로세스가 성공적으로 실행되었는지 확인하기 위해 콘솔에 메시지를 인쇄할 수 있습니다.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## 결론
Aspose.Finance for .NET을 사용하여 OFX 은행 거래 요청 파일을 생성하는 것은 요청 문서 설정, 로그인 및 은행 요청 메시지 구성, 거래 세부 정보 지정 및 문서 저장을 포함하는 체계적인 프로세스입니다. 이 단계별 가이드를 따르면 특정 요구 사항에 맞는 OFX 요청 파일을 효율적으로 생성할 수 있습니다.
## 자주 묻는 질문
### 1. OFX 파일이란 무엇입니까?
OFX(Open Financial Exchange) 파일은 기관과 사용자 간에 금융 데이터를 교환하는 데 사용되는 표준 형식입니다. 은행 명세서, 거래 및 기타 금융 활동에 널리 사용됩니다.
### 2. Aspose.Finance for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Finance for .NET은 C#과 같은 .NET 언어와 함께 사용하도록 특별히 설계되었습니다. 그러나 모든 .NET 지원 환경에서 사용할 수 있습니다.
### 3. Aspose.Finance for .NET에 대한 무료 평가판이 있습니까?
예, 다음에서 .NET용 Aspose.Finance 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### 4. .NET용 Aspose.Finance에 대한 지원을 받으려면 어떻게 해야 합니까?
 Aspose 커뮤니티 및 기술팀을 통해 지원을 받을 수 있습니다.[지원 포럼](https://forum.aspose.com/c/finance/43).
### 5. .NET용 Aspose.Finance에 대한 임시 라이선스를 얻을 수 있나요?
 예, Aspose는[임시면허](https://purchase.aspose.com/temporary-license/) 제품을 평가하는 데 사용할 수 있는 정보입니다.