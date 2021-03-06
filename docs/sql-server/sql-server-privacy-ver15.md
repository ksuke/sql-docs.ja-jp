---
title: SQL Server 2019 のプライバシーの補足情報 | Microsoft Docs
ms.date: 09/20/2019
ms.prod: sql
ms.reviewer: mikeray
ms.custom: ''
ms.topic: conceptual
f1_keywords: ''
helpviewer_keywords: ''
author: MsSQLGirl
ms.author: jukoesma
monikerRange: '>= sql-server-ver15 || = sqlallproducts-allversions'
ms.openlocfilehash: bbb8a21ee63e0a14778ee57874ba0ef385ac6cba
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "71150295"
---
# <a name="sql-server-2019-privacy-supplement"></a>SQL Server 2019 のプライバシーの補足情報

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

この記事では、機能使用状況および診断データを匿名で収集して Microsoft に送信する、インターネット対応機能の概要を説明します。 SQL Server では、標準的なコンピューター情報、および使用とパフォーマンスに関するデータが収集される場合があります。これらの情報は Microsoft に送信され、製品の品質、セキュリティ、および信頼性を向上させる目的で分析されます。 この記事は、[Microsoft のプライバシーに関する声明](https://go.microsoft.com/fwlink/?LinkId=521839)全体の内容を補うものです。 この記事のデータ分類は、SQL Server オンプレミス製品のバージョンにのみ適用されます。 次のアイテムには適用されません。

- Azure SQL データベース
- [SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-telemetry-ssms?view=sql-server-2017)
- SQL Server Data Tools (SSDT)
- Azure Data Studio
- Database Migration Assistant
- SQL Server Migration Assistant
- MS-SQL の拡張機能

*許可される使用シナリオ*の定義。 この記事のコンテキストでは、Microsoft は、"許可される使用シナリオ" を Microsoft によって開始されたアクションまたはアクティビティとして定義します。

## <a name="access-control"></a>アクセス制御

SQL Server のインストール内のログイン、ユーザー、またはアカウントをセキュリティで保護するために使用される資格情報関連の情報。

### <a name="examples-of-access-control"></a>アクセス制御の例

- パスワード
- 証明書

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ

|シナリオ |アクセスの制限 |リテンション期間の要件 |
|---------|---------|---------|
|使用状況と診断データを通じて、これらの資格情報がユーザー マシンの外に出ることはありません。 |- |- |
|クラッシュ ダンプにはアクセス制御データが含まれている可能性があります。 |- |クラッシュ ダンプ:最大 30 日。 |
|顧客が手動で挿入する場合を除き、ユーザー フィードバックを通じて、これらの資格情報がユーザー コンピューターの外に出ることはありません |サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 |ユーザー フィードバック:最大 1 年|
|&nbsp;|&nbsp;|&nbsp;|

## <a name="customer-content"></a>顧客のコンテンツ

顧客のコンテンツは、直接または間接的に、ユーザー テーブル内に格納されるデータとして定義されます。 データには、ユーザー テーブル内に格納される可能性のあるクエリ テキスト内の統計またはユーザー リテラルが含まれます。

### <a name="examples-of-customer-content"></a>顧客のコンテンツの例

- ユーザー テーブルの行内に格納されるデータ値。
- ユーザー テーブルの行内の値のコピーを含む統計オブジェクト。
- リテラル値を含むクエリ テキスト。

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ

|シナリオ  |アクセスの制限  |リテンション期間の要件 |
|---------|---------|---------|
|使用状況と診断データを通じて、このデータがユーザー マシンの外に出ることはありません。 |- |- |
|クラッシュ ダンプには顧客のコンテンツが含まれ、Microsoft に送信される場合があります。 |- |クラッシュ ダンプ:最大 30 日。 |
|同意した顧客は、顧客のコンテンツを含むユーザー フィードバックを Microsoft に送信できます。 |サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 Microsoft は元の顧客にデータを公開できます。 |ユーザー フィードバック:最大 1 年 |

## <a name="end-user-identifiable-information-euii"></a>エンド ユーザーを特定できる情報 (EUII)

ユーザーから受信したデータ、または製品の使用時に生成されたデータ。
- 個々のユーザーにリンク可能。
- コンテンツを含まない。

### <a name="examples-of-end-user-identifiable-information"></a>エンド ユーザーを特定できる情報の例

- インターフェイスの識別。 完全な IP アドレス
- コンピューター名
- ログイン/ユーザー名
- 電子メール アドレスのローカル部分 (joe@contoso.com)
- 場所情報
- 顧客の識別

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ

|シナリオ  |アクセスの制限  |リテンション期間の要件|
|---------|---------|---------|
|使用状況と診断データを通じて、このデータがユーザー マシンの外に出ることはありません。 |- |- |
|クラッシュ ダンプには EUII が含まれ、Microsoft に送信される場合があります。 |- |クラッシュ ダンプ:最大 30 日 |
|顧客の識別 ID は、ユーザーがサブスクライブしている新しいハイブリッドおよびクラウド機能を提供するために Microsoft に送信される可能性があります。 |- |現在、このようなハイブリッドまたはクラウド機能は存在しません。|
|同意した顧客は、顧客のコンテンツを含むユーザー フィードバックを Microsoft に送信できます。|サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 Microsoft は元の顧客にデータを公開できます。 |ユーザー フィードバック:最大 1 年 |

## <a name="internet-based-services-data"></a>インターネット ベースのサービス データ

SQL Server の使用許諾契約ごとに、インターネット ベースのサービスを提供するために必要なデータです。

### <a name="examples-of-internet-based-services-data"></a>インターネット ベースのサービス データの例

- コンピューター仕様の情報
- ブラウザーの名前/バージョン
- SQL Server のバージョン
- 言語コード
- 特定のオクテットが削除された IP アドレス
- マップ データ

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ

|シナリオ  |アクセスの制限  |リテンション期間の要件|
|---------|---------|---------| 
|機能の改善および/または現在の機能のバグの修正のために Microsoft で使用される可能性があります。 |サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 Microsoft は元の顧客にデータを公開できます。  たとえば、ダッシュボードを使用します。 |最短 90 日から最長 3 年 |
|同意した顧客は、顧客のコンテンツを含むユーザー フィードバックを Microsoft に送信できます。 |サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 |同意した顧客は、顧客のコンテンツを含むユーザー フィードバックを Microsoft に送信できます。 |
|Power View および SQL Reporting Services マップ アイテムの場合、Bing Maps を使用するためにデータが送信される可能性があります。 |セッション データに制限されます。 |- |

## <a name="organization-identifiable-information-oii"></a>組織を特定できる情報 (OII)

組織から受信したデータ、または製品の使用時に生成されたデータ。
-   組織にリンク可能。
-   コンテンツを含まない。

### <a name="examples-of-organization-identifiable-information"></a>組織を特定できる情報の例
-   組織名 (例:Microsoft Corp.)

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ
|シナリオ  |アクセス制限  |リテンション期間の要件|
|---------|---------|---------|
| Microsoft では、Azure Virtual Machines 内で SQL Server を使用するために Azure 内でお客様にオプションの特典を与える目的のためだけに、Azure Virtual Machines で実行されている SQL Server インスタンスの一般的使用状況データを収集することがあります。 | Microsoft は、Azure Virtual Machines で SQL Server を実行しているお客様が Azure で SQL Server を実行する場合にのみ与えられる特典にアクセスできるよう、Azure portal などを経由してお客様にデータを公開できます。 | 最短 90 日から最長 3 年 |

## <a name="system-metadata"></a>システム メタデータ

サーバーの実行中に生成されるデータです。  このデータには顧客のコンテンツは含まれません。

### <a name="examples-of-system-metadata"></a>システム メタデータの例

顧客のコンテンツ、オブジェクトのメタデータ、顧客のアクセス制御データ、または EUII が含まれない場合に考慮されるシステム メタデータを以下に示します。

- データベース GUID
- コンピューター名のハッシュ
- インスタンス名のハッシュ
- アプリケーション名
- 動作/使用状況データ
- SQL カスタマー エクスペリエンス向上プログラム データ (SQLCEIP)
- サーバー構成データ (sp_configure の設定など)
- 機能構成データ
- イベント名とエラー コード
- ハードウェア設定と、OEM 製造元などの識別

Microsoft は SQL Server を使用するその他のプログラムで設定されたアプリケーション名の値を調べます (例:SharePoint またはサードパーティでパッケージ化されたプログラム。この情報は使用状況データが有効になっている場合に Microsoft に送信されるシステム メタデータに含まれます)。 顧客は、システム メタデータ フィールドのエンド ユーザーを特定できる情報などの個人データを配置したり、これらのフィールドに個人データを格納したりするように設計されたアプリケーションを作成することはできません。 

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ

|シナリオ  |アクセス制限  |リテンション期間の要件|
|---------|---------|---------|
|機能の改善および/または現在の機能のバグの修正のために Microsoft で使用される可能性があります。|サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 |最短 90 日から最長 3 年 |
|顧客への提案の際に使用される可能性があります。  たとえば、"製品の使用状況に基づいて、パフォーマンスの向上のため、機能 *X* の使用を検討してください" というように提案されます。 |Microsoft は、ダッシュボードなどを通じて、元の顧客にデータを公開できます。 |顧客データのセキュリティ ログ:最短 3 年から最長 6 年 |
|将来の製品計画のために Microsoft で使用される可能性があります。 |Microsoft はこの情報を他のハードウェアおよびソフトウェア ベンダーと共有し、Microsoft ソフトウェアでの製品の実行方法を改善する場合があります。 |最短 90 日から最長 3 年|
|出力される使用状況と診断データに基づいてクラウド ベース サービスを提供するために、Microsoft で使用される可能性があります。 たとえば、組織内のすべての SQL Server インストールでの機能の使用状況を示す顧客のダッシュボードなどです。 |Microsoft は、ダッシュボードなどを通じて、元の顧客にデータを公開できます。 |最短 90 日から最長 3 年 |
|同意した顧客は、顧客のコンテンツを含むユーザー フィードバックを Microsoft に送信できます。 |サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。 Microsoft は元の顧客にデータを公開できます。 |ユーザー フィードバック:最大 1 年 |
|たとえば、Microsoft やその他の会社から提供されたソフトウェアを実行しているデータベースやアプリケーションを、データベース名やアプリケーション名で既知のカテゴリに分類することができます。|サードパーティによるアクセスなしの Microsoft の内部使用に制限されます。|最短 90 日から最長 3 年 |

## <a name="object-metadata"></a>オブジェクト メタデータ

サーバー、データベース、テーブル、およびその他のリソースの説明または構成を行うために使用されるデータ。  オブジェクト メタデータにはデータベース テーブルと列の名前が含まれますが、データベース行のコンテンツや他の顧客のコンテンツは含まれません。 顧客は、オブジェクト メタデータ フィールドのエンド ユーザーを特定できる情報などの個人データを配置したり、これらのフィールドに個人データを格納したりするように設計されたアプリケーションを作成することはできません。 以下の許可される使用シナリオの場合、製品改善のための使用パターンの決定にはハッシュ フォームのみが使用されます。 

### <a name="examples-of-object-metadata"></a>オブジェクト メタデータの例

- SQL Server データベース名
- テーブル名と列名
- 統計名

### <a name="permitted-usage-scenarios"></a>許可される使用シナリオ

> [!NOTE]
> すべてのオブジェクト メタデータ値は、収集の前にハッシュされます。
>

|シナリオ  |アクセスの制限  |リテンション期間の要件|
|---------|---------|---------|
|機能の改善および/または現在の機能のバグの修正のために Microsoft で使用される可能性があります。 |サードパーティによるアクセスなしの Microsoft 内部使用に制限されます。 |最短 90 日から最長 3 年|

## <a name="telemetry-controls"></a>テレメトリのコントロール

製品のテレメトリのオン/オフを切り替える方法については、 https://support.microsoft.com/help/3153756/how-to-configure-sql-server-2016-to-send-feedback-to-microsoft を参照してください。

[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]
