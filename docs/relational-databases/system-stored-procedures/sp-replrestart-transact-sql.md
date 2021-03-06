---
title: sp_replrestart (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_replrestart_TSQL
- sp_replrestart
helpviewer_keywords:
- sp_replrestart
ms.assetid: 111b3dbf-92f8-4670-b156-1468c63e4fc1
author: stevestein
ms.author: sstein
ms.openlocfilehash: a9108ab25d1a23e06ccd93daad5f755a3a65aa44
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68770890"
---
# <a name="sp_replrestart-transact-sql"></a>sp_replrestart (Transact-SQL)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

  バックアップや復元の際にトランザクション レプリケーションで使用します。これにより、ディストリビューター側のレプリケートされたデータとパブリッシャー側のデータとを同期することができます。 このストアドプロシージャは、パブリッシャー側でパブリケーションデータベースに対して実行されます。  
  
> [!IMPORTANT]  
>  **sp_replrestart**は内部レプリケーションストアドプロシージャであり、スナップショットレプリケーションおよび[トランザクションレプリケーションのバックアップと復元の方法に関する](../../relational-databases/replication/administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md)トピックで説明されているように、トランザクションレプリケーショントポロジでパブリッシュされたデータベースを復元する場合にのみ使用する必要があります。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_replrestart  
```  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>解説  
 **sp_replrestart**は、ディストリビューターで最も大きいログシーケンス番号 (lsn) の値がパブリッシャーの最大 lsn 値と一致しない場合に使用されます。  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_replrestart**を実行できるのは、固定サーバーロール**sysadmin**または固定データベースロール**db_owner**のメンバーだけです。  
  
## <a name="see-also"></a>参照  
 [レプリケーションストアドプロシージャ &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
