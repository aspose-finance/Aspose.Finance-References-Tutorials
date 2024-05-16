---
title: XBRL ドキュメントにロール参照を追加する
linktitle: XBRL ドキュメントにロール参照を追加する
second_title: Aspose.Finance .NET API
description: Aspose.Finance for .NET を使用して XBRL ドキュメントにロール参照を追加する方法を学習します。このチュートリアルを使用して、.NET アプリケーションでの財務レポート作成を簡素化します。
type: docs
weight: 14
url: /ja/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) は、特に財務報告において、ビジネス情報の交換の標準となっています。Aspose.Finance for .NET は、.NET アプリケーションでの XBRL ドキュメントの操作を簡素化します。このチュートリアルでは、Aspose.Finance for .NET を使用して XBRL ドキュメントにロール参照を追加するプロセスについて説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
### 1. Aspose.Finance for .NET をインストールする
開発環境にAspose.Finance for .NETがインストールされていることを確認してください。まだインストールしていない場合は、[リリース](https://releases.aspose.com/finance/net/)インストール手順に従ってください。
### 2. 開発環境をセットアップする
.NET 開発用の実用的な開発環境があることを確認します。これには、Visual Studio などの互換性のある IDE と、システムにインストールされている .NET フレームワークが含まれます。
## 名前空間のインポート
Aspose.Finance for .NET が提供する機能にアクセスするには、まず必要な名前空間を .NET アプリケーションにインポートします。
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## ステップ4: ロールタイプを取得してロール参照を追加する
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
URI を使用してロール タイプを取得し、XBRL インスタンスにロール参照を追加します。
## ステップ5: ドキュメントを保存する
```csharp
document.Save(outputDir + @"document7.xbrl");
```
XBRL ドキュメントを出力ディレクトリに保存します。
## 結論
XBRL ドキュメントにロール参照を追加することは、ドキュメント内のさまざまな要素のロールを定義するために重要です。Aspose.Finance for .NET は、このタスクを簡単に実行する方法を提供し、開発者が .NET アプリケーションで XBRL ドキュメントを効率的に操作できるようにします。
## よくある質問
### Aspose.Finance for .NET を任意の .NET アプリケーションで使用できますか?
はい、Aspose.Finance for .NET は、ASP.NET、WinForms、コンソール アプリケーションを含むあらゆる .NET アプリケーションと互換性があります。
### Aspose.Finance for .NET は無料で使用できますか?
 Aspose.Finance for .NETは商用ライブラリです。無料試用版をダウンロードして機能を評価できます。ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy).
### Aspose.Finance for .NET は、XBRL 以外の財務レポート形式もサポートしていますか?
Aspose.Finance for .NET は主に XBRL 関連の機能に重点を置いています。ただし、Aspose はさまざまな財務形式を扱うための他のライブラリも提供しています。
### Aspose.Finance for .NET のサポートを受けるにはどうすればよいですか?
 Aspose.Finance for .NETのサポートは、[フォーラム](https://forum.aspose.com/c/finance/43)では、質問したり、他のユーザーやサポートスタッフとやり取りしたりできます。
### Aspose.Finance for .NET の一時ライセンスを取得できますか?
はい、Aspose.Finance for .NETの一時ライセンスはテスト目的でご利用いただけます。[ここ](https://purchase.aspose.com/temporary-license/).