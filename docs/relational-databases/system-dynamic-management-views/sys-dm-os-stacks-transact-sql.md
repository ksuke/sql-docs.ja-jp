---
title: dm_os_stacks (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_os_stacks
- dm_os_stacks_TSQL
- sys.dm_os_stacks
- sys.dm_os_stacks_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_stacks dynamic management view
ms.assetid: a69b06c4-28f0-4535-8fa1-9f132db4d916
author: stevestein
ms.author: sstein
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 8f287c548a7ebb71b1ebf3e1bce30e43b412c755
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68265718"
---
# <a name="sysdm_os_stacks-transact-sql"></a>sys.dm_os_stacks (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  この動的管理ビューは、次の[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]操作を実行するためにによって内部的に使用されます。  
  
-   未処理の割り当てなど、デバッグデータを追跡します。  
  
-   コンポーネントが特定の呼び出しが行われ[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]たと想定している場所のコンポーネントによって使用されるロジックを想定または検証します。  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**stack_address**|**varbinary (8)**|このスタック割り当ての一意のアドレス。 NULL 値は許可されません。|  
|**frame_index**|**int**|各行は、特定の**stack_address**に対してフレームインデックスによって昇順に並べ替えられた場合に、完全な呼び出し履歴を返す関数呼び出しを表します。 NULL 値は許可されません。|  
|**frame_address**|**varbinary (8)**|関数呼び出しのアドレス。 NULL 値は許可されません。|  
  
## <a name="remarks"></a>解説  
 **dm_os_stacks**には、サーバーとその他のコンポーネントのシンボルが、情報を正しく表示するためにサーバー上に存在している必要があります。  
  
## <a name="permissions"></a>アクセス許可

で[!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)]は、 `VIEW SERVER STATE`権限が必要です。   
Premium [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]レベルでは、データベース`VIEW DATABASE STATE`の権限が必要です。 Standard [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]レベルおよび Basic レベルでは、**サーバー管理**者または**Azure Active Directory 管理者**アカウントが必要です。   


## <a name="see-also"></a>参照  
  [SQL Server オペレーティングシステム関連の動的管理ビュー &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  
