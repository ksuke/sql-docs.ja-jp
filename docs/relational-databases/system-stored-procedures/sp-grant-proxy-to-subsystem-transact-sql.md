---
title: sp_grant_proxy_to_subsystem (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_grant_login_to_subsystem_TSQL
- sp_grant_login_to_subsystem
dev_langs:
- TSQL
helpviewer_keywords:
- sp_grant_proxy_to_subsystem
ms.assetid: 866aaa27-a1e0-453a-9b1b-af39431ad9c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 96e044b94244492202058d6dc2b2f048a9c1db6c
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68123819"
---
# <a name="sp_grant_proxy_to_subsystem-transact-sql"></a>sp_grant_proxy_to_subsystem (Transact-SQL)

[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  サブシステムに対するアクセス権をプロキシに与えます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
sp_grant_proxy_to_subsystem  
     { [ @proxy_id = ] proxy_id | [ @proxy_name = ] 'proxy_name' },  
     { [ @subsystem_id = ] subsystem_id | [ @subsystem_name = ] 'subsystem_name' }  
```  
  
## <a name="arguments"></a>引数  
`[ @proxy_id = ] id`アクセス権を付与するプロキシのプロキシ識別番号を指定します。 *Proxy_id*は**int**,、既定値は NULL です。 *Proxy_id*または*proxy_name*のいずれかを指定する必要がありますが、両方を指定することはできません。  
  
`[ @proxy_name = ] 'proxy_name'`アクセス権を付与するプロキシの名前。 *Proxy_name*は**sysname**で、既定値は NULL です。 *Proxy_id*または*proxy_name*のいずれかを指定する必要がありますが、両方を指定することはできません。  
  
`[ @subsystem_id = ] id`アクセスを許可するサブシステムの id 番号。 *Subsystem_id*は**int**,、既定値は NULL です。 *Subsystem_id*または*subsystem_name*のいずれかを指定する必要がありますが、両方を指定することはできません。 次の表に、各サブシステムの値を示します。  
  
|値|[説明]|  
|-----------|-----------------|  
|**2**|
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX スクリプト<br /><br /> ** \*重要\* \* **ActiveX スクリプティングサブシステムは、の将来[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]の[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]バージョンでエージェントから削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。|  
|**番**|オペレーティングシステム (**CmdExec**)|  
|**4**|レプリケーション スナップショット エージェント|  
|**5/5**|レプリケーション ログ リーダー エージェント|  
|**6**|レプリケーション ディストリビューション エージェント|  
|**7**|レプリケーション マージ エージェント|  
|**8**|Replication Queue Reader Agent|  
|**9**|Analysis Services クエリ|  
|**種類**|Analysis Services コマンド|  
|**11**|[!INCLUDE[ssIS](../../includes/ssis-md.md)]パッケージの実行|  
|**12**|PowerShell スクリプト|  
| &nbsp; | &nbsp; |
  
`[ @subsystem_name = ] 'subsystem_name'`アクセスを許可するサブシステムの名前。 **Subsystem_name**は**sysname**で、既定値は NULL です。 *Subsystem_id*または*subsystem_name*のいずれかを指定する必要がありますが、両方を指定することはできません。 次の表に、各サブシステムの値を示します。  
  
|値|[説明]|  
|-----------|-----------------|  
|**ActiveScripting**| ActiveX スクリプト|  
|**CmdExec**|オペレーティングシステム (**CmdExec**)|  
|**スナップショット**|レプリケーション スナップショット エージェント|  
|**リーダー**|レプリケーション ログ リーダー エージェント|  
|**Distribution**|レプリケーションディストリビューションエージェント|  
|**マージ**|レプリケーション マージ エージェント|  
|**QueueReader**|Replication Queue Reader Agent|  
|**ANALYSISQUERY**|Analysis Services クエリ|  
|**ANALYSISCOMMAND**|Analysis Services コマンド|  
|**Dts**|SSIS パッケージの実行|  
|**PowerShell**|PowerShell スクリプト|  
| &nbsp; | &nbsp; |
  
## <a name="remarks"></a>解説  
 サブシステムへのプロキシアクセスを許可しても、プロキシで指定されたプリンシパルのアクセス許可は変更されません。  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_grant_proxy_to_subsystem**を実行できるのは、 **sysadmin**固定サーバーロールのメンバーだけです。  
  
## <a name="examples"></a>例  
  
### <a name="a-granting-access-to-a-subsystem-by-id"></a>A. ID によってサブシステムへのアクセス権を付与する  
 次の例では、 `Catalog application proxy`プロキシに ActiveX スクリプティングサブシステムへのアクセスを許可します。  
  
```sql
USE msdb ;  
GO  
  
EXEC dbo.sp_grant_proxy_to_subsystem  
    @proxy_name = 'Catalog application proxy',  
    @subsystem_id = 2;  
GO  
```  
  
### <a name="b-granting-access-to-a-subsystem-by-name"></a>B. 名前によってサブシステムへのアクセスを許可します。  
 次の例では、 `Catalog application proxy` SSIS パッケージ実行サブシステムへのアクセス権をプロキシに付与します。  
  
```sql
USE msdb ;  
GO  
  
EXEC dbo.sp_grant_proxy_to_subsystem  
    @proxy_name = N'Catalog application proxy',  
    @subsystem_name = N'Dts' ;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [SQL Server エージェントセキュリティを実装する](../../ssms/agent/implement-sql-server-agent-security.md)   
 [sp_revoke_proxy_from_subsystem &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-revoke-proxy-from-subsystem-transact-sql.md)   
 [sp_add_proxy &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-add-proxy-transact-sql.md)   
 [sp_delete_proxy &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql.md)   
 [sp_update_proxy &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-update-proxy-transact-sql.md)  
  
  
