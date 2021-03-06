---
title: MSpeer_topologyrequest (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_topologyrequest_TSQL
- MSpeer_topologyrequest
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_topologyrequest
ms.assetid: c644814b-4e40-44d7-b6b4-5954b0d4db7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29ea5e7e78d274eaf289afbd6ca73f97cd479679
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68026660"
---
# <a name="mspeer_topologyrequest-transact-sql"></a>MSpeer_topologyrequest (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  ピアツーピアレプリケーションで、パブリケーションのトポロジ状態要求を追跡するために使用されます。 このテーブルは、パブリケーションデータベースに格納されます。  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|id|**int**|トポロジ状態要求を識別します。 [MSpeer_topologyresponse](../../relational-databases/system-tables/mspeer-topologyresponse-transact-sql.md)の request_id 列には、この値が使用されます。|  
|パブリケーション (publication)|**sysname**|トポロジ状態要求が発行されたパブリケーションの名前です。|  
|sent_date|**DATETIME**|トポロジ状態要求が開始された日付と時刻。|  
  
## <a name="see-also"></a>参照  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーションビュー &#40;Transact-sql&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
