---
title: sysalerts (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 10/24/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysalerts
- sysalerts_TSQL
- dbo.sysalerts_TSQL
- sysalerts
dev_langs:
- TSQL
helpviewer_keywords:
- sysalerts system table
ms.assetid: a2c2f50d-61f3-4951-996a-add5ad092cc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4645b586c07635a405b2e678b84c4846762f7582
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68084685"
---
# <a name="dbosysalerts-transact-sql"></a>sysalerts (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  警告 1 件につき 1 行のデータを格納します。 アラートは、イベントへの応答として送信されるメッセージです。 警告メッセージは [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 環境の外に転送でき、電子メールやポケットベルのメッセージとして送信することもできます。 また、警告でタスクを生成することもできます。  このテーブルは、 **msdb**データベースに格納されます。
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**番号**|**int**|警告 ID。|  
|**name**|**sysname**|アラート名。|  
|**event_source**|**nvarchar (100)**|イベントのソース ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)])。|  
|**event_category_id**|**int**|将来使用するために予約されています。|  
|**event_id**|**int**|将来使用するために予約されています。|  
|**message_id**|**int**|この警告をトリガーするユーザー定義のメッセージ ID または**sysmessages**メッセージへの参照。|  
|**順**|**int**|このアラートをトリガーする重要度。|  
|**enabled**|**tinyint**|アラートの状態:<br /><br /> **0** = 無効です。<br /><br /> **1** = 有効。|  
|**delay_between_responses**|**int**|このアラートの通知間の待機時間 (秒単位)。|  
|**last_occurrence_date**|**int**|アラートの最終発生日 (日付)。|  
|**last_occurrence_time**|**int**|前回の警告発生時刻。|  
|**last_response_date**|**int**|前回の警告通知日。|  
|**last_response_time**|**int**|アラートの最後の通知 (時刻)。|  
|**notification_message**|**nvarchar(512)**|アラートと共に送信される追加情報。|  
|**include_event_description**|**tinyint**|イベントの説明が電子メール、ポケットベル、または Net send のどちらで送信されるかを表すビットマスク。 値については、次のグラフを参照してください。|  
|**database_name**|**nvarchar(512)**|このアラートをトリガーするためにこの警告が発生する必要があるデータベース。|  
|**event_description_keyword**|**nvarchar (100)**|警告をトリガーするために、エラーが一致する必要があるパターン。|  
|**occurrence_count**|**int**|警告の発生回数。|  
|**count_reset_date**|**int**|日 (日付) のカウントは**0**にリセットされます。|  
|**count_reset_time**|**int**|時刻のカウントは**0**にリセットされます。|  
|**job_id**|**UNIQUEIDENTIFIER**|警告が発生したときに実行するタスクの ID。|  
|**has_notification**|**int**|アラートが発生したときに電子メール通知を受信するオペレーターの数。|  
|**示す**|**int**|予約済み。|  
|**performance_condition**|**nvarchar(512)**|予約済み。|  
|**category_id**|**int**|予約済み。|  
  
 ## <a name="remarks"></a>解説

次の表は、include_event_description ビットマスクの値を示しています。 10進値は、sysalerts によって返されます。 

|decimal | binary | 意味 |
|------|------|------|
|0 |0000 |メッセージがありません |
|1 で保護されたプロセスとして起動されました |0001 |電子メール |
|2 |mylnxstorage02 |pager |
|3 |myhpccn-0011 |ポケットベルと電子メール |
|4 |0100 |[Net Send] |
|5 |0101 |Net send と電子メール |
|6 |0110 |Net send とポケットベル |
|7 |0111 |Net send、ポケットベル、電子メール |
  
