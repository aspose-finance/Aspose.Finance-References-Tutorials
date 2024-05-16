---
title: XBRL ドキュメントに ARC ロール参照を追加する
linktitle: XBRL ドキュメントに ARC ロール参照を追加する
second_title: Aspose.Finance .NET API
description: Aspose.Finance for .NET を使用して XBRL ドキュメントを効率的に操作する方法を学びます。ステップバイステップのガイドに従って、ARC ロール参照を簡単に追加します。
type: docs
weight: 10
url: /ja/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## 導入
財務データの管理とレポート作成の世界では、eXtensible Business Reporting Language (XBRL) が重要な役割を果たします。XBRL は、財務情報の伝達と交換の方法を標準化し、一貫性、正確性、効率性を確保します。ただし、XBRL ドキュメントの操作、特に特定のロールと参照を組み込む場合は、基礎となるメカニズムを細かく理解する必要があります。このチュートリアルでは、そのようなタスクの 1 つである、Aspose.Finance for .NET を使用して XBRL ドキュメントに ARC ロール参照を追加することに焦点を当てます。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
### 環境設定
1. Aspose.Finance for .NETのインストール: Aspose.Finance for .NETライブラリを以下のサイトからダウンロードしてインストールします。[リリース](https://releases.aspose.com/finance/net/).
   
2. 開発環境: Visual Studio またはその他の推奨 IDE を使用して開発環境を設定します。
## 名前空間のインポート
C# コードに必要な名前空間を必ずインポートしてください。
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## ステップ1: ソースディレクトリと出力ディレクトリを定義する
続行する前に、XBRL ファイルが配置されるソース ディレクトリと保存される出力ディレクトリを指定します。
```csharp
//ソースディレクトリ
string sourceDir = "Your Source Directory";
//出力ディレクトリ
string outputDir = "Your Output Directory";
```
## ステップ2: XBRLドキュメントを作成する
インスタンス化する`XbrlDocument`XBRL データを操作するオブジェクト。
```csharp
XbrlDocument document = new XbrlDocument();
```
## ステップ3: XbrlInstanceコレクションにアクセスする
ドキュメント内の XBRL インスタンスのコレクションにアクセスします。
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## ステップ4: XbrlInstanceを追加する
コレクションに新しい XBRL インスタンスを追加します。
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## ステップ5: スキーマ参照を追加する
ソース ディレクトリ、名前空間プレフィックス、および URI を指定して、XBRL インスタンスにスキーマ参照を含めます。
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## ステップ6: ArcroleTypeを取得する
取得する`ArcroleType`特定の URI に基づきます。
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## ステップ7: ArcroleReferenceを追加する
もし、`ArcroleType`見つかった場合は、`ArcroleReference`それを XBRL インスタンスの arcrole 参照に追加します。
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## ステップ8: ドキュメントを保存する
変更された XBRL ドキュメントを指定された出力ディレクトリに保存します。
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## 結論
このチュートリアルでは、Aspose.Finance for .NET を使用して XBRL ドキュメントに ARC ロール参照を追加する方法について説明しました。これらのステップバイステップの指示に従い、Aspose.Finance の機能を活用することで、特定の要件を満たすように XBRL データを効率的に管理および操作できます。
## よくある質問
### XBRL とは何ですか?
XBRL は eXtensible Business Reporting Language の略で、ビジネスおよび財務データの電子通信用の標準化された言語です。
### XBRL が重要なのはなぜですか?
XBRL は、財務情報の交換と分析における一貫性、正確性、効率性を確保し、規制当局、アナリスト、企業に利益をもたらします。
### Aspose.Finance は複雑な XBRL タスクを処理できますか?
はい、Aspose.Finance は、ロール参照やタクソノミー管理などの複雑なタスクの処理を含む、XBRL ドキュメントを操作するための強力な機能を提供します。
### Aspose.Finance は他の .NET ライブラリと互換性がありますか?
はい、Aspose.Finance は他の .NET ライブラリとシームレスに統合され、財務データの操作とレポート作成を幅広くサポートします。
### Aspose.Finance の追加サポートはどこで受けられますか?
追加のサポートについては、[Aspose.Finance サポート ページ](https://forum.aspose.com/c/finance/43).