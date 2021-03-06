---
title: sp_help_log_shipping_secondary_database (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 08/02/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_help_log_shipping_secondary_database
- sp_help_log_shipping_secondary_database_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_log_shipping_secondary_database
ms.assetid: 11ce42ca-d3f1-44c8-9cac-214ca8896b9a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65c4cd3f6ca07f2c3cb35dc7dcbaad373930ecc5
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68066809"
---
# <a name="sp_help_log_shipping_secondary_database-transact-sql"></a>sp_help_log_shipping_secondary_database (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  1 つ以上のセカンダリ データベースの設定を取得します。  
  

  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_help_log_shipping_secondary_database  
[ @secondary_database = ] 'secondary_database' OR  
[ @secondary_id = ] 'secondary_id'  
```  
  
## <a name="arguments"></a>引数  
`[ @secondary_database = ] 'secondary_database'`セカンダリデータベースの名前を指定します。 *secondary_database*は**sysname**であり、既定値はありません。  
  
`[ @secondary_id = ] 'secondary_id'`ログ配布構成におけるセカンダリサーバーの ID。 *secondary_id*は**uniqueidentifier**であり、NULL にすることはできません。  
  
## <a name="return-code-values"></a>リターン コードの値  
 0 (成功) または 1 (失敗)  
  
## <a name="result-sets"></a>結果セット  
  
|列名|[説明]|  
|-----------------|-----------------|  
|**secondary_id**|ログ配布構成におけるセカンダリ サーバーの ID。|  
|**primary_server**|ログ配布構成における [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]のプライマリ インスタンスの名前。|  
|**primary_database**|ログ配布構成のプライマリデータベースの名前。|  
|**backup_source_directory**|プライマリサーバーからのトランザクションログバックアップファイルが格納されているディレクトリ。|  
|**backup_destination_directory**|バックアップファイルのコピー先となるセカンダリサーバー上のディレクトリ。|  
|**file_retention_period**|バックアップファイルが削除される前にセカンダリサーバーで保持される時間 (分単位)。|  
|**copy_job_id**|セカンダリ サーバーでのコピー ジョブに関連付けられた ID。|  
|**restore_job_id**|セカンダリサーバー上の復元ジョブに関連付けられている ID。|  
|**monitor_server**|ログ配布構成で監視サーバーと[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]して使用されているのインスタンスの名前。|  
|**monitor_server_security_mode**|監視サーバーへの接続に使用されるセキュリティモード。<br /><br /> 1 = [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 認証。<br /><br /> 0 = [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]認証。|  
|**secondary_database**|ログ配布構成のセカンダリデータベースの名前。|  
|**restore_delay**|指定されたバックアップファイルを復元する前に、セカンダリサーバーが待機する時間 (分単位)。 既定値は、0 分です。|  
|**restore_all**|1 に設定すると、セカンダリ サーバーでは復元ジョブの実行時にすべてのトランザクション ログ バックアップが復元されます。 それ以外の場合は、1つのファイルが復元された後に停止します。|  
|**restore_mode**|セカンダリデータベースの復元モード。<br /><br /> 0 = with NORECOVERY を使用してログを復元します。<br /><br /> 1 = スタンバイ状態のログを復元します。|  
|**disconnect_users**|1に設定すると、復元操作の実行時にユーザーがセカンダリデータベースから切断されます。 既定値は 0 です。|  
|**block_size**|バックアップデバイスのブロックサイズとして使用されるサイズ (バイト単位)。|  
|**buffer_count**|バックアップまたは復元操作によって使用されるバッファーの合計数。|  
|**max_transfer_size**|によって[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]バックアップデバイスに発行される入力要求または出力要求の最大サイズ (バイト単位)。|  
|**restore_threshold**|復元操作の間に、アラートが生成されるまでの経過時間 (分単位)。|  
|**threshold_alert**|復元のしきい値を超えたときに発生する警告。|  
|**threshold_alert_enabled**|復元のしきい値の警告を有効にするかどうか。<br /><br /> 1 = 有効。<br /><br /> 0 = 無効です。|  
|**last_copied_file**|セカンダリ サーバーにコピーされた最後のバックアップ ファイルの名前。|  
|**last_copied_date**|セカンダリサーバーに最後にコピー操作を行った日時です。|  
|**last_copied_date_utc**|セカンダリサーバーへの最後のコピー操作の日時。協定世界時で表されます。|  
|**last_restored_file**|セカンダリデータベースに復元された最後のバックアップファイルのファイル名。|  
|**last_restored_date**|セカンダリデータベースに対する最後の復元操作の日時。|  
|**last_restored_date_utc**|セカンダリデータベースでの最後の復元操作の日時。協定世界時で表されます。|  
|**history_retention_period**|指定されたセカンダリデータベースのログ配布履歴レコードが保持されてから削除されるまでの時間 (分単位)。|  
|**last_restored_latency**|ログバックアップがプライマリで作成されてからセカンダリに復元されるまでの経過時間 (分単位)。<br /><br /> 初期値が NULL です。|  
  
## <a name="remarks"></a>解説  
 *Secondary_database*パラメーターを指定した場合、結果セットにはそのセカンダリデータベースに関する情報が含まれます。*secondary_id*パラメーターを指定した場合、結果セットには、そのセカンダリ id に関連付けられているすべてのセカンダリデータベースに関する情報が含まれます。  
  
 **sp_help_log_shipping_secondary_database**は、セカンダリサーバーの**master**データベースから実行する必要があります。  
  
## <a name="permissions"></a>アクセス許可  
 このプロシージャを実行できるのは、 **sysadmin**固定サーバーロールのメンバーだけです。  
  
## <a name="see-also"></a>参照  
 [sp_help_log_shipping_secondary_primary &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-help-log-shipping-secondary-primary-transact-sql.md)   
 [ログ配布について &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [システムストアドプロシージャ &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
