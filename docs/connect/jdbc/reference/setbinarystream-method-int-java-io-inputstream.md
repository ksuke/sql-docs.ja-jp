---
title: setBinaryStream (int, java.io.InputStream) メソッド | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 6c32b904-c44b-472e-a084-38f008a742b4
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 483588eee0a5d1baaf7f2eda4a88372c45836d2e
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "67975315"
---
# <a name="setbinarystream-method-int-javaioinputstream"></a>setBinaryStream (int, java.io.InputStream) メソッド
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  指定されたパラメーターを、指定された入力ストリームに設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public final void setAsciiStream(int parameterIndex,  
                                 java.io.InputStream x)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *parameterIndex*  
  
 パラメーターの番号を示す **int** です。  
  
 *x*  
  
 java.io.InputStream オブジェクト。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この setBinaryStream メソッドは、java.sql.PreparedStatement インターフェイスの setBinaryStream メソッドによって指定されます。  
  
## <a name="see-also"></a>参照  
 [setBinaryStream メソッド &#40;SQLServerPreparedStatement&#41;](../../../connect/jdbc/reference/setbinarystream-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement のメンバー](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
