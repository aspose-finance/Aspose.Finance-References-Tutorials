---
title: XBRL ドキュメントにアイテムを追加
linktitle: XBRL ドキュメントにアイテムを追加
second_title: Aspose.Finance .NET API
description: Aspose.Finance for .NET を使用して XBRL ドキュメントに項目を追加する方法を学びます。.NET アプリケーションでの財務レポート作成を簡素化します。#Aspose #Finance
type: docs
weight: 13
url: /ja/net/xbrl-file-creation/add-item-to-xbrl-document/
---
拡張ビジネス レポート言語 (XBRL) は、財務レポートの標準形式となり、財務データの効率的で正確な通信を可能にしています。Aspose.Finance for .NET は、.NET アプリケーションで XBRL ドキュメントを操作するための強力な機能を提供します。このチュートリアルでは、Aspose.Finance for .NET を使用して XBRL ドキュメントに項目を追加する手順について説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
### 1. Aspose.Finance for .NET をインストールする
まだの場合は、Aspose.Finance for .NETをダウンロードしてインストールしてください。[公式ウェブサイト](https://releases.aspose.com/finance/net/)インストール手順に従って、.NET 環境にライブラリを設定します。
### 2. 開発環境をセットアップする
.NET 開発用の機能する開発環境があることを確認してください。Visual Studio などの互換性のある IDE と、システムにインストールされている .NET フレームワークが必要です。
## 名前空間のインポート
まず、Aspose.Finance for .NET が提供する機能を利用するために、必要な名前空間を .NET アプリケーションにインポートします。
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#では、サンプル コードを複数のステップに分解してみましょう。
## ステップ1: ソースディレクトリと出力ディレクトリを定義する
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
交換する`"Your Source Directory"`そして`"Your Output Directory"`それぞれソース ディレクトリと出力ディレクトリへのパスに置き換えます。
## ステップ2: XBRLドキュメントとインスタンスを作成する
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
作業する XBRL ドキュメントとインスタンスを初期化します。
## ステップ3: スキーマ参照を追加する
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
スキーマ ファイルへのパスを提供し、名前空間の詳細を指定して、XBRL インスタンスにスキーマ参照を追加します。
## ステップ4: コンテキストとエンティティを定義する
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
期間とエンティティの詳細を指定して、XBRL インスタンスのコンテキストとエンティティを作成します。
## ステップ5: ユニットを追加する
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217");
xbrlInstance.Units.Add(unit);
```
メジャー修飾名を指定して、XBRL インスタンスの単位を定義します。
## ステップ6: アイテムを追加する
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
概念、コンテキスト、単位、精度、値を指定して、XBRL インスタンスに項目を追加します。
## ステップ7: ドキュメントを保存する
```csharp
document.Save(outputDir + @"document5.xbrl");
```
XBRL ドキュメントを出力ディレクトリに保存します。
## 結論
XBRL ドキュメントに項目を追加することは、財務データを正確に表現するために不可欠です。Aspose.Finance for .NET は、.NET アプリケーションで XBRL ドキュメントを操作するための包括的な API を提供することで、このプロセスを簡素化します。
## よくある質問
### Aspose.Finance for .NET を任意の .NET アプリケーションで使用できますか?
はい、Aspose.Finance for .NET は、ASP.NET、WinForms、コンソール アプリケーションを含むあらゆる .NET アプリケーションと互換性があります。
### Aspose.Finance for .NET は無料で使用できますか?
 Aspose.Finance for .NETは商用ライブラリです。無料試用版をダウンロードして機能を評価できます。ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy).
### Aspose.Finance for .NET は、XBRL 以外の財務レポート形式もサポートしていますか?
Aspose.Finance for .NET は主に XBRL 関連の機能に重点を置いています。ただし、Aspose はさまざまな財務形式を扱うための他のライブラリも提供しています。
### Aspose.Finance for .NET のサポートを受けるにはどうすればよいですか?
 Aspose.Finance for .NETのサポートは、[公式フォーラム](https://forum.aspose.com/c/finance/43)では、質問したり、他のユーザーやサポートスタッフとやり取りしたりできます。
### Aspose.Finance for .NET の一時ライセンスを取得できますか?
はい、Aspose.Finance for .NETの一時ライセンスはテスト目的でご利用いただけます。[ここ](https://purchase.aspose.com/temporary-license/).