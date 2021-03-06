---
title: availability_replicas (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 10/16/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- availability_replicas_TSQL
- availability_replicas
- sys.availability_replicas
- sys.availability_replicas_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- sys.availability_replicas catalog view
ms.assetid: 0a06e9b6-a1e4-4293-867b-5c3f5a8ff62c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6623d6b95dfe0ebd4e45b13d190d8176bcab1a3c
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67942618"
---
# <a name="sysavailability_replicas-transact-sql"></a>sys.availability_replicas (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

WSFC フェールオーバー クラスター内の AlwaysOn 可用性グループに属している各可用性レプリカに対する行を返します。  
  
たとえばクラスターがダウンしたりクォーラムが失われたりしたために、ローカル サーバー インスタンスが WSFC フェールオーバー クラスターと通信できない場合は、ローカル可用性レプリカの行だけが返されます。 これらの行には、メタデータ内にローカルにキャッシュされているデータの列だけが含まれます。  
  
 
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**replica_id**|**UNIQUEIDENTIFIER**|レプリカの一意の ID。|  
|**group_id**|**UNIQUEIDENTIFIER**|レプリカが属する可用性グループの一意の ID。|  
|**replica_metadata_id**|**int**|データベースエンジン内の可用性レプリカのローカルメタデータオブジェクトの ID。|  
|**replica_server_name**|**nvarchar(256)**|このレプリカをホストし、既定ではないインスタンスの場合はレプリカのインスタンス名もホストしている、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスのサーバー名。|  
|**owner_sid**|**varbinary (85)**|このサーバー インスタンスに登録されている、この可用性レプリカの外部所有者のセキュリティ ID (SID)。<br /><br /> 非ローカル可用性レプリカの場合は NULL です。|  
|**endpoint_url**|**nvarchar(128**|データ同期のためにプライマリとセカンダリのレプリカの間の接続で使用される、ユーザー指定のデータベース ミラーリング エンドポイントの文字列表現。 エンドポイント URL の構文の詳細については、「[可用性レプリカを追加または変更する場合のエンドポイント URL の指定 &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)」を参照してください。<br /><br /> NULL = WSFC フェールオーバー クラスターと通信できません。<br /><br /> このエンドポイントを変更するには、 [ALTER AVAILABILITY GROUP](../../t-sql/statements/alter-availability-group-transact-sql.md) [!INCLUDE[tsql](../../includes/tsql-md.md)]ステートメントの ENDPOINT_URL オプションを使用します。|  
|**availability_mode**|**tinyint**|レプリカの可用性モード。次のいずれかです。<br /><br /> 0 &#124; 非同期コミット。 プライマリ レプリカは、セカンダリがログをディスクに書き込むのを待機することなくトランザクションをコミットできます。<br /><br /> 1 &#124; 同期コミットです。 プライマリ レプリカは、セカンダリ レプリカがトランザクションをディスクに書き込むまで、特定のトランザクションのコミットを待機します。<br /><br />4 &#124; 構成のみ。 プライマリレプリカは、可用性グループの構成メタデータを同期的にレプリカに送信します。 ユーザーデータがレプリカに送信されることはありません。 SQL Server 2017 CU1 以降で使用できます。<br /><br /> 詳細については、「 [可用性モード &#40;AlwaysOn 可用性グループ&#41;](../../database-engine/availability-groups/windows/availability-modes-always-on-availability-groups.md)と呼ばれるプロセスで交換されることがあります。|  
|**availability_mode_desc**|**nvarchar (60)**|**可用性\_モード**の説明。次のいずれかになります。<br /><br /> 非同期\_コミット<br /><br /> 同期\_コミット<br /><br /> 構成\_のみ<br /><br /> 可用性レプリカの可用性モードを変更するには、 [ALTER availability GROUP](../../t-sql/statements/alter-availability-group-transact-sql.md) [!INCLUDE[tsql](../../includes/tsql-md.md)]ステートメントの AVAILABILITY_MODE オプションを使用します。<br/><br>レプリカの可用性モードを構成\_のみに変更することはできません。 構成\_のみのレプリカをセカンダリレプリカまたはプライマリレプリカに変更することはできません。 |  
|**フェール\_オーバーモード**|**tinyint**|可用性レプリカの[フェールオーバーモード](../../database-engine/availability-groups/windows/failover-and-failover-modes-always-on-availability-groups.md)。次のいずれかになります。<br /><br /> 0 &#124; 自動フェールオーバー。 レプリカは、自動フェールオーバーの潜在的なターゲットです。  自動フェールオーバーは、可用性モードが同期コミット (**可用性\_モード**= 1) に設定されていて、可用性レプリカが現在同期されている場合にのみサポートされます。<br /><br /> 1 &#124; 手動フェールオーバー。 手動フェールオーバーに設定されたセカンダリレプリカへのフェールオーバーは、データベース管理者が手動で開始する必要があります。 実行されるフェールオーバーの種類は、セカンダリレプリカが同期されているかどうかによって異なります。次に例を示します。<br /><br /> 可用性レプリカが同期していない場合、またはまだ同期を行っている場合は、強制フェールオーバーのみが可能です (データが失われる可能性があります)。<br /><br /> 可用性モードが同期コミット (**可用性\_モード**= 1) に設定されていて、可用性レプリカが現在同期されている場合、データ損失のない手動フェールオーバーが発生する可能性があります。<br /><br /> 可用性レプリカ内のすべての可用性データベースのデータベース同期の正常性のロールアップを表示するには、 [dm_hadr_availability_replica_states](../../relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql.md)動的管理ビューの [**同期\_の状態**] 列と [ **\_同期状態\_** ] 列を使用します。 ロールアップでは、各可用性データベースの同期状態と、その可用性レプリカの可用性モードが考慮されます。<br /><br /> **注:** 指定された可用性データベースの同期の正常性を表示するには、 [dm_hadr_database_replica_states](../../relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-states-transact-sql.md)動的管理ビューの [ **\_同期状態**] 列と [**同期\_** 状態] 列に対してクエリを実行します。|  
|**フェール\_オーバー\_モード desc**|**nvarchar (60)**|**フェールオーバー\_モード**の説明。次のいずれかになります。<br /><br /> MANUAL<br /><br /> AUTOMATIC<br /><br /> フェールオーバーモードを変更するには、\_ [ALTER AVAILABILITY GROUP](../../t-sql/statements/alter-availability-group-transact-sql.md) [!INCLUDE[tsql](../../includes/tsql-md.md)]ステートメントのフェールオーバーモードオプションを使用します。|  
|**セッション\_のタイムアウト**|**int**|タイムアウト時間 (秒単位)。 タイムアウト時間は、レプリカが別のレプリカからのメッセージの受信を待機する最大時間です。この時間を過ぎると、プライマリ レプリカとセカンダリ レプリカの間の接続は障害があるものと見なされます。 セッション タイムアウトは、セカンダリ レプリカがプライマリ レプリカに接続されているかどうかを検出します。<br /><br /> セカンダリレプリカとの接続が失敗したことを検出すると、プライマリレプリカはセカンダリレプリカ\_が同期されていないと見なします。 プライマリ レプリカとの接続が確立されていないことを検出すると、セカンダリ レプリカは単に再接続を試みます。<br /><br /> **注:** セッションのタイムアウトでは、自動フェールオーバーは行われません。<br /><br /> この値を変更するには、 [ALTER AVAILABILITY GROUP](../../t-sql/statements/alter-availability-group-transact-sql.md) [!INCLUDE[tsql](../../includes/tsql-md.md)]ステートメントの SESSION_TIMEOUT オプションを使用します。|  
|**プライマリ\_ロール\_で\_の接続の許可**|**tinyint**|可用性ですべての接続を許可するか、読み取り/書き込み接続のみを許可するかは、次のいずれかになります。<br /><br /> 2 = すべて (既定値)<br /><br /> 3 = 読み取り/書き込み|  
|**プライマリ\_ロール\_が\_接続\_を許可する desc**|**nvarchar (60)**|**プライマリ\_\_ロールの接続許可\_** の説明。次のいずれかになります。<br /><br /> ALL<br /><br /> 読み取り\_/書き込み|  
|**セカンダリ\_ロール\_で\_の接続の許可**|**tinyint**|セカンダリ ロールを実行している (つまりセカンダリ レプリカとして機能している) 可用性レプリカがクライアントからの接続を受け入れることができるかどうか。以下のいずれかです。<br /><br /> 0 = いいえ。 セカンダリ レプリカのデータベースに対する接続は許可されず、データベースに対して読み取りアクセスを実行できません。 これが既定の設定です。<br /><br /> 1 = 読み取り専用。 セカンダリ レプリカのデータベースに対しては読み取り専用接続だけが許可されます。 レプリカ内のすべてのデータベースは読み取りアクセスで利用できます。<br /><br /> 2 = すべて。 読み取り専用アクセスに限り、セカンダリ レプリカのデータベースに対するすべての接続が許可されます。<br /><br /> 詳細については、「 [アクティブなセカンダリ: 読み取り可能なセカンダリ レプリカ &#40;AlwaysOn 可用性グループ&#41;](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)での 1 つ以上の可用性グループの構成と管理において重要です。|  
|**secondary_role_allow_connections_desc**|**nvarchar (60)**|**Secondary_role_allow_connections**の説明。次のいずれかになります。<br /><br /> いいえ<br /><br /> READ_ONLY<br /><br /> ALL|  
|**create_date**|**DATETIME**|レプリカが作成された日付。<br /><br /> NULL = このサーバーインスタンスにレプリカがありません。|  
|**modify_date**|**DATETIME**|レプリカが最後に変更された日付。<br /><br /> NULL = このサーバーインスタンスにレプリカがありません。|  
|**backup_priority**|**int**|同じ可用性グループ内の他のレプリカと比較して、このレプリカでバックアップを実行する優先順位を表す、ユーザー指定の値。 値は 0 ～ 100 の範囲の整数です。<br /><br /> 詳細については、「[アクティブなセカンダリ:セカンダリ レプリカでのバックアップ &#40;Always On 可用性グループ&#41;](../../database-engine/availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)」を参照してください。|  
|**read_only_routing_url**|**nvarchar(256)**|読み取り専用可用性レプリカの接続エンドポイント (URL) です。 詳細については、このトピックの後の「 [可用性グループの読み取り専用ルーティングの構成 &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/configure-read-only-routing-for-an-availability-group-sql-server.md)など) を含め、セカンダリ レプリカをホストするサーバー インスタンス上の読み書き可能なデータベースには書き込むことができます。|  
  
## <a name="security"></a>Security  
  
### <a name="permissions"></a>アクセス許可  
 サーバー インスタンスに対する VIEW ANY DEFINITION 権限が必要です。  
  
## <a name="see-also"></a>参照  
 [availability_groups &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md)   
 [AlwaysOn 可用性グループの概要 &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Always On 可用性グループ &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)   
 [Transact-sql&#41;&#40;可用性グループの監視](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)   
 [Transact-sql&#41;&#40;可用性グループの監視](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)  
  
  
