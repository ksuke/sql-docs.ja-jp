---
title: getConnection メソッド (SQLServerPooledConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerPooledConnection.getConnection
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 05bdb61f-26e8-480f-a1c1-1e46a8ed4b70
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 352d867e444158cb2b8754a9cce1752bc4c2ee4a
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "67952696"
---
# <a name="getconnection-method-sqlserverpooledconnection"></a>getConnection メソッド (SQLServerPooledConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  [SQLServerPooledConnection](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md) オブジェクトが表す物理的な接続用のオブジェクト ハンドルを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public java.sql.Connection getConnection()  
```  
  
## <a name="return-value"></a>戻り値  
 Connection オブジェクトです。  
  
## <a name="exceptions"></a>例外  
 java.sql.SQLException  
  
## <a name="remarks"></a>解説  
 この getConnection メソッドは、javax.sql.PooledConnection インターフェイスの getConnection メソッドによって指定されます。  
  
## <a name="see-also"></a>参照  
 [SQLServerPooledConnection のメソッド](../../../connect/jdbc/reference/sqlserverpooledconnection-methods.md)   
 [SQLServerPooledConnection のメンバー](../../../connect/jdbc/reference/sqlserverpooledconnection-members.md)   
 [SQLServerPooledConnection クラス](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md)  
  
  
