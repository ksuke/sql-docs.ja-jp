---
title: DacFx と SqlPackage のリリース ノート
description: Microsoft sqlpackage のリリース ノート。
ms.custom: tools|sos
ms.date: 02/02/2019
ms.prod: sql
ms.reviewer: alayu; sstein
ms.prod_service: sql-tools
ms.topic: conceptual
author: pensivebrian
ms.author: broneill
manager: kenvh
ms.openlocfilehash: 9dfbb1192c160fb032afa6dbb56ee7b24b80bcd6
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "75241220"
---
# <a name="release-notes-for-sqlpackageexe"></a>SqlPackage.exe のリリース ノート

**[最新バージョンのダウンロード](sqlpackage-download.md)**

この記事では、SqlPackage.exe のリリースされたバージョンによって提供される機能と修正プログラムを示します。

<!--
TODO:
The Introduction text needs to add clarity regarding the relationship between
'SqlPackage.exe' and 'DacFx' (the Microsoft 'Data-Tier Application Framework').
One added sentence would be sufficient.

Or, if there is no relationship, remove 'DacFx' from the metadata 'title:'.

I discussed this with SStein (SteveStein).
Thanks.  GeneMi (MightyPen in GitHub).  2019-03-27
-->
## <a name="1841-sqlpackage"></a>18.4.1 sqlpackage

|プラットフォーム|ダウンロード|リリース日|Version|Build
|:---|:---|:---|:---|:---|
|Windows|[MSI インストーラー](https://go.microsoft.com/fwlink/?linkid=2113703)|2019 年 12 月 13 日|18.4.1|15.0.4630.1|
|macOS .NET Core |[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2113705)|2019 年 12 月 13 日| 18.4.1|15.0.4630.1|
|Linux .NET Core |[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2113331)|2019 年 12 月 13 日| 18.4.1|15.0.4630.1|
|Windows .NET Core |[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2113704)|2019 年 12 月 13 日| 18.4.1|15.0.4630.1|

### <a name="fixes"></a>修正
| Fix | 詳細 |
| :-- | :------ |
| ScriptDom |  18.3.1 で ScriptDom の解析回帰が導入されましたが、"RENAME" が最上位のトークンとして不適切に処理されるため、解析が失敗します。
| &nbsp; | &nbsp; |


## <a name="184-sqlpackage"></a>18.4 sqlpackage

|プラットフォーム|ダウンロード|リリース日|Version|Build
|:---|:---|:---|:---|:---|
|Windows|[MSI インストーラー](https://go.microsoft.com/fwlink/?linkid=2108813)|2019 年 10 月 29 日|18.4|15.0.4573.2|
|macOS .NET Core |[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2108815)|2019 年 10 月 29 日| 18.4|15.0.4573.2|
|Linux .NET Core |[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2108814)|2019 年 10 月 29 日| 18.4|15.0.4573.2|
|Windows .NET Core |[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2109019)|2019 年 10 月 29 日| 18.4|15.0.4573.2|

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| デプロイ | Azure SQL Data Warehouse (GA) に配置できるようにサポートを追加しました。 | 
| プラットフォーム | macOS、Linux、および Windows 用の sqlpackage .NET Core GA。 | 
| Security | SHA1 コード署名を削除しました。 |
| デプロイ | 新たに次の Azure データベース エディションのサポートを追加しました: GeneralPurpose、BusinessCritical、および Hyperscale |
| デプロイ | AAD ユーザーとグループに対する Managed Instance のサポートを追加しました。 |
| デプロイ | .NET Core で sqlpackage の /AccessToken パラメーターをサポートします。 |
| &nbsp; | &nbsp; |

### <a name="known-issues"></a>既知の問題 

| 機能 | 詳細 |
| :------ | :------ |
| ScriptDom |  18.3.1 で ScriptDom の解析回帰が導入されましたが、"RENAME" が最上位のトークンとして不適切に処理されるため、解析が失敗します。 これは次の sqlpackage リリースで修正される予定です。 | 
| &nbsp; | &nbsp; |

### <a name="known-issues-for-net-core"></a>.NET Core に関する既知の問題

| 機能 | 詳細 |
| :------ | :------ |
| [インポート] |  圧縮ファイルのサイズが 4 GB を超える bacpac ファイルでは、インポートを実行する際に .NET Core バージョンの sqlpackage を使用することが必要になる場合があります。  これは、.NET Core が ZIP ヘッダーを生成する方法に起因します。ZIP ヘッダーが有効でも、.NET Framework バージョンの sqlpackage では読み取ることができないためです。 | 
| デプロイ | /p: Storage=File パラメーターはサポートされていません。 .NET Core では、Memory のみがサポートされています。 | 
| Always Encrypted | sqlpackage .NET Core では、Always Encrypted 列はサポートされていません。 | 
| Security | sqlpackage .NET Core では、多要素認証用の /ua パラメーターはサポートされていません。 | 
| デプロイ | json データによるシリアル化を使用している古い V2 .dacpac ファイルと .bacpac ファイルがサポートされません。 |
| &nbsp; | &nbsp; |

## <a name="1831-sqlpackage"></a>18.3.1 sqlpackage

|プラットフォーム|ダウンロード|リリース日|Version|Build
|:---|:---|:---|:---|:---|
|Windows|[MSI インストーラー](https://go.microsoft.com/fwlink/?linkid=2102893)|2019 年 9 月 13 日|18.3.1|15.0.4538.1|
|macOS .NET Core (プレビュー)|[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2102894)|2019 年 9 月 13 日| 18.3.1|15.0.4538.1|
|Linux .NET Core (プレビュー)|[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2102978)|2019 年 9 月 13 日| 18.3.1|15.0.4538.1|
|Windows .NET Core (プレビュー)|[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2102979)|2019 年 9 月 13 日| 18.13.1|15.0.4538.1|

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| デプロイ | Azure SQL Data Warehouse (プレビュー) に配置できるようにサポートを追加しました。 | 
| デプロイ | /p:DatabaseLockTimeout=(INT32 '60') パラメーターを sqlpackage に追加しました。 | 
| デプロイ | /p:LongRunningCommandTimeout=(INT32) パラメーターを sqlpackage に追加しました。 |
| エクスポートおよび抽出 | /p:TempDirectoryForTableData=(STRING) パラメーターを sqlpackage に追加しました。 |
| デプロイ | 配置の共同作成者を他の場所から読み込むことができるようになりました。 配置の共同作成者は、配置されているターゲット .dacpac と同じディレクトリ、sqlpackage .exe バイナリを基準とした Extensions ディレクトリ、および他のディレクトリの場所を指定できる、sqlpackage に追加された /p:AdditionalDeploymentContributorPaths=(STRING) パラメーターから読み込まれます。 |
| デプロイ | OPTIMIZE_FOR_SEQUENTIAL_KEY のサポートを追加しました。 |
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| デプロイ | 自動インデックスが配置時に削除されないよう、自動インデックスを無視するように修正しました。 | 
| Always Encrypted | Always Encrypted の varchar 列の処理を修正しました。 | 
| ビルド/配置 | xml 列セットの nodes () メソッドが解決されるように修正しました。| 
| ScriptDom | "URL" 文字列が最上位レベルのトークンとして解釈されていたその他のケースが修正されました。 | 
| グラフ | 制約内の擬似列参照に対して生成された TSQL を修正しました。  | 
| [エクスポート] | 複雑さの要件を満たすランダムなパスワードが生成されるようになりました。 | 
| デプロイ | 制約を取得するときにコマンド タイムアウトに従うように修正しました。 | 
| .NET Core (プレビュー) | ファイルへの診断ログの記録を修正しました。 | 
| .NET Core (プレビュー) | ストリーミングを使用してテーブル データをエクスポートすることで、大きなテーブルがサポートされるようになりました。 | 
| &nbsp; | &nbsp; |

## <a name="182-sqlpackage"></a>18.2 sqlpackage

|プラットフォーム|ダウンロード|リリース日|Version|Build
|:---|:---|:---|:---|:---|
|Windows|[MSI インストーラー](https://go.microsoft.com/fwlink/?linkid=2087429)|2019 年 4 月 15 日|18.2|15.0.4384.2|
|macOS .NET Core (プレビュー)|[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2087247)|2019 年 4 月 15 日 | 18.2 |15.0.4384.2|
|Linux .NET Core (プレビュー)|[zip ファイル](https://go.microsoft.com/fwlink/?linkid=2087431)|2019 年 4 月 15 日 | 18.2 |15.0.4384.2|

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| グラフ | グラフ テーブルのエッジ制約とエッジ制約句のサポートが追加されました。 |
| デプロイ | SQL Server 2016 以降のインデックス キーで 32 列をサポートするためのモデルの検証規則が有効になりました。 |
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| デプロイ | サポートされていないクエリ ヒントの使用に起因する SQL Server 2016 RTM データベースのリバース エンジニア リングが修正されました。 |
| デプロイ | filegroup ステートメントの作成前に発生するように auto close alter ステートメントの配置順序が修正されました。 |
| ScriptDom | 'URL' 文字列が最上位レベルのトークンとして解釈されていた ScriptDom の回帰解析が修正されました。 |
| デプロイ | alter table add index ステートメントの解析時の null 参照例外が修正されました。 | 
| スキーマ比較 | null 許容の保存される計算列でのスキーマ比較で、常に一致しないとなっていた結果が修正されました。|
| &nbsp; | &nbsp; |

## <a name="181-sqlpackage"></a>18.1 sqlpackage

リリース日: &nbsp;2019 年 2 月 1 日  
ビルド: &nbsp; 15.0.4316.1  
プレビュー リリース。

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| デプロイ | UTF8 照合順序のサポートが追加されました。 |
| デプロイ | インデックス付きビューでの非クラスター化列ストア インデックスが有効になりました。 |
| プラットフォーム | .NET Core 2.2 に移動しました。 | 
| スキーマ比較 | .NET Core でのスキーマ比較でメモリ ストレージが使用されます。 |
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| パフォーマンス | リバース エンジニアリング クエリでのレガシ カーディナリティ推定機能を使用するためのパフォーマンスが改善されました。 | 
| パフォーマンス | スクリプトを生成する際のスキーマ比較での顕著なパフォーマンス問題が修正されました。 | 
| スキーマ比較 | 特定の拡張イベント (xevent) セッションを無視するスキーマのドリフト検出ロジックが修正されました。 |
| グラフ | グラフ テーブルのインポート順序が修正されました。 | 
| [エクスポート] | オブジェクトのアクセス許可による外部テーブルのエクスポートが修正されました。 |
| &nbsp; | &nbsp; |

### <a name="known-issues"></a>既知の問題

このリリースには、.NET Core 2.2 をターゲットとする sqlpackage のクロスプラットフォーム プレビュー ビルドが含まれています。 sqlpackage は、macOS および Linux で実行できます。

| 既知の問題 | 詳細 |
| :---------- | :------ |
| デプロイ | .NET Core では、ビルド コントリビューターと配置コントリビューターがサポートされません。 | 
| デプロイ | .NET Core では、json データによるシリアル化を使用している古い .dacpac ファイルと .bacpac ファイルがサポートされません。 | 
| デプロイ | .NET Core では、大文字と小文字が区別されるファイル システムの問題により、参照された .dacpacs (master.dacpac など) が解決されない場合があります。 | 回避策は、参照ファイルの名前をすべて大文字にすることです (例: MASTER.BACPAC)。 |
| &nbsp; | &nbsp; |

## <a name="180-sqlpackage"></a>18.0 sqlpackage

リリース日: &nbsp;2018 年 10 月 24 日  
ビルド: &nbsp; 15.0.4200.1

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| デプロイ | データベース互換性レベル 150 のサポートが追加されました。 | 
| デプロイ | マネージ インスタンスのサポートが追加されました。 | 
| パフォーマンス | データベース操作の並列処理の程度を指定する MaxParallelism コマンドライン パラメーターが追加されました。 | 
| Security | SQL Server に接続するときの認証トークンを指定する AccessToken コマンドライン パラメーターが追加されました。 | 
| [インポート] | インポートでの BLOB/CLOB データ型のストリーミングのサポートが追加されました。 | 
| デプロイ | スカラー UDF 'INLINE' オプションのサポートが追加されました。 | 
| グラフ | グラフ テーブルの 'MERGE' 構文のサポートが追加されました。 |
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| グラフ | グラフ テーブルの解決されない擬似列が修正されました。 |
| デプロイ | メモリ最適化テーブル使用時のメモリ最適化されたファイル グループによるデータベースの作成が修正されました。 |
| デプロイ | 外部テーブルでの拡張プロパティの包含が修正されました。 |
| &nbsp; | &nbsp; |

## <a name="178-sqlpackage"></a>17.8 sqlpackage

リリース日: &nbsp;2018 年 6 月 22 日  
ビルド: &nbsp; 14.0.4079.2

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| 診断 | SqlClient の例外メッセージを含めて、接続エラーのエラー メッセージが改良されました。 |
| デプロイ | 単一パーティション インデックスのインポート/エクスポートで、インデックスの圧縮がサポートされます。 |
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| デプロイ | SQL 2017 以降での XML 列セットのリバース エンジニアリング問題が修正されました。 | 
| デプロイ | データベース互換性レベル 140 のスクリプトが Azure SQL Database で無視される問題が修正されました。 |
| &nbsp; | &nbsp; |

## <a name="1741-sqlpackage"></a>17.4.1 sqlpackage

リリース日: &nbsp;2018 年 1 月 25 日  
ビルド: &nbsp; 14.0.3917.1

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| インポート/エクスポート | 入れ子になったステートメントの数が多い Transact-SQL を解析するための ThreadMaxStackSize コマンドライン パラメーターが追加されました。 |
| デプロイ | データベース カタログ照合順序のサポート。 | 
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| [インポート] | Azure SQL Database の .bacpac をオンプレミスのインスタンスにインポートする際の、"_パスワードのないデータベース マスター キーは、このバージョンの SQL Server ではサポートされていません_" に起因するエラーが修正されました。 |
| グラフ | グラフ テーブルの解決されない擬似列エラーが修正されました。 |
| スキーマ比較 | スキーマを比較するための SQL 認証を修正しました。 | 
| &nbsp; | &nbsp; |

## <a name="1740-sqlpackage"></a>17.4.0 sqlpackage

リリース日: &nbsp;2017 年 12 月 12 日  
ビルド: &nbsp; 14.0.3881.1

### <a name="features"></a>[機能]

| 機能 | 詳細 |
| :------ | :------ |
| デプロイ |  SQL 2017 以降と Azure SQL Database での_テンポラル保持ポリシー_のサポートが追加されました。 | 
| 診断 | 診断情報を保存するファイル パスを指定する /DiagnosticsFile:"C:\Temp\sqlpackage.log" コマンドライン パラメーターが追加されました。 | 
| 診断 | 診断情報をコンソールにログ記録する /Diagnostics コマンドライン パラメーターが追加されました。 |
| &nbsp; | &nbsp; |

### <a name="fixes"></a>修正

| Fix | 詳細 |
| :-- | :------ |
| デプロイ | 認識できないデータベース互換性レベルに遭遇してもブロックは行われません。 代わりに、最新の Azure SQL Database またはオンプレミスのプラットフォームであるとみなされます。 |
| &nbsp; | &nbsp; |
