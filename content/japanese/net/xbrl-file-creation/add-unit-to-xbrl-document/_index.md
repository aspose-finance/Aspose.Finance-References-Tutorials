---
title: XBRL ドキュメントに単位を追加する
linktitle: XBRL ドキュメントに単位を追加する
second_title: Aspose.Finance .NET API
description: Aspose.Finance for .NET を使用して、XBRL ドキュメントに単位を簡単に追加する方法を学びます。今すぐ財務データ処理機能を強化しましょう。
type: docs
weight: 16
url: /ja/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Aspose.Finance for .NET の世界へようこそ。これは、.NET アプリケーション内での効率的な財務ドキュメント操作へのゲートウェイです。会計ソフトウェア、財務分析ツール、またはその他の財務アプリケーションを構築する場合でも、Aspose.Finance for .NET は、開発プロセスを効率化する包括的な機能セットを提供します。
## 前提条件
Aspose.Finance for .NET のパワーを活用する前に、必要な前提条件が整っていることを確認しましょう。
### 1. Visual Studioのインストール
システムに Visual Studio がインストールされていることを確認してください。インストールされていない場合は、Microsoft の公式 Web サイトからダウンロードしてインストールできます。
### 2. ライセンスを取得する
Aspose.Finance for .NETの潜在能力を最大限に引き出すには、有効なライセンスが必要です。ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy)または、テスト目的で一時ライセンスを選択することもできます。
### 3. Aspose.Finance for .NET をダウンロードして参照する
Aspose.Finance for .NETライブラリを以下からダウンロードしてください。[リリースページ](https://releases.aspose.com/finance/net/).NET プロジェクトで参照します。
### 4. ドキュメントとサポートにアクセスする
参照[ドキュメンテーション](https://reference.aspose.com/finance/net/)Aspose.Finance for .NETの詳しい利用方法については、こちらをご覧ください。また、Aspose.Financeコミュニティから支援を受けることもできます。[サポートフォーラム](https://forum.aspose.com/c/finance/43).
## 名前空間のインポート
次に、必要な名前空間を .NET プロジェクトにインポートします。
## ステップ 1: Aspose.Finance 名前空間を追加する
```csharp
using Aspose.Finance.Xbrl;
using System;
```
この名前空間には、XBRL ドキュメントとデータの操作に不可欠なクラスとメソッドが含まれています。
Aspose.Finance for .NET を使用して XBRL ドキュメントにユニットを追加する方法を理解するために、提供されている例を複数のステップに分解してみましょう。
## ステップ1: 出力ディレクトリを定義する
```csharp
//出力ディレクトリ
string outputDir = "Your Output Directory";
```
交換する`"Your Output Directory"`希望する出力ディレクトリへの実際のパスを入力します。
## ステップ2: XBRLドキュメントを作成する
```csharp
XbrlDocument document = new XbrlDocument();
```
これにより、XBRL ドキュメントの新しいインスタンスが初期化されます。
## ステップ3: XBRLインスタンスにアクセスする
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
これにより、ドキュメントから XBRL インスタンスのコレクションが取得され、新しいインスタンスが追加されます。
## ステップ4: ユニットを追加する
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217");
xbrlInstance.Units.Add(unit);
```
これにより、新しい測定単位 (この場合は USD) が作成され、XBRL インスタンスに追加されます。必要に応じて、通貨コードと名前空間 URI を調整できます。
## ステップ5: ドキュメントを保存する
```csharp
document.Save(outputDir + @"document4.xbrl");
```
これにより、変更された XBRL ドキュメントが指定された出力ディレクトリに保存されます。
## 結論
結論として、Aspose.Finance for .NET を使用すると、開発者は .NET アプリケーション内で財務ドキュメントやデータを簡単に操作できるようになります。このチュートリアルで説明されている手順に従うことで、Aspose.Finance for .NET をプロジェクトにシームレスに統合し、財務処理機能を強化できます。
## よくある質問
### 1. ライセンスなしで Aspose.Finance for .NET を使用できますか?
いいえ、Aspose.Finance for .NET の全機能を使用するには有効なライセンスが必要です。ただし、テスト目的で一時ライセンスはご利用いただけます。
### 2. Aspose.Finance for .NET は会計ソフトウェアの構築に適していますか?
はい、Aspose.Finance for .NET は、会計ソフトウェアや関連する財務アプリケーションの構築に特化した強力な機能を提供します。
### 3. Aspose.Finance for .NET のサポートはどこで受けられますか?
サポート フォーラムの Aspose.Finance コミュニティから支援を求めることができます。
### 4. XBRL ドキュメントの測定単位をカスタマイズできますか?
はい、Aspose.Finance for .NET を使用して、カスタム測定単位を作成し、XBRL ドキュメントに追加できます。
### 5. Aspose.Finance for .NET は複数の通貨をサポートしていますか?
はい、Aspose.Finance for .NET は複数の通貨をサポートしており、多目的な財務データ処理が可能です。