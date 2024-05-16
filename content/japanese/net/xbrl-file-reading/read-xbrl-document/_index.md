---
title: XBRLドキュメントを読む
linktitle: XBRLドキュメントを読む
second_title: Aspose.Finance .NET API
description: Aspose.Finance を使用して .NET で XBRL ドキュメントを読み取る方法を学びます。財務データ処理機能を簡単に強化できます。#Aspose #Finance #XBRL
type: docs
weight: 11
url: /ja/net/xbrl-file-reading/read-xbrl-document/
---
## 導入
Aspose.Finance for .NET は、開発者が .NET アプリケーション内で財務データを効率的に管理できるようにする強力な財務ソフトウェア開発ツールです。その主な機能の 1 つは、XBRL (eXtensible Business Reporting Language) ドキュメントをシームレスに読み取る機能です。この包括的なガイドでは、Aspose.Finance for .NET を使用して XBRL ドキュメントを読み取るプロセスを順を追って説明します。このチュートリアルを完了すると、この機能を活用して財務データ処理機能を強化する方法をしっかりと理解できるようになります。
## 前提条件
チュートリアルに進む前に、必要なものがすべて揃っていることを確認しましょう。
### .NET 開発環境
まず最初に、マシンに .NET 開発環境がセットアップされていることを確認してください。まだセットアップしていない場合は、Microsoft の公式 Web サイトから最新バージョンの .NET SDK をダウンロードしてインストールできます。
### Aspose.Finance .NET 版
このチュートリアルを実行するには、開発環境に Aspose.Finance for .NET がインストールされている必要があります。ライブラリは、以下の公式ダウンロード リンクからダウンロードできます。
[Aspose.Finance for .NET をダウンロード](https://releases.aspose.com/finance/net/)
### XBRL ドキュメント
Aspose.Finance for .NET を使用して読み取る予定の XBRL ドキュメントを準備します。コード内で参照するためのファイル パスが準備されていることを確認します。
## 名前空間のインポート
まず、Aspose.Finance の機能にアクセスするために必要な名前空間を .NET プロジェクトにインポートします。次の手順に従います。
## ステップ1: .NETプロジェクトを開く
Visual Studio などの任意の統合開発環境 (IDE) で .NET プロジェクトを起動します。
## ステップ 2: Aspose.Finance 参照を追加する
プロジェクトに Aspose.Finance for .NET への参照を追加します。ライブラリをダウンロードしてローカルで参照するか、NuGet パッケージ マネージャーを使用してプロジェクトに直接インストールすることでこれを実現できます。
## ステップ3: 名前空間をインポートする
次に、コード ファイルの先頭に必要な名前空間をインポートします。これらの名前空間は、XBRL ドキュメントの操作に必要なクラスとメソッドへのアクセスを提供します。
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## XBRLドキュメントを読む
環境を設定し、必要な名前空間をインポートしたので、Aspose.Finance for .NET を使用して XBRL ドキュメントを読み取るプロセスについて詳しく見ていきましょう。次の手順に従ってください。
## ステップ1: ソースディレクトリを定義する
まず、XBRL文書が保存されているディレクトリパスを定義します。`"Your Source Directory"`ドキュメントへの実際のパスを入力します。
```csharp
string sourceDir = "Your Source Directory";
```
## ステップ 2: XbrlDocument オブジェクトを作成する
次に、`XbrlDocument` XBRL ドキュメントへのパスを指定してオブジェクトを作成します。
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## ステップ3: XBRLインスタンスにアクセスする
ドキュメントからXBRLインスタンスにアクセスするには、`XbrlInstances`財産。
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## ステップ4: ファクト、スキーマ参照、コンテキスト、ユニットを抽出する
XBRL インスタンスからファクト、スキーマ参照、コンテキスト、および単位を取得します。
```csharp
List<Fact> facts = xbrlInstance.Facts;
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
List<Context> contexts = xbrlInstance.Contexts;
List<Unit> units = xbrlInstance.Units;
```
## ステップ5: 成功メッセージを表示する
XBRL ドキュメントが正常に読み取られたことをユーザーに通知します。
```csharp
Console.WriteLine("ReadXbrlDocument executed successfully.");
```
これらの手順に従うことで、Aspose.Finance for .NET を使用して XBRL ドキュメントを正常に読み取ることができます。
## 結論
このチュートリアルでは、Aspose.Finance for .NET を使用して XBRL ドキュメントを読み取るプロセスについて説明しました。提供されているステップバイステップ ガイドを活用することで、.NET アプリケーション内で XBRL ドキュメントを効率的に処理し、財務データ処理機能を強化できます。
## よくある質問
### Aspose.Finance for .NET はすべてのバージョンの .NET と互換性がありますか?
はい、Aspose.Finance for .NET は、すべてのバージョンの .NET フレームワークと互換性があるように設計されており、プロジェクトへのシームレスな統合を保証します。
### Aspose.Finance を商用プロジェクトに使用できますか?
もちろんです! Aspose.Finance for .NET は個人プロジェクトにも商用プロジェクトにも使用できます。ライセンスを購入するだけで、その機能を最大限に活用できます。
### Aspose.Finance は XBRL 以外のドキュメント形式をサポートしていますか?
はい、Aspose.Finance はさまざまな財務ドキュメント形式をサポートしており、財務データの処理における柔軟性と汎用性を提供します。
### Aspose.Finance ユーザー向けのテクニカル サポートは提供されますか?
もちろんです! Aspose は、Aspose.Finance を含む自社製品専用のテクニカル サポートを提供しています。公式サポート フォーラムを通じてサポートにアクセスできます。
### 購入する前に Aspose.Finance を試すことはできますか?
もちろんです! Aspose は Aspose.Finance の無料試用版を提供しており、契約する前にその機能や性能を調べることができます。