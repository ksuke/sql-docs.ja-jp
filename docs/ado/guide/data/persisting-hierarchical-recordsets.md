---
title: 階層レコードセットの保持 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchical Recordsets [ADO], persisting
- persisting hierarchical Recordsets [ADO]
- data shaping [ADO], hierarchical Recordsets
ms.assetid: 43798bb5-98a6-4ad6-9bf8-78154b3a1827
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 34649bba37f922e7597bf09870e3e9d3bcf522dc
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67924624"
---
# <a name="persisting-hierarchical-recordsets"></a>階層レコードセットの保持
ADTG 形式または XML 形式のファイルに階層**レコードセット**を保存するには、 [save](../../../ado/reference/ado-api/save-method.md)メソッドを呼び出します。 ただし、階層**レコード**セットを xml 形式で保存する場合は、2つの制限があります。階層**レコードセット**に保留中の更新が含まれている場合は xml で保存できません。また、パラメーター化された階層**レコードセット**を保存することもできません。  
  
 データシェイププロバイダーの詳細については、「 [Microsoft data](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) OLE DB for OLE DB (ADO)」および「[データシェイプサービスの概要](https://msdn.microsoft.com/9f51e471-8e85-448e-9fb8-b64bbf767bf3)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [データシェイプの例](../../../ado/guide/data/data-shaping-example.md)   
 [仮形の文法](../../../ado/guide/data/formal-shape-grammar.md)   
 [一般的な Shape コマンド](../../../ado/guide/data/shape-commands-in-general.md)
