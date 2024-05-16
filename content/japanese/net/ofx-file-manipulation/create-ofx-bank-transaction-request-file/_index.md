---
title: OFX銀行取引リクエストファイルの作成
linktitle: OFX銀行取引リクエストファイルの作成
second_title: Aspose.Finance .NET API
description: 詳細なステップバイステップ ガイドを使用して、Aspose.Finance for .NET を使用して OFX 銀行取引リクエスト ファイルを作成する方法を学びます。#Aspose #Finance
type: docs
weight: 12
url: /ja/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
OFX 銀行取引リクエスト ファイルの作成は困難に思えるかもしれませんが、適切なツールとガイダンスがあれば、簡単なプロセスになります。このチュートリアルでは、Aspose.Finance for .NET を使用して OFX 銀行取引リクエスト ファイルを生成する手順を 1 つ 1 つ説明します。前提条件、必要な名前空間について説明し、簡単に従うことができるように詳細なステップ バイ ステップ ガイドを提供します。
## 前提条件
チュートリアルに進む前に、準備しておく必要があるものがいくつかあります。
1.  Visual Studio: お使いのコンピュータにVisual Studioがインストールされていることを確認してください。[公式ウェブサイト](https://visualstudio.microsoft.com/).
2. Aspose.Finance for .NET: Aspose.Finance for .NETライブラリが必要です。こちらからダウンロードできます。[ここ](https://releases.aspose.com/finance/net/).
3. C# の基本知識: C# プログラミングの基礎を理解すると、コード例を理解しやすくなります。
これらの前提条件が満たされたら、開始する準備は完了です。
## 名前空間のインポート
まず、必要な名前空間をインポートしましょう。これらの名前空間は、OFX 銀行取引リクエスト ファイルを作成するために必要なクラスとメソッドにアクセスするために重要です。
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## ステップ1: 作業ディレクトリを設定する
OFX リクエスト ファイルの作成を開始する前に、ファイルを保存する出力ディレクトリを指定する必要があります。
```csharp
string outputDir = "Your Output Directory";
```
交換する`"Your Output Directory"`生成されたファイルを保存するディレクトリへのパスを指定します。
## ステップ2: OFXリクエストドキュメントを作成する
次に、`OfxRequestDocument`クラス。このクラスは OFX リクエストのコンテナーとして機能します。
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## ステップ3: サインオンリクエストを設定する
サインオン要求は、ユーザーを認証し、OFX セッションを開始するために不可欠です。サインオン要求メッセージを設定し、クライアントの日付、ユーザー ID、パスワード、金融機関情報などの必要な詳細を入力します。
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
## ステップ4: 銀行リクエストメッセージを設定する
サインオン要求が設定されたので、銀行要求メッセージの作成に進みます。このメッセージには、銀行口座の詳細と取引明細書要求が含まれます。
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
## ステップ5: 取引の詳細を入力する
特定の取引を取得するには、日付範囲と、リクエストに取引を含めるかどうかを指定する必要があります。これは、`IncTransaction`物体。
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## ステップ6: OFXリクエストドキュメントを保存する
最後に、OFX リクエスト ドキュメントを XML 形式と SGML 形式の両方で保存します。これにより、いずれかの形式を使用する可能性のあるさまざまなシステムとの互換性が確保されます。
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## ステップ7: 実行が成功したことを確認する
プロセスが正常に実行されたことを確認するには、コンソールにメッセージを出力します。
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## 結論
Aspose.Finance for .NET を使用して OFX 銀行取引リクエスト ファイルを作成するには、リクエスト ドキュメントの設定、サインオンと銀行リクエスト メッセージの構成、トランザクションの詳細の指定、ドキュメントの保存といった、系統立ったプロセスが必要です。このステップ バイ ステップ ガイドに従うことで、特定のニーズに合わせた OFX リクエスト ファイルを効率的に生成できます。
## よくある質問
### 1. OFX ファイルとは何ですか?
OFX (Open Financial Exchange) ファイルは、金融機関とユーザーの間で金融データを交換するために使用される標準形式です。銀行取引明細書、取引、その他の金融活動に広く使用されています。
### 2. Aspose.Finance for .NET を他のプログラミング言語で使用できますか?
Aspose.Finance for .NET は、C# などの .NET 言語で使用するために特別に設計されています。ただし、.NET がサポートされている任意の環境で使用できます。
### 3. Aspose.Finance for .NET の無料試用版はありますか?
はい、Aspose.Finance for .NETの無料トライアルをこちらからダウンロードできます。[ここ](https://releases.aspose.com/).
### 4. Aspose.Finance for .NET のサポートを受けるにはどうすればよいですか?
 Asposeコミュニティと技術チームからのサポートは、[サポートフォーラム](https://forum.aspose.com/c/finance/43).
### 5. Aspose.Finance for .NET の一時ライセンスを取得できますか?
はい、Asposeは[一時ライセンス](https://purchase.aspose.com/temporary-license/)製品を評価するために使用できます。