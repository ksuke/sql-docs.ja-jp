---
title: MSreplmonthresholdmetrics (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- msreplmonthresholdmetrics_TSQL
- msreplmonthresholdmetrics
dev_langs:
- TSQL
helpviewer_keywords:
- MSreplmonthresholdmetrics system table
ms.assetid: 0cc9b40a-36ce-485b-9bc2-d4abd5aa6727
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3e8b9c2443a6fa74e113dc1a3f25880ac753dc0
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68079941"
---
# <a name="msreplmonthresholdmetrics-transact-sql"></a>MSreplmonthresholdmetrics (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSreplmonthresholdmetrics**テーブルは、レプリケーションを監視するために提供されるメトリックを定義します。 このテーブルは、 **msdb**データベースに格納されます。  
  
|列名|データ型|[説明]|  
|-----------------|---------------|-----------------|  
|**metric_id**|**int**|レプリケーションパフォーマンスメトリックを識別します。次のいずれかの値を指定できます。<br /><br /> **1** = 有効期限<br /><br /> **2** = 待機時間<br /><br /> **4** = mergeexpiration 期限<br /><br /> **5** = mergeslowrunduration<br /><br /> **6** = mergefastrunduration<br /><br /> **7** = mergefastrunspeed<br /><br /> **8** = mergeslowrunspeed|  
|**題**|**sysname**|レプリケーション パフォーマンス基準の名前。|  
|**warningbitstatus**|**int**|次のいずれかの基準に対応するしきい値違反の警告を示す、ビットごとの識別子です。<br /><br /> **1** = 有効期限-トランザクションパブリケーションへのサブスクリプションが、保有期間の割合として、許容されるしきい値を超える保有期間を超えました。<br /><br /> **2** = 待機時間-トランザクションパブリッシャーからサブスクライバーへのデータのレプリケートにかかった時間が、秒単位のしきい値を超えています。<br /><br /> **4** = mergeexpiration-マージパブリケーションに対するサブスクリプションが、保有期間の割合として許容されるしきい値を超える保有期間を超えました。<br /><br /> **8** = mergefastrunduration-高速ネットワーク接続経由で、マージサブスクリプションの同期の完了にかかった時間が、秒単位のしきい値を超えています。<br /><br /> **16** = mergeslowrunduration-低速またはダイヤルアップネットワーク接続を介して、マージサブスクリプションの同期の完了にかかった時間が、秒単位のしきい値を超えています。<br /><br /> **32** = mergefastrunspeed-高速ネットワーク接続上で、マージサブスクリプションの同期中の行の配信率が、1秒あたりの行数でのしきい値の比率を維持できませんでした。<br /><br /> **64** = mergeslowrunspeed-低速またはダイヤルアップネットワーク接続を介して、マージサブスクリプションの同期中の行の配信率が、1秒あたりの行数でしきい値を維持できませんでした。|  
|**alertmessageid**|**int**|しきい値の警告が発生した場合に表示されるエラー メッセージの ID。|  
|**記述**|**nvarchar (3000)**|レプリケーションパフォーマンス基準の説明|  
|**default_value**|**sql_variant**|レプリケーション パフォーマンス基準の既定値。|  
|**min_value**|**sql_variant**|範囲指定されたレプリケーションパフォーマンスメトリックの最小値。|  
|**max_value**|**sql_variant**|範囲指定されたレプリケーションパフォーマンスメトリックの最大値です。|  
  
## <a name="see-also"></a>参照  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーションビュー &#40;Transact-sql&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
