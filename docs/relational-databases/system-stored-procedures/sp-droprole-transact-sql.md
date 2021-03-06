---
title: sp_droprole (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_droprole
- sp_droprole_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_droprole
ms.assetid: 889ee074-00f8-40a9-bddb-d7d3ef0cbc19
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2573019948a326c9171fc83d62428e7e2f888eb5
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67933817"
---
# <a name="sp_droprole-transact-sql"></a>sp_droprole (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  現在のデータベースからデータベース ロールを削除します。  
  
> [!IMPORTANT]  
>  で[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]は、 **sp_droprole**は DROP ROLE ステートメントに置き換えられました。 **sp_droprole**は、以前のバージョンのとの互換性[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のためだけに含まれており、将来のリリースではサポートされない可能性があります。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_droprole [ @rolename= ] 'role'  
```  
  
## <a name="arguments"></a>引数  
`[ @rolename = ] 'role'`現在のデータベースから削除するデータベースロールの名前を指定します。 *role*は**sysname**で、既定値はありません。 *ロール*は、現在のデータベースに既に存在している必要があります。  
  
## <a name="return-code-values"></a>リターン コードの値  
 0 (成功) または 1 (失敗)  
  
## <a name="remarks"></a>解説  
 **Sp_droprole**を使用すると、データベースロールのみを削除できます。  
  
 メンバーが既に存在するデータベース ロールは削除できません。 データベース ロールを削除するには、あらかじめそのデータベース ロールのすべてのメンバーを削除しておく必要があります。 ロールからユーザーを削除するには、 **sp_droprolemember**を使用します。 ロールのメンバーであるユーザーがいる場合、 **sp_droprole**にはそれらのメンバーが表示されます。  
  
 固定ロールと**パブリック**ロールは削除できません。  
  
 Securables を所有している場合、ロールを削除することはできません。 セキュリティ保護可能なリソースを所有しているアプリケーション ロールを削除するには、先にセキュリティ保護可能なリソースの所有権を譲渡するか削除する必要があります。 削除しないオブジェクトの所有者を変更するには、ALTER AUTHORIZATION を使用します。  
  
 **sp_droprole**は、ユーザー定義のトランザクション内では実行できません。  
  
## <a name="permissions"></a>アクセス許可  
 ロールに対する CONTROL 権限が必要です。  
  
## <a name="examples"></a>例  
 次の例では、アプリケーション ロール `Sales` を削除します。  
  
```  
EXEC sp_droprole 'Sales';  
GO  
```  
  
## <a name="see-also"></a>参照  
 [セキュリティストアドプロシージャ &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [sp_addrole &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-addrole-transact-sql.md)   
 [DROP ROLE &#40;Transact-sql&#41;](../../t-sql/statements/drop-role-transact-sql.md)   
 [ALTER AUTHORIZATION &#40;Transact-sql&#41;](../../t-sql/statements/alter-authorization-transact-sql.md)   
 [sp_dropapprole &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-dropapprole-transact-sql.md)   
 [システムストアドプロシージャ &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
