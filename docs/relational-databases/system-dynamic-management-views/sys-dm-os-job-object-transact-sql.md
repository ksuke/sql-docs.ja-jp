---
title: dm_os_job_object (Azure SQL Database) |Microsoft Docs
ms.custom: ''
ms.date: 02/11/2020
ms.service: sql-database
ms.reviewer: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_db_resource_stats
- sys.dm_db_resource_stats_TSQL
- dm_db_resource_stats
- dm_db_resource_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_db_resource_stats
- dm_db_resource_stats
ms.assetid: 6e76b39f-236e-4bbf-b0b5-38be190d81e8
author: julieMSFT
ms.author: jrasnick
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: b7674e3e7696d91170f9bf955808923d713479a1
ms.sourcegitcommit: 9bdecafd1aefd388137ff27dfef532a8cb0980be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "77147411"
---
# <a name="sysdm_os_job_object-azure-sql-database"></a>sys.dm_os_job_object (Azure SQL Database)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

SQL Server プロセスを管理するジョブオブジェクトの構成と、ジョブオブジェクトレベルでの特定のリソース消費量の統計を示す1行のデータを返します。 SQL Server がジョブオブジェクトで実行されていない場合は、空のセットを返します。

ジョブオブジェクトは、オペレーティングシステムレベルで CPU、メモリ、および IO リソースガバナンスを実装する Windows コンストラクトです。 ジョブオブジェクトの詳細については、「 [Job objects](/windows/desktop/ProcThread/job-objects)」を参照してください。
  
|[列]|データ型|[説明]|  
|-------------|---------------|-----------------|  
|cpu_rate|**int**|SQL Server のスレッドが各スケジューリング間隔中に使用できるプロセッササイクルの部分を指定します。 この値は、1万サイクルのスケジュール間隔で、使用可能なサイクルの割合として報告されます。 たとえば、値100は、スレッドが CPU コアを使用できることを意味します。|
|cpu_affinity_mask|**bigint**|SQL Server プロセスがプロセッサグループ内で使用できる論理プロセッサを示すビットマスク。 たとえば、cpu_affinity_mask 255 (バイナリでは 1111 1111) は、最初の8個の論理プロセッサを使用できることを意味します。 <br /><br />この列は、下位互換性のために用意されています。 プロセッサグループに64個を超える論理プロセッサが含まれている場合、プロセッサグループは報告されず、報告された値が正しくない可能性があります。 代わりに、 `process_physical_affinity`列を使用してプロセッサの関係を判断してください。|
|cpu_affinity_group|**int**|SQL Server によって使用されるプロセッサグループの番号。|
|memory_limit_mb|**bigint**|コミットされたメモリの最大量 (MB 単位)。ジョブオブジェクト内のすべてのプロセス (SQL Server を含む) で累積的を使用できます。| 
|process_memory_limit_mb |**bigint**|SQL Server など、ジョブオブジェクト内の1つのプロセスが使用できるコミット済みメモリの最大量 (MB 単位)。|
|workingset_limit_mb |**bigint**|SQL Server ワーキングセットが使用できるメモリの最大量 (MB 単位)。|
|non_sos_mem_gap_mb|**bigint**|スレッドスタック、Dll、およびその他の SOS 以外のメモリ割り当てに対して確保されるメモリの量 (MB 単位)。 SOS ターゲットメモリは`process_memory_limit_mb` 、と`non_sos_mem_gap_mb`の差です。| 
|low_mem_signal_threshold_mb|**bigint**|メモリのしきい値 (MB 単位)。 ジョブオブジェクトで使用可能なメモリの量がこのしきい値を下回ると、メモリ不足の通知信号が SQL Server プロセスに送信されます。 |
|total_user_time|**bigint**|ジョブオブジェクトが作成されてから、ジョブオブジェクト内のスレッドがユーザーモードで費やした 100 ns タイマー刻みの合計数。 |
|total_kernel_time |**bigint**|ジョブオブジェクトが作成されてから、ジョブオブジェクト内のスレッドがカーネルモードで消費した 100 ns タイマー刻みの合計数。 |
|write_operation_count |**bigint**|ジョブオブジェクトが作成されてから、SQL Server によって発行されたローカルディスク上の書き込み IO 操作の合計数。 |
|read_operation_count |**bigint**|ジョブオブジェクトが作成されてから、SQL Server によって発行されたローカルディスク上の読み取り IO 操作の合計数。 |
|peak_process_memory_used_mb|**bigint**|ジョブオブジェクトが作成されてから、SQL Server など、ジョブオブジェクト内の1つのプロセスが使用していたメモリのピーク容量 (MB 単位)。| 
|peak_job_memory_used_mb|**bigint**|ジョブオブジェクトが作成されてから、ジョブオブジェクト内のすべてのプロセスが累積的を使用したメモリのピーク容量 (MB 単位)。|
|process_physical_affinity|**nvarchar (3072)**|SQL Server プロセスが各プロセッサグループで使用できる論理プロセッサを示すビットマスク。 この列の値は、それぞれ中かっこで囲まれた1つ以上の値のペアで形成されます。 各ペアでは、最初の値はプロセッサグループ番号、2番目の値はそのプロセッサグループの関係ビットマスクです。 `{{0,a}{1,2}}`たとえば、値は、プロセッサグループ`0`の関係マスクが`a` (`1010`プロセッサ2と4が使用されていることを示すバイナリ) で、プロセッサグループ`1`の関係マスクが`2` (`10`プロセッサ2が使用されていることを示すバイナリ) であることを意味します。|
  
## <a name="permissions"></a>アクセス許可  
SQL Database Managed Instance では、 `VIEW SERVER STATE`権限が必要です。 SQL Database では、データベースにおける `VIEW DATABASE STATE` アクセス許可が必要です。  
 
## <a name="see-also"></a>参照  

マネージインスタンスの詳細については、「 [SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)」を参照してください。
  
