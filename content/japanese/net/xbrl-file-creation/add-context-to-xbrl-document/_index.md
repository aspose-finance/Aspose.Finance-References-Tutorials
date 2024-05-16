---
title: XBRL ドキュメントにコンテキストを追加する
linktitle: XBRL ドキュメントにコンテキストを追加する
second_title: Aspose.Finance .NET API
description: Aspose.Finance を使用して .NET の XBRL ドキュメントにコンテキストを追加し、財務レポートを効率化する方法を学びます。#Aspose #Finance #XBRL
type: docs
weight: 11
url: /ja/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## 導入
財務報告の分野では、XBRL (eXtensible Business Reporting Language) がビジネス情報の交換の標準化において重要な役割を果たしています。XBRL ドキュメントにコンテキストを追加することは、ドキュメントに含まれるデータの整合性と関連性を保証するために不可欠です。Aspose.Finance for .NET を使用すると、このプロセスが合理化され、効率化され、開発者はコンテキストを XBRL ドキュメントにシームレスに組み込むことができます。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. Aspose.Finance for .NETライブラリ: Aspose.Finance for .NETライブラリを以下のサイトからダウンロードしてインストールします。[リリース](https://releases.aspose.com/finance/net/).
2. .NET 開発環境: マシンに動作する .NET 開発環境が設定されていることを確認します。
3. C# の基本的な理解: C# プログラミング言語の知識があると、例を理解するのに役立ちます。
## 名前空間のインポート
C# プロジェクトで、Aspose.Finance for .NET によって提供される機能にアクセスするために必要な名前空間をインポートします。
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## ステップ1: 出力ディレクトリを設定する
XBRL ドキュメントにコンテキストを追加する前に、変更されたドキュメントを保存する出力ディレクトリを指定します。
```csharp
string outputDir = "Your Output Directory";
```
交換する`"Your Output Directory"`システム上の目的のパスを入力します。
## ステップ2: XBRLドキュメントを作成する
インスタンス化する`XbrlDocument`XBRL ドキュメントを操作するオブジェクト:
```csharp
XbrlDocument document = new XbrlDocument();
```
このオブジェクトは、操作される XBRL ドキュメントを表します。
## ステップ3: XBRLインスタンスを追加する
ドキュメントに XBRL インスタンスを追加します。各インスタンスには、特定のレポート期間のデータが含まれます。
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
このステップでは、ドキュメント内の XBRL インスタンスを初期化します。
## ステップ4: コンテキスト期間とエンティティを定義する
XBRL インスタンスのコンテキスト期間とエンティティを作成します。
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
レポート要件に応じて期間とエンティティの詳細を指定します。
## ステップ5: コンテキストを作成する
前の手順で定義した期間とエンティティを使用してコンテキストを構築します。
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
このコンテキストは、時間的およびエンティティ関連の情報をカプセル化します。
## ステップ6: XBRLインスタンスにコンテキストを追加する
前の手順で作成したコンテキストを XBRL インスタンスに関連付けます。
```csharp
xbrlInstance.Contexts.Add(context);
```
このステップでは、コンテキストを XBRL インスタンスにリンクし、データに関連するコンテキスト情報を提供します。
## ステップ7: ドキュメントを保存する
変更した XBRL ドキュメントを指定された出力ディレクトリに保存します。
```csharp
document.Save(outputDir + @"document3.xbrl");
```
これによりプロセスが完了し、追加されたコンテキストを含む XBRL ドキュメントが保存されます。
## 結論
これらの手順に従うことで、Aspose.Finance for .NET を使用して XBRL ドキュメントに効果的にコンテキストを追加できます。これにより、財務データの明瞭性と使いやすさが向上し、正確な分析とレポート作成が容易になります。
## よくある質問
### Aspose.Finance for .NET は大規模な XBRL ドキュメントを処理できますか?
Aspose.Finance for .NET は、大規模なデータセットを含むさまざまなサイズの XBRL ドキュメントを処理するように最適化されています。
### Aspose.Finance for .NET の試用版はありますか?
はい、Aspose の公式 Web サイトから無料試用版をダウンロードできます。
### Aspose.Finance for .NET は、XBRL 以外の財務報告標準もサポートしていますか?
Aspose.Finance は主に XBRL 関連の機能に重点を置いていますが、他の財務形式のサポートも提供しています。
### 特定の要件に応じてコンテキスト情報をカスタマイズできますか?
はい、Aspose.Finance for .NET は、ニーズに合わせてコンテキスト情報をカスタマイズする柔軟性を提供します。
### Aspose.Finance for .NET の追加サポートやリソースはどこで見つかりますか?
コミュニティからのサポートが必要な場合は、Aspose.Finance フォーラムにアクセスしてください。また、包括的なガイダンスについてはドキュメントを参照してください。