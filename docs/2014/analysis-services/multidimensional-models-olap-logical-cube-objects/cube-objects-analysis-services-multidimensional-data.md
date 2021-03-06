---
title: Cube オブジェクト (Analysis Services-多次元データ) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: fc9b813f5310acad9d6dfa2b844adae6168fc1f9
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62702641"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a>Cube オブジェクト (Analysis Services - 多次元データ)
    
## <a name="introducing-cube-objects"></a>Cube オブジェクトの導入  
 簡単な <xref:Microsoft.AnalysisServices.Cube> オブジェクトは、基本情報、ディメンション、およびメジャー グループで構成されます。 基本情報には、キューブの名前、キューブの既定のメジャー、データ ソース、ストレージ モードなどが含まれます。  
  
 Dimensions コレクションには、データベースのディメンション コレクションのキューブで使用される、実際のディメンションのセットが含まれています。 すべてのディメンションは、キューブ内で参照される前に、データベースのディメンション コレクション内で定義されている必要があります。 プライベートディメンションは、で[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]は使用できません。  
  
 メジャー グループは、キューブ内のメジャーのセットです。 メジャー グループは、共通のデータ ソース ビューと共通のディメンション セットを持つ、メジャーのコレクションです。 メジャー グループは、メジャーの処理単位です。メジャー グループは個別に処理されてから参照できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|||  
|-|-|  
|トピック||  
|[アクション &#40;Analysis Services-多次元データ&#41;](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[集計と集計デザイン](aggregations-and-aggregation-designs.md)||  
|[[新しい名前付きセット]](calculations.md)||  
|[キューブセル &#40;Analysis Services-多次元データ&#41;](cube-cells-analysis-services-multidimensional-data.md)||  
|[キューブ プロパティ](cube-properties-multidimensional-model-programming.md)||  
|[Cube Storage &#40;Analysis Services-多次元データ&#41;](cube-storage-analysis-services-multidimensional-data.md)||  
|[キューブの翻訳](cube-translations.md)||  
|[ディメンション リレーションシップ](dimension-relationships.md)||  
|[多次元モデルの Kpi&#41; &#40;主要業績評価指標](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[メジャーおよびメジャー グループ](../multidimensional-models/measures-and-measure-groups.md)||  
|[パーティション &#40;Analysis Services-多次元データ&#41;](partitions-analysis-services-multidimensional-data.md)||  
|[パースペクティブ](perspectives.md)||  
  
  
