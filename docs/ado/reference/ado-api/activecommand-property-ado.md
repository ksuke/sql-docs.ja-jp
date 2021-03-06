---
title: ActiveCommand プロパティ (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset20::ActiveCommand
helpviewer_keywords:
- ActiveCommand property [ADO]
ms.assetid: fb4088d5-5968-42d6-aeaa-3955046bb4da
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d2a2f23360cf3ce032d14af7ca475d5c2c3ea638
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67921674"
---
# <a name="activecommand-property-ado"></a>ActiveCommand プロパティ (ADO)
関連付けられた[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)オブジェクトを作成した[Command](../../../ado/reference/ado-api/command-object-ado.md)オブジェクトを示します。  
  
## <a name="return-value"></a>戻り値  
 **Command**オブジェクトを含む**Variant**を返します。 既定値は null オブジェクト参照です。  
  
## <a name="remarks"></a>解説  
 **Activecommand**プロパティは読み取り専用です。  
  
 **Command**オブジェクトを使用して現在の**レコードセット**を作成しなかった場合は、 **Null**オブジェクト参照が返されます。  
  
 このプロパティを使用して、結果の**レコードセット**オブジェクトだけを指定した場合に、関連付けられている**Command**オブジェクトを検索します。  
  
## <a name="applies-to"></a>適用対象  
 [Recordset オブジェクト (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>参照  
 [ActiveCommand プロパティの例 (VB)](../../../ado/reference/ado-api/activecommand-property-example-vb.md)   
 [ActiveCommand プロパティの例 (JScript)](../../../ado/reference/ado-api/activecommand-property-example-jscript.md)   
 [ActiveCommand プロパティの例 (VC + +)](../../../ado/reference/ado-api/activecommand-property-example-vc.md)   
 [Command オブジェクト (ADO)](../../../ado/reference/ado-api/command-object-ado.md)
