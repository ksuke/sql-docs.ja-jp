---
title: モデルを削除する
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting models [Master Data Services]
- models [Master Data Services], deleting models
ms.assetid: f0ad3cc4-aed7-47c8-94bc-2971fe9fe871
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 65164c1732aefe6555aa19325a158793d07631a6
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "73728358"
---
# <a name="delete-a-model-master-data-services"></a>モデルを削除する (マスター データ サービス)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  モデルを削除して、モデルおよびそのすべてのデータを [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]から削除します。  
  
> [!NOTE]  
>  これらの手順が完了すると、モデルのすべてのバージョンのすべてのオブジェクトおよびすべてのデータが完全に削除されます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには  
  
-   [**システム管理**] 機能領域にアクセスするためのアクセス許可が必要です。  
  
-   モデル管理者である必要があります。 詳細については、「 [管理者 (マスター データ サービス)](../master-data-services/administrators-master-data-services.md)にアクセスすることなくグループに対してユーザーの追加または削除を行うことができます。  
  
### <a name="to-delete-a-model"></a>モデルを削除するには  
  
1.  
  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]で **[システム管理]** をクリックします。  
  
2.  
  **[モデル ビュー]** ページのメニュー バーから **[管理]** をポイントして **[モデル]** をクリックします。  
  
3.  
  **[モデルの管理]** ページで、グリッドから削除するモデルの行を選択します。  
  
4.  
  **[削除]** をクリックします。  
  
5.  確認のダイアログ ボックスで **[OK]** をクリックします。  
  
6.  追加の確認のダイアログ ボックスで **[OK]** をクリックします。  
  
 グリッドの **[状態]** 列には、モデルに対する操作の状態が示されます。 [**モデルの保存**] ボタンをクリックすると、![更新](../master-data-services/media/mds-model-status-updating.png "更新中")中のイメージが表示されます。これは、モデルが更新中であることを示します。 モデルの作成時または編集時にエラーが発生した場合は、![エラー](../master-data-services/media/mds-model-status-error.png "エラー")イメージが表示されます。 それ以外の場合、状態は [OK] になり、 ![[Ok]](../master-data-services/media/mds-model-status-ok.png "OK")のイメージが表示されます。  
  
## <a name="see-also"></a>参照  
 [モデル &#40;マスターデータサービス&#41;](../master-data-services/models-master-data-services.md)   
 [モデル &#40;マスターデータサービスを作成し&#41;](../master-data-services/create-a-model-master-data-services.md)  
  
  
