---
title: dm_hadr_name_id_map (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_hadr_name_id_map
- sys.dm_hadr_name_id_map_TSQL
- dm_hadr_name_id_map
- dm_hadr_name_id_map_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- sys.dm_hadr_name_id_map dynamic management view
ms.assetid: e07bb8a9-37de-4a39-a257-950d7c3ae8fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4fc446efc410ff13d5697c7ab195e3e3895b4839
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67900432"
---
# <a name="sysdm_hadr_name_id_map-transact-sql"></a>dm_hadr_name_id_map (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  の現在の[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]インスタンスが、可用性グループ ID、WSFC リソース id、および WSFC グループ id という3つの一意の id に結合した Always On 可用性グループのマッピングを示します。 このマッピングの目的は、WSFC リソースまたは WSFC グループの名前が変更されるシナリオを処理することです。  
   
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**ag_name**|**nvarchar(256)**|可用性グループの名前。 これは、Windows Server フェールオーバークラスター (WSFC) クラスター内で一意である必要があるユーザー指定の名前です。|  
|**ag_id**|**UNIQUEIDENTIFIER**|可用性グループの一意識別子 (GUID)。|  
|**ag_resource_id**|**nvarchar(256)**|WSFC クラスターのリソースとしての可用性グループの一意な ID。|  
|**ag_group_id**|**nvarchar(256)**|可用性グループの一意の WSFC グループ ID。|  
  
## <a name="permissions"></a>アクセス許可  
 サーバーに対する VIEW SERVER STATE 権限が必要です。  
  
## <a name="see-also"></a>参照  
 [Always On 可用性グループの動的管理ビューおよび関数 &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/always-on-availability-groups-dynamic-management-views-functions.md)   
 [Always On 可用性グループのカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)   
 [Transact-sql&#41;&#40;可用性グループの監視](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)   
 [Always On 可用性グループ &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
