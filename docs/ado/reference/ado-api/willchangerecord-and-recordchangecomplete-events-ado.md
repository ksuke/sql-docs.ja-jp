---
title: Changerecord イベントと RecordChangeComplete イベント (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- RecordChangeComplete
- Recordset::WillChangeRecord
- WillChangeRecord
- Recordset::RecordChangeComplete
helpviewer_keywords:
- WillChangeRecord event [ADO]
- recordchangecomplete event [ADO]
ms.assetid: cbc369fd-63af-4a7d-96ae-efa91b78ca69
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 6e632db34fbbacbee61cd943067052af27a8cfe8
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67938672"
---
# <a name="willchangerecord-and-recordchangecomplete-events-ado"></a>WillChangeRecord および RecordChangeComplete イベント (ADO)
この**イベントは、** [レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)の1つ以上のレコード (行) が変更される前に呼び出されます。 **RecordChangeComplete**イベントは、1つ以上のレコードが変更された後に呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
WillChangeRecord adReason, cRecords, adStatus, pRecordset  
RecordChangeCompleteadReason, cRecords, pError, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>パラメーター  
 *adReason*  
 このイベントの理由を指定する[Eventreason 列挙](../../../ado/reference/ado-api/eventreasonenum.md)値。 この値には、 **Adrsnaddnew**、 **adrsnaddnew**、 **adrsnaddnew**、 **adRsnUndoUpdate**、 **AdRsnUndoAddNew**、 **adRsnUndoDelete**、または**adrsnfirstchange**を指定できます。  
  
 *cRecords*  
 変更されるレコードの数を示す**Long**値 (影響を受けます)。  
  
 *pError*  
 [エラー](../../../ado/reference/ado-api/error-object.md)オブジェクトです。 *Adstatus*の値が**adstatuserrorて**いる場合に発生したエラーについて説明します。それ以外の場合は設定されません。  
  
 *adStatus*  
 [Eventstatusenum](../../../ado/reference/ado-api/eventstatusenum.md)状態の値です。  
  
 が**呼び出されたときに**、イベントを発生させた操作が成功した場合、このパラメーターは**adstatusok**に設定されます。 このイベントが保留中の操作の取り消しを要求できない場合は、 **Adstatuscantdeny**に設定されます。  
  
 **RecordChangeComplete**が呼び出されると、このパラメーターは、イベントの原因となった操作が成功した場合は**adstatusok**に、操作が失敗した場合は**Adstatuserror curred**に設定されます。  
  
 このパラメーターを**Adstatuscancel**に設定し**てから、** このイベントの原因となった操作の取り消しを要求するか、このパラメーターを**adStatusUnwantedEvent**に設定して後続の通知を防止します。  
  
 **RecordChangeComplete**が返される前に、このパラメーターを**adStatusUnwantedEvent**に設定して、後続の通知が行われないようにします。  
  
 *pRecordset*  
 **レコードセット**オブジェクトです。 このイベントが発生した**レコードセット**。  
  
## <a name="remarks"></a>解説  
 [Update](../../../ado/reference/ado-api/update-method.md)、 [Delete](../../../ado/reference/ado-api/delete-method-ado-recordset.md)、 [CancelUpdate](../../../ado/reference/ado-api/cancelupdate-method-ado.md)、 [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md)、 [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md)、および[CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md)の各**レコードセット**操作により、行の最初に変更されたフィールドに対して、 **RecordChangeComplete**イベントが**発生する可能性**があります。 **レコードセット** [CursorType](../../../ado/reference/ado-api/cursortype-property-ado.md)の値によって、イベントを発生させる操作が決定されます。  
  
 このイベントでは、**レコードセット**[フィルター](../../../ado/reference/ado-api/filter-property.md)プロパティが**adFilterAffectedRecords**に設定さ**れてい**ます。 イベントの処理中にこのプロパティを変更することはできません。  
  
 **AdReason**パラメーターを含むイベントのイベント通知を完全に停止するには、使用可能な**adReason**値ごとに**adstatus**パラメーターを**adStatusUnwantedEvent**に設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [ADO Events モデルの例 (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [ADO イベント ハンドラーの概要](../../../ado/guide/data/ado-event-handler-summary.md)
