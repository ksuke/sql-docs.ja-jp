---
title: Code 以外の属性の値の自動生成 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
manager: craigg
ms.openlocfilehash: fb58fdf9666abcb01c19da65dbc6c31622343657
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "65480051"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a>Code 以外の属性の値の自動生成 (Master Data Services)
  
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] では、ビジネス ルールが適用されるたびにエンティティの属性値に整数を自動的に割り当てる場合は、属性の値を自動的に生成します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには  
  
-   [**システム管理**] 機能領域にアクセスするためのアクセス許可が必要です。  
  
-   モデル管理者である必要があります。 詳細については、「 [管理者 (マスター データ サービス)](administrators-master-data-services.md)にアクセスすることなくグループに対してユーザーの追加または削除を行うことができます。  
  
-   数値属性が存在する必要があります。 詳細については、「[数値属性を作成する (マスター データ サービス)](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md)」を参照してください。  
  
### <a name="to-automatically-generate-an-attribute-value"></a>属性値を自動的に生成するには  
  
1.  
  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]で **[システム管理]** をクリックします。  
  
2.  メニュー バーから **[管理]** をポイントして **[ビジネス ルール]** をクリックします。  
  
3.  
  **[ビジネス ルールのメンテナンス]** ページの **[モデル]** の一覧からモデルを選択します。  
  
4.  
  **[エンティティ]** の一覧からエンティティを選択します。  
  
5.  
  **[メンバーの種類]** の一覧から、適用するビジネス ルールのメンバーの種類を選択します。  
  
6.  
  **[属性]** ボックスの一覧は、 **[すべて]** の既定値のままにします。  
  
7.  
  **[ビジネス ルールの追加]** をクリックします。  
  
8.  
  **[選択したビジネス ルールの編集]** をクリックします。  
  
9. 
  **[コンポーネント]** ペインで **[アクション]** ノードを展開します。  
  
10. 既定値ノードで、**[の既定値が生成値である]** をクリックし、**[THEN]** ペインの **[アクション]** ラベルにドラッグします。  
  
11. 
  **[属性]** ペインで値を生成する属性をクリックして、 **[アクションの編集]** ペインの **[属性の選択]** ラベルにドラッグします。  
  
12. 
  **[開始]** および **[増分]** ボックスに値を入力します。 メンバーが既に存在する場合、値は既存の最も大きい値に基づいて設定されます。 たとえば、既存の最も大きい値が 299 で、**[増分]** を **1**に設定してある場合、次のメンバーの値は 300 に設定されます。  
  
13. 
  **[アクションの編集]** ペインの **[アイテムの保存]** をクリックします。  
  
14. 
  **[戻る]** をクリックします。  
  
15. 必要に応じて、 **[ビジネス ルールのメンテナンス]** ページで、ビジネス ルールを含む行の **[名前]**、 **[説明]**、または **[通知]** 列のセルをダブルクリックして値を更新します。  
  
16. 
  **[ビジネス ルールのパブリッシュ]** をクリックします。  
  
17. 確認のダイアログ ボックスで **[OK]** をクリックします。 ルールの状態が **[アクティブ]** に変わります。  
  
## <a name="next-steps"></a>次の手順  
  
-   [ビジネスルールに対して特定のメンバーを検証 &#40;マスターデータサービス&#41;](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [ビジネスルールに対してバージョンを検証する &#40;マスターデータサービス&#41;](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a>参照  
 [自動コード作成 &#40;マスターデータサービス&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md)   
 [ビジネスルール &#40;マスターデータサービス&#41;](../../2014/master-data-services/business-rules-master-data-services.md)   
 [検証 &#40;マスターデータサービス&#41;](../../2014/master-data-services/validation-master-data-services.md)  
  
  
