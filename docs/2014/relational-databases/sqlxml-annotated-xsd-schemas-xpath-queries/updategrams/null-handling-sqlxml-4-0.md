---
title: NULL 処理 (SQLXML 4.0) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 11f7ca96ca65ae23202b84030140e0eaef945de2
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66014684"
---
# <a name="null-handling-sqlxml-40"></a>NULL の取り扱い (SQLXML 4.0)
  XML 構文では、NULL は "存在しない" ことを表します。 (たとえば、属性または要素の値が NULL の場合、その属性または要素は XML ドキュメントに存在しません)。SQLXML [!INCLUDE[msCoName](../../../includes/msconame-md.md)]では、 `updg:nullvalue`属性を使用して、要素または属性値に NULL を指定できます。  
  
 たとえば、次のアップデートグラムでは、 **ContactID**が64である連絡先の**TITLE**値が NULL であることを確認し、 **title**値を "Mr" に更新します。 をお問い合わせください。  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 パラメーターをアップデートグラムに渡すときには、パラメーター値として NULL を指定できます。 これを行うには、`nullvalue` ブロックに `<updg:header>` 属性を指定します。 例については、「[アップデートグラムへのパラメーターの引き渡し &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [SQLXML 4.0&#41;&#40;アップデートグラムのセキュリティに関する考慮事項](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
