---
title: database_recovery_status (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 08/12/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- database_recovery_status_TSQL
- database_recovery_status
- sys.database_recovery_status
- sys.database_recovery_status_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.database_recovery_status catalog view
ms.assetid: 46fab234-1542-49be-8edf-aa101e728acf
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e78b5a8640918291fc68e5b4882448b94a1b9d1
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68079521"
---
# <a name="sysdatabase_recovery_status-transact-sql"></a>sys.database_recovery_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  データベースごとに1行のデータを格納します。 データベースが起動していない場合は、[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] によってデータベースの起動が試行されます。  
  
 **Master**または**tempdb**以外のデータベースの行を表示するには、次のいずれかを適用する必要があります。  
  
-   データベースの所有者である。  
  
-   ALTER ANY DATABASE または VIEW ANY DATABASE サーバーレベルの権限が必要です。  
  
-   **Master**データベースの CREATE DATABASE 権限を持っている。    
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**database_id**|**int**|
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンス内で一意のデータベースの ID です。|  
|**database_guid**|**UNIQUEIDENTIFIER**|1つのデータベースのすべてのデータベースファイルを関連付けるために使用します。 データベースが適切に起動するには、すべてのファイルのヘッダー ページにこの GUID が定義されている必要があります。 この GUID を持つデータベースは1つだけですが、データベースをコピーしてアタッチすることによって重複を作成できます。 RESTORE では、まだ存在しないデータベースを復元するときに常に新しい GUID が生成されます。<br /><br /> NULL = データベースがオフラインであるか、データベースが開始されません。|  
|**family_guid**|**UNIQUEIDENTIFIER**|一致する復元状態を検出するためのデータベースの "バックアップファミリ" の識別子。<br /><br /> NULL = データベースがオフラインであるか、データベースが開始されません。|  
|**last_log_backup_lsn**|**数値 (25, 0)**|次のログバックアップの開始ログシーケンス番号。<br /><br /> NULL の場合、データベースが単純復旧であるか、または現在のデータベースバックアップが存在しないため、トランザクションログのバックアップを実行できません。|  
|**recovery_fork_guid**|**UNIQUEIDENTIFIER**|データベースが現在アクティブになっている現在の復旧分岐を識別します。<br /><br /> NULL = データベースがオフラインであるか、データベースが開始されません。|  
|**first_recovery_fork_guid**|**UNIQUEIDENTIFIER**|開始復旧分岐の識別子。<br /><br /> NULL = データベースがオフラインであるか、データベースが開始されません。|  
|**fork_point_lsn**|**数値 (25, 0)**|**First_recovery_fork_guid**が等しくない (! =) **recovery_fork_guid**の場合、 **fork_point_lsn**は現在の分岐ポイントのログシーケンス番号です。 それ以外の場合は NULL になります。|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)]詳細については、「[メタデータ表示の構成](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [データベースとファイルのカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql.md)   
 [RESTORE HEADERONLY &#40;Transact-sql&#41;](../../t-sql/statements/restore-statements-headeronly-transact-sql.md)   
 [SQL Server システム カタログに対するクエリに関してよく寄せられる質問](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
