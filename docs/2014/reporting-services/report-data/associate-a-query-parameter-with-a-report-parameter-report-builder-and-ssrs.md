---
title: クエリ パラメーターのレポート パラメーターへの関連付け (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 697a8bbfa77a8afcabfdf00deef93620ff607233
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66107468"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a>クエリ パラメーターのレポート パラメーターへの関連付け (レポート ビルダーおよび SSRS)
  クエリ変数を含んだデータセット クエリを定義すると、クエリ コマンドが解析されます。 クエリ変数ごとに、対応するデータセット クエリ パラメーターおよびレポート パラメーターが作成されます。 データセット パラメーターは、レポート パラメーターを参照します。 これにより、クエリに直接渡される値を入力できます。 クエリ コマンドを編集するたびに、同じ処理が実行されます。  
  
 クエリ パラメーターにバインドされているレポート パラメーターの名前を変更した場合、このトピックの手順で、名前を変更したレポート パラメーターにクエリ パラメーターを手動でリンクする必要があります。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a>クエリ パラメーターをレポート パラメーターに関連付けるには  
  
1.  レポート データ ペインでデータセットを右クリックし、 **[データセットのプロパティ]** をクリックして、 **[パラメーター]** をクリックします。  
  
    > [!NOTE]  
    >  レポート データ ペインが表示されていない場合は、 **[表示]** メニューの **[レポート データ]** をクリックします。  
  
2.  
  **[パラメーター名]** 列で、クエリ パラメーターの名前を探します。 パラメーター名は、クエリに基づいて自動的に設定されます。 クエリを変更するたびに、新しいクエリ パラメーターがチェックされます。 手動で作成したクエリ パラメーターは、クエリが変更されても変更されません。  
  
    -   
  **[パラメーター名]** で、クエリ内に表示された名前と同じクエリ パラメーターを探します。 新しいクエリ パラメーターを手動で追加して、名前を入力することもできます。  
  
    -   
  **[パラメーター値]** では、クエリ パラメーターに渡す値に評価される式を入力または選択します。 これは通常、レポート パラメーターの名前です。  
  
        > [!NOTE]  
        >  クエリ パラメーターの値には、レポート パラメーター以外も指定できます。 このパラメーター値に対応する値に評価される式を使用できます。  
  
3.  クエリ パラメーターを追加する場合は、手順 2. を繰り返します。  
  
## <a name="see-also"></a>参照  
 [レポート埋め込みデータセットと共有データセット &#40;レポート ビルダーおよび SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [レポートパラメーターの概念 &#40;レポートビルダーと SSRS&#41;](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
