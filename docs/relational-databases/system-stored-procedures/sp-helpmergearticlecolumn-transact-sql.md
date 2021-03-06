---
title: sp_helpmergearticlecolumn (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_helpmergearticlecolumn
- sp_helpmergearticlecolumn_TSQL
helpviewer_keywords:
- sp_helpmergearticlecolumn
ms.assetid: 651c017b-9e9a-48f2-a0bd-6fc896eab334
author: stevestein
ms.author: sstein
ms.openlocfilehash: da2eec998176dfd46ab261fa405ecaa4b6e90044
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68126442"
---
# <a name="sp_helpmergearticlecolumn-transact-sql"></a>sp_helpmergearticlecolumn (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  マージ パブリケーションの指定のテーブルまたはビュー アーティクル内の列の一覧を返します。 ストアド プロシージャには列がないので、アーティクルとしてストアド プロシージャを指定してこのストアド プロシージャを実行するとエラーが返されます。 このストアドプロシージャは、パブリッシャー側でパブリケーションデータベースに対して実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_helpmergearticlecolumn [ @publication = ] 'publication' ]  
        , [ @article= ] 'article' ]  
```  
  
## <a name="arguments"></a>引数  
`[ @publication = ] 'publication'`パブリケーションの名前を指定します。*publication*は**sysname**,、既定値はありません。  
  
`[ @article = ] 'article'`情報を取得するアーティクルであるテーブルまたはビューの名前を指定します。*アーティクル*は**sysname**で、既定値はありません。  
  
## <a name="result-sets"></a>結果セット  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**column_id**|**sysname**|列を識別します。|  
|**column_name**|**sysname**|テーブルまたはビューの列の名前を指定します。|  
|**投稿**|**bit**|列名がパブリッシュされているかどうかを指定します。<br /><br /> **1**は、列がパブリッシュされることを示します。<br /><br /> **0**は、パブリッシュされていないことを示します。|  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>解説  
 **sp_helpmergearticlecolumn**は、マージレプリケーションで使用します。  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_helpmergearticlecolumn**を実行できるのは、ディストリビューションデータベースの**replmonitor**固定データベースロールのメンバー、またはパブリケーションのパブリケーションアクセスリストのメンバーだけです。  
  
## <a name="see-also"></a>参照  
 [システムストアドプロシージャ &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
