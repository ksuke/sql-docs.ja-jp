---
title: sp_helpxactsetjob (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_helpxactsetjob
- sp_helpxactsetjob_TSQL
helpviewer_keywords:
- sp_helpxactsetjob
ms.assetid: 242cea3e-e6ac-4f84-a072-b003b920eb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0fdd70480a63e334aa3e178d19287b30937e2f53
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "74056793"
---
# <a name="sp_helpxactsetjob-transact-sql"></a>sp_helpxactsetjob (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Oracle パブリッシャーの Xactset ジョブに関する情報を表示します。 このストアドプロシージャは、ディストリビューター側で任意のデータベースに対して実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_helpxactsetjob [ @publisher = ] 'publisher'   
```  
  
## <a name="arguments"></a>引数  
`[ @publisher = ] 'publisher'`ジョブが属する以外の[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]パブリッシャーの名前を指定します。 *publisher*は**sysname**で、既定値はありません。  
  
## <a name="result-sets"></a>結果セット  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**jobnumber**|**int**|Oracle ジョブ番号。|  
|**lastdate**|**varchar (22)**|ジョブが最後に実行された日付。|  
|**この日付**|**varchar (22)**|変更時刻です。|  
|**nextdate**|**varchar (22)**|ジョブが実行される次の日。|  
|**分解**|**varchar (1)**|ジョブが中断されたかどうかを示すフラグです。|  
|**定期的**|**varchar (200)**|ジョブの間隔。|  
|**回**|**int**|ジョブの失敗の回数です。|  
|**xactsetjobwhat**|**varchar (200)**|ジョブによって実行されるプロシージャの名前。|  
|**xactsetjob**|**varchar (1)**|ジョブの状態。次のいずれかを指定できます。<br /><br /> **1** -ジョブが有効になっています。<br /><br /> **0** -ジョブは無効です。|  
|**xactsetlonginterval**|**int**|ジョブの長い間隔です。|  
|**xactsetlongthreshold**|**int**|ジョブの長いしきい値。|  
|**xactsetshortinterval**|**int**|ジョブの短い間隔。|  
|**xactsetshortthreshold**|**int**|ジョブの短いしきい値です。|  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>解説  
 **sp_helpxactsetjob**は、Oracle パブリッシャーのスナップショットレプリケーションおよびトランザクションレプリケーションで使用します。  
  
 **sp_helpxactsetjob**は、常にパブリッシャーで Xactset ジョブ (HREPL_XactSetJob) の現在の設定を返します。 Xactset ジョブが現在ジョブキューにある場合は、Oracle パブリッシャーの管理者アカウントで作成された USER_JOB データディクショナリビューから、さらにジョブの属性が返されます。  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_helpxactsetjob**を実行できるのは、 **sysadmin**固定サーバーロールのメンバーだけです。  
  
## <a name="see-also"></a>参照  
 [Oracle パブリッシャー &#40;レプリケーション Transact-sql プログラミングのトランザクションセットジョブの構成&#41;](../../relational-databases/replication/administration/configure-the-transaction-set-job-for-an-oracle-publisher.md)   
 [sp_publisherproperty &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql.md)  
  
  
