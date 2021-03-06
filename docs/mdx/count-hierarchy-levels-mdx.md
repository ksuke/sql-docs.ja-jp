---
title: Count (階層レベル) (MDX) |Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 17fe804de8bf2c20581ca5c00bee3a28dbce4d55
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68045207"
---
# <a name="count-hierarchy-levels-mdx"></a>Count (階層レベル) (MDX)


  階層内のレベル数を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Hierarchy_Expression.Levels.Count  
```  
  
## <a name="arguments"></a>引数  
 *Hierarchy_Expression*  
 階層を返す有効な多次元式 (MDX) 式です。  
  
## <a name="remarks"></a>解説  
 階層内のレベル数を返します。`[All]` レベルがある場合はこれも含みます。  
  
> [!IMPORTANT]  
>  表示可能な階層がディメンション内に 1 つしかない場合は、ディメンション名がその 1 つしかない階層に解決されるため、その階層はディメンション名でも階層名でも参照できます。 たとえば、は`Measures.Levels.Count` 、Measures ディメンション内の唯一の階層に解決されるため、有効な MDX 式です。  
  
## <a name="example"></a>例  
 次の例では、Adventure Works キューブの Product Categories ユーザー定義階層に含まれるレベルの数を返します。  
  
```  
WITH MEMBER measures.X AS  
   [Product].[Product Categories].Levels.Count   
Select Measures.X ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>参照  
 [&#40;ディメンション&#41; &#40;MDX&#41;のカウント](../mdx/count-dimension-mdx.md)   
 [MDX&#41;&#41; &#40;組 &#40;数](../mdx/count-tuple-mdx.md)   
 [MDX&#41;&#41; &#40;設定 &#40;数](../mdx/count-set-mdx.md)   
 [Mdx 関数リファレンス &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
