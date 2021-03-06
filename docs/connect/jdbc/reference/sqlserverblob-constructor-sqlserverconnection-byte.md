---
title: SQLServerBlob コンストラクター (SQLServerConnection, byte) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection, byte[].SQLServerBlob
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9fe573e3-30db-4828-abab-e9346493e931
author: MightyPen
ms.author: genemi
ms.openlocfilehash: c4f3c26ca45da6cba3a86324e970117cde9fcc4b
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "67971993"
---
# <a name="sqlserverblob-constructor-sqlserverconnection-byte"></a>SQLServerBlob コンストラクター (SQLServerConnection, byte)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  [SQLServerConnection](../../../connect/jdbc/reference/sqlserverblob-class.md) オブジェクトと [byte](../../../connect/jdbc/reference/sqlserverconnection-class.md) 配列が渡されたときに、**SQLServerBlob** クラスの新しいインスタンスを初期化します。  
  
> [!NOTE]  
>  このメソッドは、JDBC Driver Version 2.0 では非推奨とされました。 代わりに、[SQLServerConnection](../../../connect/jdbc/reference/createblob-method-sqlserverconnection.md) クラスの [createBlob](../../../connect/jdbc/reference/sqlserverconnection-class.md) メソッドを使用してください。  
  
## <a name="syntax"></a>構文  
  
```  
  
public SQLServerBlob(SQLServerConnection connection,  
                     byte[] data)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *connection*  
  
 SQLServerConnection オブジェクト。  
  
 *data*  
  
 **byte** 配列。  
  
## <a name="see-also"></a>参照  
 [SQLServerBlob コンストラクター](../../../connect/jdbc/reference/sqlserverblob-constructors.md)   
 [SQLServerBlob のメンバー](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [SQLServerBlob クラス](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  
