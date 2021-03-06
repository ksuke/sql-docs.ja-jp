---
title: dm_pdw_dms_external_work (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 47345015-f861-451e-97c4-6e1cb81d1922
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: a1778cbb88fcd6a4142e800cd45109602509125d
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67899498"
---
# <a name="sysdm_pdw_dms_external_work-transact-sql"></a>dm_pdw_dms_external_work (Transact-sql)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]外部操作のすべてのデータ移動サービス (DMS) ステップに関する情報を保持するシステムビュー。  
  
|列名|データ型|[説明]|Range|  
|-----------------|---------------|-----------------|-----------|  
|request_id|**nvarchar (32)**|この DMS ワーカーを使用しているクエリ。<br /><br /> request_id、step_index、および dms_step_index は、このビューのキーを形成します。|[Dm_pdw_exec_requests &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)の request_id と同じです。|  
|step_index|**int**|この DMS ワーカーを呼び出すクエリステップ。<br /><br /> request_id、step_index、および dms_step_index は、このビューのキーを形成します。|[Dm_pdw_request_steps &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)の step_index と同じです。|  
|dms_step_index|**int**|DMS プランの現在のステップ。<br /><br /> request_id、step_index、および dms_step_index は、このビューのキーを形成します。|[Dm_pdw_dms_workers &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-dms-workers-transact-sql.md)の dms___step_index と同じです。|  
|pdw_node_id|**int**|DMS ワーカーを実行しているノード。|[Dm_pdw_nodes &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)の node_id と同じです。|  
|型|**nvarchar (60)**|このノードが実行されている外部操作の種類。<br /><br /> ファイル分割は、複数の小さい分類に分割されている外部の Hadoop ファイルに対する操作です。|' ファイル分割 '|  
|work_id|**int**|ファイル分割 ID。|0以上。<br /><br /> コンピューティングノードごとに一意です。|  
|input_name|**nvarchar (60)**|読み取る入力の文字列名。|Hadoop ファイルの場合は、Hadoop ファイル名です。|  
|read_location|**bigint**|読み取り場所のオフセット。||  
|estimated_bytes_processed|**bigint**|このワーカーによって処理されたバイト数。|0以上。|  
|length|**bigint**|分割されたファイル内のバイト数。<br /><br /> Hadoop の場合、これは HDFS ブロックのサイズです。|ユーザー定義。 既定値は 64 MB です。|  
|status|**nvarchar (32)**|ワーカーの状態。|保留中、処理中、完了、失敗、中止|  
|start_time|**DATETIME**|このワーカーの実行が開始された時刻。|このワーカーが所属するクエリステップの開始時刻以上。 「 [Sys. dm_pdw_request_steps &#40;transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)」を参照してください。|  
|end_time|**DATETIME**|実行が終了した、失敗した、または取り消された時刻。|実行中またはキューに置かれたワーカーの場合は NULL です。 それ以外の場合は start_time より大きい。|  
|total_elapsed_time|**int**|実行に費やされた合計時間 (ミリ秒単位)。|0以上。<br /><br /> Total_elapsed_time が整数の最大値を超えた場合、total_elapsed_time は引き続き最大値になります。 この条件により、"最大値を超えました。" という警告が生成されます。<br /><br /> ミリ秒単位の最大値は24.8 日に相当します。|  
  
 このビューで保持される最大行数の詳細については、「[容量制限](/azure/sql-data-warehouse/sql-data-warehouse-service-capacity-limits#metadata)」トピックの「メタデータ」セクションを参照してください。
  
## <a name="see-also"></a>参照  
 [システムビュー &#40;Transact-sql&#41;](https://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)  
  
  
