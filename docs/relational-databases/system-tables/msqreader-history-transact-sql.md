---
title: MSqreader_history (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSqreader_history
- MSqreader_history_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSqreader_history system table
ms.assetid: c5c91d39-513c-4a77-870b-c8ef74a1cd6b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f21873e8db662bc77bd1acbb5d48c6af49aba404
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68032530"
---
# <a name="msqreader_history-transact-sql"></a>MSqreader_history (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSqreader_history**テーブルには、ローカルディストリビューターに関連付けられているキューリーダーエージェントの履歴行が含まれています。 このテーブルは、ディストリビューションデータベースに格納されます。  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|キュー リーダー エージェントの ID|  
|**publication_id**|**int**|パブリケーションの ID です。|  
|**runstatus**|**int**|エージェントの実行状態。<br /><br /> **1** = 開始します。<br /><br /> **2** = 成功します。<br /><br /> **3** = 実行中です。<br /><br /> **4** = アイドル状態。<br /><br /> **5** = 再試行します。<br /><br /> **6** = 失敗。|  
|**start_time**|**DATETIME**|エージェントセッションが開始された日付と時刻。|  
|**time**|**DATETIME**|最後にメッセージがログに記録された日時。|  
|**全**|**int**|ログに記録されたセッションのアクティビティの経過時間 (秒単位)。|  
|**comments**|**nvarchar(255)**|説明のテキスト。|  
|**transaction_id**|**nvarchar (40)**|メッセージと共に格納されるトランザクション ID (該当する場合)。|  
|**transaction_status **|**int**|トランザクションの状態。|  
|**transactions_processed**|**int**|セッションで処理されたトランザクションの累積数。|  
|**commands_processed**|**int**|セッション中に処理されたコマンド数の累計。|  
|**delivery_rate**|**float (53)**|1秒間に配信されたコマンドの平均数。|  
|**transaction_rate**|**float (53)**|処理されたトランザクションの比率。|  
|**サブスクライバ**|**sysname**|サブスクライバーの名前です。|  
|**subscriberdb**|**sysname**|サブスクリプションデータベースの名前。|  
|**error_id**|**int**|0以外の値を指定すると[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 、エラーメッセージが表示されます。|  
|**timestamp**|**timestamp**|テーブルの timestamp 列。|  
  
## <a name="see-also"></a>参照  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーションビュー &#40;Transact-sql&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
