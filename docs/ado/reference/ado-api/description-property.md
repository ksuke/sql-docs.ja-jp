---
title: Description プロパティ |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Error::Description
- Error::GetDescription
- Error::get_Description
helpviewer_keywords:
- Description property
ms.assetid: 4b5d6790-6c29-42aa-bf78-d9cfb8ad7965
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 48b3a6987e6c7b6c3754f5041d90d248520345ab
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67933087"
---
# <a name="description-property"></a>Description プロパティ
[エラー](../../../ado/reference/ado-api/error-object.md)オブジェクトについて説明します。  
  
## <a name="return-value"></a>戻り値  
 エラーの説明を含む**文字列**値を返します。  
  
## <a name="remarks"></a>解説  
 **Description**プロパティを使用して、エラーの簡単な説明を取得します。 このプロパティを表示して、処理できない、または処理したくないエラーをユーザーに通知します。 文字列は、ADO またはプロバイダーから取得されます。  
  
 プロバイダーは、ADO に特定のエラーテキストを渡す役割を担います。 ADO は、受信したプロバイダーエラーまたは警告ごとに[エラー](../../../ado/reference/ado-api/error-object.md)オブジェクトを**エラーコレクションに**追加します。 **エラー**コレクションを列挙して、プロバイダーが成功したエラーをトレースします。  
  
## <a name="applies-to"></a>適用対象  
 [Error オブジェクト](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>参照  
 [Description、HelpContext、HelpFile、のエラー、Number、Source、および SQLState プロパティの例 (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Description、HelpContext、HelpFile、のエラー、Number、Source、および SQLState プロパティの例 (VC + +)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [HelpContext、HelpFile プロパティ](../../../ado/reference/ado-api/helpcontext-helpfile-properties.md)   
 [Number プロパティ (ADO)](../../../ado/reference/ado-api/number-property-ado.md)   
 [Source プロパティ (ADO Error)](../../../ado/reference/ado-api/source-property-ado-error.md)
