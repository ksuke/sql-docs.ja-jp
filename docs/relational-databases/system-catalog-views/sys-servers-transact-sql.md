---
title: sys. servers (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- servers_TSQL
- sys.servers_TSQL
- servers
- sys.servers
dev_langs:
- TSQL
helpviewer_keywords:
- sys.servers catalog view
ms.assetid: 4e774ed9-4e83-4726-9f1d-8efde8f9feff
author: stevestein
ms.author: sstein
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: b17296d558c078d3f580e63bf662bb975615ad94
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68132947"
---
# <a name="sysservers-transact-sql"></a>sys. servers (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-asdbmi-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdbmi-xxxx-xxx-md.md)]

  登録されているリンクまたはリモートサーバーごとに1行、および**server_id** = 0 のローカルサーバーの行が含まれています。  

|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**server_id**|**int**|リンクサーバーのローカル ID。|  
|**name**|**sysname**|**Server_id** = 0 の場合、返される値はサーバー名です。<br /><br /> **Server_id** > 0 の場合、返される値はリンクサーバーのローカル名になります。|  
|**梱包**|**sysname**|リンクサーバーの製品名。 値 "SQL Server" は、の別の[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]インスタンスを示します。|  
|**provider**|**sysname**|リンク サーバー接続用の OLE DB プロバイダー名です。|  
|**data_source**|**nvarchar(4000)**|データソース接続プロパティを OLE DB します。|  
|**設置**|**nvarchar(4000)**|OLE DB 場所接続プロパティです。 None の場合は NULL です。|  
|**provider_string**|**nvarchar(4000)**|OLE DB プロバイダー文字列接続プロパティです。<br /><br /> 呼び出し側に ALTER ANY LINKED SERVER 権限がなければ NULL になります。|  
|**カタログ**|**sysname**|OLEDB カタログの接続プロパティ。 None の場合は NULL です。|  
|**connect_timeout**|**int**|接続タイムアウト (秒単位)、0 (なしの場合)。|  
|**query_timeout**|**int**|クエリタイムアウト (秒単位)。存在しない場合は0です。|  
|**is_linked**|**bit**|0 = **sp_addserver**を使用して追加された古い形式のサーバーであり、RPC と分散トランザクションの動作が異なります。<br /><br /> 1 の場合、標準リンク サーバーです。|  
|**is_remote_login_enabled**|**bit**|RPC オプションは、このサーバーの受信リモートログインを有効にするように設定されています。|  
|**is_rpc_out_enabled**|**bit**|(このサーバーからの) 発信 RPC が有効です。|  
|**is_data_access_enabled**|**bit**|サーバーで分散クエリが有効になっています。|  
|**is_collation_compatible**|**bit**|リモート データの照合順序は、照合順序に関する情報がない場合にはローカル データと互換性があると見なされます。|  
|**uses_remote_collation**|**bit**|1 の場合、リモート サーバーによってレポートされる照合順序を使用し、それ以外の場合は、次の列で指定された照合順序を使用します。|  
|**collation_name**|**sysname**|使用する照合順序名です。ローカルを使用するだけの場合は NULL です。|  
|**lazy_schema_validation**|**bit**|1の場合、クエリの起動時にスキーマの検証は確認されません。|  
|**is_system**|**bit**|このサーバーには、内部システムによってのみアクセスできます。|  
|**is_publisher**|**bit**|サーバーはレプリケーションパブリッシャーです。|  
|**is_subscriber**|**bit**|サーバーはレプリケーション サブスクライバーです。|  
|**is_distributor**|**bit**|サーバーはレプリケーション ディストリビューターです。|  
|**is_nonsql_subscriber**|**bit**|サーバーは SQL Server 以外のレプリケーション サブスクライバーです。|  
|**is_remote_proc_transaction_promotion_enabled**|**bit**|1の場合、リモートストアドプロシージャを呼び出すと分散トランザクションが開始され、トランザクションは MS DTC に参加します。 詳細については、「 [sp_serveroption &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-serveroption-transact-sql.md)からデータにアクセスする方法について説明します。|  
|**modify_date**|**DATETIME**|サーバー情報が前回変更された日付です。|  
  
## <a name="permissions"></a>アクセス許可  
 **Provider_string**の値は、呼び出し元が ALTER ANY LINKED SERVER 権限を持っていない限り、常に NULL になります。  
  
 ローカルサーバーを表示するためにアクセス許可は必要ありません (**server_id** = 0)。  
  
 リンクサーバーまたはリモートサーバーを作成する[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]と、によって、既定のログインマッピングが**public**サーバーロールに対して作成されます。 既定のログインマッピングは、すべてのログインがリンクされたサーバーとリモートサーバーをすべて表示できることを意味します。 これらのサーバーの可視性を制限するには、 [sp_droplinkedsrvlogin](../../relational-databases/system-stored-procedures/sp-droplinkedsrvlogin-transact-sql.md)を実行し、 *LOCALLOGIN*パラメーターに NULL を指定することで、既定のログインマッピングを削除します。  
  
 既定のログインマッピングが削除された場合、リンクされたログインまたはリモートログインとして明示的に追加されたユーザーのみが、ログインがあるリンクサーバーまたはリモートサーバーを表示できます。  既定のログインマッピングの後、すべてのリンクサーバーとリモートサーバーを表示するには、次のアクセス許可が必要です。  
  
- `ALTER ANY LINKED SERVER`もしくは`ALTER ANY LOGIN ON SERVER`  
- **Setupadmin**または**sysadmin**固定サーバーロールのメンバーシップ  
  
## <a name="see-also"></a>参照  
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [リンクサーバーのカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/linked-servers-catalog-views-transact-sql.md)   
 [sp_addlinkedsrvlogin &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-addlinkedsrvlogin-transact-sql.md)   
 [sp_addremotelogin &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-addremotelogin-transact-sql.md)  
  
  
