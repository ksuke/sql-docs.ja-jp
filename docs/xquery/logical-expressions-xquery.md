---
title: 論理式 (XQuery) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- logical operators [SQL Server], XQuery
- effective Boolean value [XQuery]
- logical expressions [XQuery]
- EBV
- expressions [XQuery], logical
ms.assetid: de94cd2e-2d48-49fb-9ebd-a2d90c79bf62
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b1dc7b961dd0b85824ea180cbc4815d5488a360
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68004505"
---
# <a name="logical-expressions-xquery"></a>論理式 (XQuery)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  XQuery**では、論理**演算子**と演算子が**サポートされています。  
  
```  
expression1 and expression2  
expression1 or expression2  
```  
  
 の`expression1,``expression2` [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]テスト式では、空のシーケンス、1つまたは複数のノードのシーケンス、または単一のブール値が生成されます。 結果に基づいて、次の方法で有効なブール値が決まります。  
  
-   テスト式の結果が空のシーケンスになった場合、式の結果は False になります。  
  
-   テスト式の結果が 1 つのブール値になった場合、この値が式の結果になります。  
  
-   テスト式の結果が 1 つ以上のノードのシーケンスになった場合、式の結果は True になります。  
  
-   それ以外の場合は、静的なエラーが発生します。  
  
 その後、論理**and**および**or**演算子は、標準の論理セマンティクスを使用して、式の結果のブール値に適用されます。  
  
 次のクエリでは、製品カタログから、特定の製品モデルのフロント角度`Picture`の小さい画像 (<> 要素) を取得します。 製品の説明ドキュメントごとに、サイズや角度など、異なる属性を持つ 1 つ以上の製品写真をカタログに格納できることに注意してください。  
  
```  
SELECT CatalogDescription.query('  
     declare namespace PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     for $F in /PD:ProductDescription/PD:Picture[PD:Size="small"   
                                                 and PD:Angle="front"]  
     return   
         $F   
    ') as Result  
FROM  Production.ProductModel  
where ProductModelID=19  
```  
  
 結果を次に示します。  
  
```  
<PD:Picture   
  xmlns:PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
  <PD:Angle>front</PD:Angle>  
  <PD:Size>small</PD:Size>  
  <PD:ProductPhotoID>31</PD:ProductPhotoID>  
</PD:Picture>  
  
```  
  
## <a name="see-also"></a>参照  
 [XQuery 式](../xquery/xquery-expressions.md)  
  
  
