---
title: CreateRecordset メソッド (RDS) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- DataControl::CreateRecordset
- RDS.DataControl::CreateRecordset
- CreateRecordset
- RDSServer.DataFactory::CreateRecordset
- DataFactory::CreateRecordset
helpviewer_keywords:
- CreateRecordset method [RDS]
ms.assetid: 6840b1e5-c04d-4d3e-9dcc-42128c83492f
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 3c65f7d415864b169b683e0c9ab858506d31783b
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67964512"
---
# <a name="createrecordset-method-rds"></a>CreateRecordset メソッド (RDS)
空の非接続[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)を作成します。  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および[Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416)」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.CreateRecordset(ColumnInfos)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Object*  
 [RDSServer DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)または RDS を表すオブジェクト変数です[。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)オブジェクト。  
  
 *コラムの info*  
 作成された**レコードセット**内の各列を定義する属性の**Variant**配列。 各列定義には、4つの必須属性と1つの省略可能な属性の配列が含まれています。  
  
|Attribute|[説明]|  
|---------------|-----------------|  
|Name|列ヘッダーの名前。|  
|種類|データ型の整数。|  
|Size|データ型に関係なく、文字単位の幅の整数。|  
|NULL 値の許容|ブール値。|  
|Scale (省略可能)|この省略可能な属性は、数値フィールドの小数点以下桁数を定義します。 この値が指定されていない場合、数値は3桁に切り捨てられます。 有効桁数は影響を受けませんが、小数点の後の桁数は3桁に切り捨てられます。|  
  
 次に、一連の列配列が配列にグループ化されて、**レコードセット**が定義されます。  
  
## <a name="remarks"></a>解説  
 サーバー側ビジネスオブジェクトは、結果の**レコードセット**に、株価を含むオペレーティングシステムファイルなど、OLE DB 以外のデータプロバイダーからのデータを設定できます。  
  
 次の表に、 **CreateRecordset**メソッドでサポートされる[DataTypeEnum](../../../ado/reference/ado-api/datatypeenum.md)の値を示します。 表示される数値は、フィールドを定義するために使用される参照番号です。  
  
 各データ型の長さは固定長または可変長です。 サイズが事前に定義されていて、サイズ定義が必要であるため、固定長型は-1 のサイズで定義する必要があります。 可変長データ型では、1 ~ 32767 のサイズを使用できます。  
  
 変数のデータ型によっては、代入列に示されている型に型を強制的に変換することができます。 **レコードセット**が作成され、いっぱいになるまで、置換は表示されません。 その後、必要に応じて、実際のデータ型を確認できます。  
  
|Length|常時|番号|代替|  
|------------|--------------|------------|------------------|  
|固定|**adTinyInt**|16||  
|固定|**adSmallInt**|2||  
|固定|**adInteger**|3||  
|固定|**adBigInt**|20||  
|固定|**adUnsignedTinyInt**|17||  
|固定|**adUnsignedSmallInt**|18||  
|固定|**adUnsignedInt**|19||  
|固定|**adUnsignedBigInt**|21||  
|固定|**adSingle**|4||  
|固定|**追加**|5||  
|固定|**adCurrency**|6||  
|固定|**adDecimal**|14||  
|固定|**adNumeric**|131||  
|固定|**adBoolean**|11||  
|固定|**adError**|10||  
|固定|**adGuid**|72||  
|固定|**adDate**|7||  
|固定|**adDBDate**|133||  
|固定|**adDBTime**|134||  
|固定|**adDBTimestamp**|135|7|  
|変数|**adBSTR**|8|130|  
|変数|**adChar**|129|200|  
|変数|**adVarChar**|200||  
|変数|**adLongVarChar**|201|200|  
|変数|**adWChar**|130||  
|変数|**adVarWChar**|202|130|  
|変数|**adLongVarWChar**|203|130|  
|変数|**adBinary**|128||  
|変数|**adVarBinary**|204||  
|変数|**adLongVarBinary**|205|204|  
  
## <a name="applies-to"></a>適用対象  
  
|||  
|-|-|  
|[DataControl オブジェクト (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)|[DataFactory オブジェクト (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)|  
  
## <a name="see-also"></a>参照  
 [CreateRecordset メソッドの例 (VB)](../../../ado/reference/ado-api/createrecordset-method-example-vb.md)   
 [CreateRecordset メソッドの例 (VBScript)](../../../ado/reference/rds-api/createrecordset-method-example-vbscript.md)   
 [CreateObject メソッド (RDS)](../../../ado/reference/rds-api/createobject-method-rds.md)



