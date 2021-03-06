---
title: 編集モードの決定 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- editing data [ADO], edit mode
- ADO, editing data
ms.assetid: 4c7e010d-08cd-4e22-9b32-23c36f02f88c
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 22e63bad49586bbbc1a5616114055779cd3ea041
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67925548"
---
# <a name="determining-edit-mode"></a>編集モードの決定
ADO は、現在のレコードに関連付けられている編集バッファーを保持します。 **EditMode**プロパティは、このバッファーに変更が加えられたかどうか、または新しいレコードが作成されたかどうかを示します。 現在のレコードの編集状態を確認するには、 **EditMode**を使用します。 編集プロセスが中断されている場合は、保留中の変更をテストし、 **Update**または**CancelUpdate**メソッドを使用する必要があるかどうかを判断できます。  
  
 **EditMode**は、次の表に示すいずれかの**editmodeenum**定数を返します。  
  
|常時|[説明]|  
|--------------|-----------------|  
|**adEditNone**|編集操作が実行中でないことを示します。|  
|**adEditInProgress**|現在のレコードのデータが変更されていても保存されていないことを示します。|  
|**adEditAdd**|**AddNew**メソッドが呼び出され、コピーバッファー内の現在のレコードが、データベースに保存されていない新しいレコードであることを示します。|  
|**adEditDelete**|現在のレコードが削除されたことを示します。|  
  
 **EditMode**は、現在のレコードがある場合にのみ、有効な値を返すことができます。 **BOF**または**EOF**が**True**の場合、または現在のレコードが削除されている場合、 **EditMode**はエラーを返します。
