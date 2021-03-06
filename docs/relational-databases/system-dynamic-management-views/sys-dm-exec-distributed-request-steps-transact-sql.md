---
title: dm_exec_distributed_request_steps (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- SYS.DM_EXEC_DISTRIBUTED_REQUEST_STEPS_TSQL
- DM_EXEC_DISTRIBUTED_REQUEST_STEPS_TSQL
- DM_EXEC_DISTRIBUTED_REQUEST_STEPS
dev_langs:
- TSQL
helpviewer_keywords:
- PolyBase,views
- PolyBase
- dm_exec_distributed_request_steps
- sys.dm_exec_distributed_request_steps management view
ms.assetid: 1954541d-b716-4e03-8fcc-7022f428e01d
author: stevestein
ms.author: sstein
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: b5c40ce6d1c7b7ef85f24fc8032559e000d89be1
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68097823"
---
# <a name="sysdm_exec_distributed_request_steps-transact-sql"></a>dm_exec_distributed_request_steps (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  指定された PolyBase 要求またはクエリを構成するすべてのステップに関する情報を保持します。 クエリステップごとに1行が表示されます。  
  
|列名|データ型|[説明]|Range|  
|-----------------|---------------|-----------------|-----------|  
|execution_id|**int**|execution_id と step_index このビューのキーを構成します。 要求に関連付けられている一意の数値 id。|詳細については、「 [sys. dm_exec_requests &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md)」を参照してください。|  
|step_index|**int**|要求を構成する一連の手順におけるこのステップの位置。|n 個の手順を含む要求の場合は 0 ~ (n-1)。|  
|operation_type|**nvarchar(128**|このステップで表される操作の種類。|' MoveOperation '、' OnOperation '、' RandomIDOperation '、' RemoteOperation '、' Returnoperation) '、' ShuffleMoveOperation '、' TempTablePropertiesOperation '、' DropDiagnosticsNotifyOperation '、' HadoopShuffleOperation '、' HadoopBroadCastOperation '、'HadoopRoundRobinOperation'|  
|distribution_type|**nvarchar (32)**|ステップが実行されている場所です。|' AllComputeNodes '、' AllDistributions '、' CompuSubsetNodes '、' Distribution '、' Alldistributions '、' '、' SubsetDistributions '、' 未指定 '。|  
|location_type|**nvarchar (32)**|ステップが実行されている場所です。|' Compute '、' Head '、または ' DMS '。 すべてのデータ移動手順は、"DMS" を示しています。|  
|status|**nvarchar (32)**|この手順の状態|' Pending '、' Running '、' Complete '、' Failed '、' UndoFailed '、' PendingCancel '、' 取り消し済み '、' 元に戻す '、' Aborted '|  
|error_id|**nvarchar (36)**|このステップに関連付けられているエラーの一意の id (存在する場合)|エラーが発生しなかった場合は、「id of [sys. dm_exec_compute_node_errors &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-node-errors-transact-sql.md)」を参照してください。|  
|start_time|**DATETIME**|ステップが実行を開始した時刻|小さいまたは現在の時刻に等しいが、このステップが属するクエリの end_compile_time 以上です。|  
|end_time|**DATETIME**|このステップの実行が完了した時刻。が取り消されたか、失敗しました。|小または現在の時刻に等しいか start_time 以上で、現在実行中またはキューに置かれているステップに対して NULL に設定されます。|  
|total_elapsed_time|**int**|クエリステップが実行されていた合計時間 (ミリ秒)|0 ~ end_time と start_time の差。 キューに登録されたステップの場合は0。|  
|row_count|**bigint**|この要求によって変更または返された行の合計数|データが変更または返されなかったステップの場合は0。それ以外の場合は、影響を受けた行の数。 DMS ステップの場合は-1 に設定します。|  
|command|nvarchar(4000)|このステップのコマンドの完全なテキストを保持します。|ステップの任意の有効な要求文字列。 4000文字を超える場合は切り捨てられます。|  
  
## <a name="see-also"></a>参照  
 [動的管理ビューを使用した PolyBase のトラブルシューティング](https://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [動的管理ビューと動的管理関数 &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Transact-sql&#41;&#40;データベース関連の動的管理ビュー](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  
