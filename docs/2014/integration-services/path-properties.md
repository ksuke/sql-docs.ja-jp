---
title: パスのプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: fc13943df93acf2227b089b177cdca6c86ee1831
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66056663"
---
# <a name="path-properties"></a>パスのプロパティ
  オブジェクトモデルのデータフローオブジェクト[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]には、コンポーネント、入力、出力、入力列、および出力列のレベルで共通のプロパティとカスタムプロパティがあります。 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] 多くのプロパティの値は読み取り専用で、実行時にデータ フロー エンジンによって割り当てられます。  
  
 このトピックでは、データ フロー オブジェクトを連結するパスのカスタム プロパティの一覧を示し、それらのプロパティについて説明します。  
  
## <a name="path-properties"></a>パスのプロパティ  
 
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] オブジェクト モデルでは、データ フロー内のコンポーネントを連結するパスは <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> インターフェイスを実装します。  
  
 次の表は、データ フロー内のパスの、値が設定できるプロパティを示しています。 データ フロー エンジンは、この一覧にない追加の読み取り専用プロパティにも値を割り当てます。  
  
|プロパティ名|データ型|[説明]|  
|-------------------|---------------|-----------------|  
|[PathAnnotation]|Integer (列挙)|注釈をパスと共にデザイナー画面に表示するかどうかを示す値。 値には、`AsNeeded`、`SourceName`、`PathName`、および `Never` があります。 既定値は `AsNeeded` です。|  
|[DestinationName]|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|パスに関連付けられた入力|  
|SourceName|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|パスに関連付けられた出力|  
  
## <a name="see-also"></a>参照  
 [Integration Services パス](data-flow/integration-services-paths.md)   
 [共通プロパティ](../../2014/integration-services/common-properties.md)   
 [変換のカスタムプロパティ](data-flow/transformations/transformation-custom-properties.md)   
 [式を使って設定できるデータ フロー プロパティ](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
