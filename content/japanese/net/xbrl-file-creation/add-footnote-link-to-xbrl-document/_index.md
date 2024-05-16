---
title: XBRL ドキュメントに脚注リンクを追加する
linktitle: XBRL ドキュメントに脚注リンクを追加する
second_title: Aspose.Finance .NET API
description: Aspose.Finance for .NET を使用して XBRL ドキュメントに脚注リンクを追加する方法を学びます。追加のコンテキストを簡単に追加して財務レポートを強化します。
type: docs
weight: 12
url: /ja/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
XBRL ドキュメントに脚注リンクを追加することは、特定のデータ ポイントに関する追加のコンテキストや説明を提供するために重要です。このチュートリアルでは、Aspose.Finance for .NET を使用して、プロセスを段階的に説明します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Finance for .NET: システムにAspose.Finance for .NETがインストールされていることを確認してください。ダウンロードはここから行えます。[ここ](https://releases.aspose.com/finance/net/).
  
2. 開発環境: .NET Framework または .NET Core を使用して開発環境をセットアップします。
## 名前空間をインポート:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## ステップ1: ソースディレクトリと出力ディレクトリを設定する
まず、ソース ファイルと出力ファイルのディレクトリを指定します。
```csharp
//ソースディレクトリ
string sourceDir = "Your Source Directory";
//出力ディレクトリ
string outputDir = "Your Output Directory";
```
## ステップ2: XBRLドキュメントとインスタンスを作成する
XBRL ドキュメントとインスタンスを初期化します。
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## ステップ3: スキーマ参照を追加する
XBRL インスタンスにスキーマ参照を追加します。
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## ステップ4: コンテキストを定義する
XBRL インスタンスのコンテキストを定義します。
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## ステップ5: 脚注リンクを追加する
XBRL インスタンスに脚注リンクを作成して追加します。
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## ステップ6: ドキュメントを保存する
変更した XBRL ドキュメントを保存します。
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## 結論
Aspose.Finance for .NET を使用すると、XBRL ドキュメントに脚注リンクを追加するのは簡単です。このチュートリアルで説明されている手順に従うことで、追加のコンテキストや説明を財務レポートにシームレスに組み込むことができます。
## よくある質問
### 単一の XBRL ドキュメントに複数の脚注リンクを追加できますか?
はい、このチュートリアルで説明されている手順を追加リンクごとに繰り返すことで、複数の脚注リンクを追加できます。
### Aspose.Finance for .NET は .NET Framework と .NET Core の両方と互換性がありますか?
はい、Aspose.Finance for .NET は .NET Framework と .NET Core の両方の環境をサポートしています。
### Aspose.Finance for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance for .NET は XBRL 検証をサポートしていますか?
はい、Aspose.Finance for .NET は、業界標準への準拠を保証するために、XBRL 検証の包括的なサポートを提供します。
### Aspose.Finance for .NET に関する追加のリソースとサポートはどこで見つかりますか?
訪問することができます[Aspose.Finance for .NET フォーラム](https://forum.aspose.com/c/finance/43)サポートおよびアクセスドキュメント[ここ](https://reference.aspose.com/finance/net/).