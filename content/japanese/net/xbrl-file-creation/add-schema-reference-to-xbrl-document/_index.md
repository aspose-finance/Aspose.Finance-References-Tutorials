---
title: XBRL ドキュメントにスキーマ参照を追加する
linktitle: XBRL ドキュメントにスキーマ参照を追加する
second_title: Aspose.Finance .NET API
description: Aspose.Finance for .NET を使用して XBRL ドキュメントにスキーマ参照を追加する方法を学びます。今すぐ財務データ処理を効率化しましょう。
type: docs
weight: 15
url: /ja/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Aspose.Finance for .NET のご紹介
Aspose.Finance for .NET は、.NET アプリケーション内で財務文書やデータを処理および操作するための包括的な機能を提供する強力なライブラリです。会計ソフトウェア、財務分析ツール、またはその他の財務アプリケーションを構築する場合でも、Aspose.Finance for .NET は開発プロセスを効率化する幅広い機能を提供します。
## 前提条件
Aspose.Finance for .NET の使用を開始する前に、次の前提条件が設定されていることを確認してください。
### 1. Visual Studioをインストールする
システムに Visual Studio がインストールされていることを確認してください。Microsoft の公式 Web サイトからダウンロードしてインストールできます。
### 2. Aspose.Financeライセンスを取得する
Aspose.Finance for .NETの全機能を利用するには、有効なライセンスを取得する必要があります。ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy)または、テスト目的で一時ライセンスを選択することもできます。
### 3. Aspose.Finance for .NET をダウンロードして参照する
Aspose.Finance for .NETライブラリを以下からダウンロードしてください。[リリースページ](https://releases.aspose.com/finance/net/).NET プロジェクトで参照します。
### 4. ドキュメントとサポートにアクセスする
参照[APIドキュメント](https://reference.aspose.com/finance/net/)Aspose.Finance for .NET の使用に関する詳細情報については、こちらをご覧ください。また、Aspose.Finance コミュニティからサポートを受けることもできます。[サポートフォーラム](https://forum.aspose.com/c/finance/43).
## 名前空間のインポート
まず、必要な名前空間を .NET プロジェクトにインポートします。
## ステップ 1: Aspose.Finance 名前空間を追加する
```csharp
using Aspose.Finance.Xbrl;
using System;
```
この名前空間には、XBRL ドキュメントとデータを操作するためのクラスとメソッドが含まれています。
ここで、提供されている例を複数のステップに分解して、Aspose.Finance for .NET を使用して XBRL ドキュメントにスキーマ参照を追加する方法を理解しましょう。
## ステップ1: ソースディレクトリと出力ディレクトリを定義する
```csharp
//ソースディレクトリ
string sourceDir = "Your Source Directory";
//出力ディレクトリ
string outputDir = "Your Output Directory";
```
交換する`"Your Source Directory"`そして`"Your Output Directory"`それぞれソース ディレクトリと出力ディレクトリへの実際のパスを指定します。
## ステップ2: XBRLドキュメントを作成する
```csharp
XbrlDocument document = new XbrlDocument();
```
これにより、XBRL ドキュメントの新しいインスタンスが作成されます。
## ステップ3: XBRLインスタンスにアクセスする
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
これにより、ドキュメントから XBRL インスタンスのコレクションが取得され、新しいインスタンスが追加されます。
## ステップ4: スキーマ参照を追加する
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
これにより、XBRLインスタンスにスキーマ参照が追加されます。`"schema.xsd"`スキーマファイルの実際の名前で、`"example"`適切な接頭辞を付けて、`"http://example.com/xbrl/taxonomy"`ターゲット名前空間 URI を使用します。
## ステップ5: ドキュメントを保存する
```csharp
document.Save(outputDir + @"document2.xbrl");
```
これにより、変更された XBRL ドキュメントが指定された出力ディレクトリに保存されます。
## 結論
結論として、Aspose.Finance for .NET は、.NET アプリケーションで財務ドキュメントとデータを処理するための堅牢なソリューションを提供します。このチュートリアルで概説されている手順に従うことで、Aspose.Finance をプロジェクトに簡単に統合し、XBRL ドキュメントを効率的に操作できます。
## よくある質問
 （よくある質問）
### 1. ライセンスなしで Aspose.Finance for .NET を使用できますか?
いいえ、Aspose.Finance for .NET の全機能を利用するには有効なライセンスが必要です。ただし、テスト目的で一時的なライセンスを取得することはできます。
### 2. Aspose.Finance は会計ソフトウェアの構築に適していますか?
はい、Aspose.Finance は財務データを処理するための包括的な機能を提供するため、会計ソフトウェアや関連アプリケーションの構築に最適です。
### 3. Aspose.Finance のサポートはどこで受けられますか?
公式サポート フォーラムの Aspose.Finance コミュニティからサポートを求めることができます。
### 4. スキーマ参照プレフィックスをカスタマイズできますか?
はい、Aspose.Finance for .NET を使用して XBRL ドキュメントにスキーマ参照を追加するときに、適切なプレフィックスを選択できます。
### 5. Aspose.Finance は XBRL 以外の財務形式もサポートしていますか?
はい、Aspose.Finance はさまざまな財務形式と標準をサポートしており、多様な財務アプリケーションへのシームレスな統合を可能にします。