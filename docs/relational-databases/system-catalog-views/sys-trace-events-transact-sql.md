---
title: trace_events (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- trace_events_TSQL
- trace_events
- sys.trace_events
- sys.trace_events_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.trace_events catalog view
ms.assetid: e7d2c5df-0e17-4e94-9d41-d36c7ee60662
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 17bf8ff345e2869d6189491cbf09df49312e1f75
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68106657"
---
# <a name="systrace_events-transact-sql"></a>sys.trace_events (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **Trace_events**カタログビューには、すべての SQL トレースイベントの一覧が含まれています。 これらのトレース イベントは、[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]によって異なることはありません。  
  
> **大事な！** [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]代わりに拡張イベントカタログビューを使用します。  
  
 これらのトレースイベントの詳細については、「 [SQL Server イベントクラスのリファレンス](../../relational-databases/event-classes/sql-server-event-class-reference.md)」を参照してください。  
  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**trace_event_id**|**smallint**|イベントの一意な ID。 この列は、 **trace_event_bindings**および**trace_subclass_values**カタログビューにも含まれています。|  
|**category_id**|**smallint**|イベントのカテゴリ ID。 この列は、 **trace_categories**カタログビューにも含まれています。|  
|**name**|**nvarchar(128**|このイベントの一意な名前。 このパラメーターはローカライズされていません。|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)]詳細については、「[メタデータ表示の構成](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [オブジェクトカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Transact-sql&#41;&#40;のトレース](../../relational-databases/system-catalog-views/sys-traces-transact-sql.md)   
 [trace_categories &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-categories-transact-sql.md)   
 [trace_columns &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-columns-transact-sql.md)   
 [trace_event_bindings &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)   
 [trace_subclass_values &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-subclass-values-transact-sql.md)  
  
  
