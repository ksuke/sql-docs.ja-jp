---
title: リレーションシップ ステージング テーブル (マスター データ サービス) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- relationships staging table [Master Data Services]
- database [Master Data Services], relationships table
ms.assetid: e19b6002-67bd-4e7d-9f19-ecb455522b1a
author: lrtoyou1223
ms.author: lle
manager: craigg
ms.openlocfilehash: 3b5cc194306a4baecb2c5fa5478bf4733d1386af
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67284978"
---
# <a name="relationship-staging-table-master-data-services"></a>リレーションシップ ステージング テーブル (マスター データ サービス)
  
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] データベースのリレーションシップ ステージング テーブル (stg.name_Relationship) を使用して、メンバーが相互に保持するリレーションシップに基づいて、明示的階層におけるメンバーの位置を変更します。  
  
##  <a name="TableColumns"></a>テーブルの列  
 次の表は、リレーションシップ ステージング テーブルの各フィールドの用途を説明しています。  
  
|列名|[説明]|  
|-----------------|-----------------|  
|**id**|自動的に割り当てられる ID。 このフィールドには値を入力しないでください。 バッチが未処理の場合、このフィールドは空白です。|  
|**RelationshipType**<br /><br /> 必須|設定しているリレーションシップの種類。 設定可能な値は、次のとおりです。<br /><br /> **1**:P arent<br /><br /> **2**: 兄弟 (同じレベル)|  
|**ImportStatus_ID**<br /><br /> 必須|インポート処理の状態。 設定可能な値は、次のとおりです。<br /><br /> **0**: レコードがステージングの準備ができていることを示すために指定します。<br /><br /> **1**は、自動的に割り当てられ、レコードのステージング処理が成功したことを示します。<br /><br /> **2**。自動的に割り当てられ、レコードのステージング処理が失敗したことを示します。|  
|**Batch_ID**<br /><br /> Web サービスでのみ必須|ステージング用のレコードをグループ化する、自動的に割り当てられる識別子。 バッチ内のメンバーすべてにこの識別子が割り当てられます。これは、 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ユーザー インターフェイスの **[ID]** 列に表示されます。<br /><br /> バッチが未処理の場合、このフィールドは空白です。|  
|**BatchTag**<br /><br /> Web サービス以外は必須|バッチの一意名 (最大 50 文字)。|  
|**HierarchyName**<br /><br /> 必須|明示的階層の名前。 各統合メンバーは、1 つの階層にのみ所属することができます。|  
|**ParentCode**<br /><br /> 必須|親子リレーションシップの場合、子リーフまたは統合メンバーの親になる統合メンバーのコード。<br /><br /> 兄弟リレーションシップの場合、兄弟のいずれかのコード。|  
|**ChildCode**<br /><br /> 必須|親子リレーションシップの場合、子になる統合メンバーまたはリーフ メンバーのコード。<br /><br /> 兄弟リレーションシップの場合、兄弟のいずれかのコード。|  
|**並べ替え順序**<br /><br /> 省略可能|親の下にある他のメンバーに対するメンバーの順序を示す整数。 各子メンバーは一意識別子を保持します。|  
|**ErrorCode**|エラー コードを表示します。 
  **ImportStatus_ID** が **2** のすべてのレコードについては、「[ステージング処理のエラー (マスター データ サービス)](staging-process-errors-master-data-services.md)」を参照してください。|  
  
## <a name="see-also"></a>参照  
 [ステージングプロセス &#40;マスターデータサービスを使用して明示的階層メンバーを移動する&#41;](add-update-and-delete-data-master-data-services.md)   
 [データのインポート &#40;マスターデータサービス&#41;](overview-importing-data-from-tables-master-data-services.md)   
 [ステージング処理中に発生したエラーを表示 &#40;マスターデータサービス&#41;](view-errors-that-occur-during-staging-master-data-services.md)   
 [ステージング処理のエラー &#40;マスターデータサービス&#41;](staging-process-errors-master-data-services.md)  
  
  
