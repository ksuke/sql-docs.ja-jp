---
title: ADORecordConstruction Interface |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADORecordConstruction
helpviewer_keywords:
- ADORecordConstruction interface [ADO]
ms.assetid: 52a5429e-5829-455e-be3b-31f05cbecf2d
author: MightyPen
ms.author: genemi
ms.openlocfilehash: c56ba0b9d7ebebbf4a9e4baf669bbdc6eb84355e
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67920809"
---
# <a name="adorecordconstruction-interface"></a>ADORecordConstruction インターフェイス
**ADORecordConstruction**インターフェイスは、C/c + + アプリケーションの OLE DB **ROW**オブジェクトから ADO**レコード**オブジェクトを構築するために使用されます。  
  
 このインターフェイスは、次のプロパティをサポートしています。  
  
## <a name="properties"></a>Properties  
  
|||  
|-|-|  
|[ParentRow](../../../ado/reference/ado-api/parentrow-property-ado.md)|書き込み専用です。<br />この ADO **Record**オブジェクトの OLE DB **Row**オブジェクトのコンテナーを設定します。|  
|[行](../../../ado/reference/ado-api/row-property-ado.md)|読み取り/書き込み。<br />この ADO **Record**オブジェクトから OLE DB **Row**オブジェクトを取得/設定します。|  
  
## <a name="methods"></a>メソッド  
 [なし] :  
  
## <a name="events"></a>events  
 [なし] :  
  
## <a name="remarks"></a>解説  
 OLE DB **Row**オブジェクト (`pRow`) を指定した場合、ADO**レコード**オブジェクト (`adoR`) の構造は、次の3つの基本的な操作になります。  
  
1.  ADO**レコード**オブジェクトを作成します。  
  
    ```  
    _RecordPtr adoR;  
    adoRs.CreateInstance(__uuidof(_Record));  
    ```  
  
2.  **レコード**オブジェクトの**IADORecordConstruction**インターフェイスに対してクエリを実行します。  
  
    ```  
    adoRecordConstructionPtr adoRConstruct=NULL;  
    adoR->QueryInterface(__uuidof(ADORecordConstruction),  
                        (void**)&adoRConstruct);  
    ```  
  
3.  **IADORecordConstruction::p ut_Row** property メソッドを呼び出して、ADO **Record**オブジェクトの OLE DB **Row**オブジェクトを設定します。  
  
    ```  
    IUnknown *pUnk=NULL;  
    pRow->QueryInterface(IID_IUnknown, (void**)&pUnk);  
    adoRConstruct->put_Row(pUnk);  
    ```  
  
 結果の**adoR**オブジェクトは、OLE DB **Row**オブジェクトから構築された ADO**レコード**オブジェクトを表します。  
  
 ADO**レコード**オブジェクトは、OLE DB **Row**オブジェクトのコンテナーから構築することもできます。  
  
## <a name="requirements"></a>必要条件  
 **バージョン:** ADO 2.0 以降  
  
 **ライブラリ:** msado15.dll  
  
 **UUID:** 00000567-0000-0010-8000-00AA006D2EA4
