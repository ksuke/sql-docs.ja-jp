---
title: updateByte (int, byte) メソッド | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.updateByte (int, byte)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e635d789-9218-488e-a213-2e3e09635acc
author: MightyPen
ms.author: genemi
ms.openlocfilehash: da7c1c07537ebd9cb258bbd2eba9c2e8718bfe40
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "67996935"
---
# <a name="updatebyte-method-int-byte"></a>updateByte (int, byte) メソッド
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  渡された列インデックスを使用して、指定された列を **byte** の値で更新します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public void updateByte(int index,  
                       byte x)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *インデックス*  
  
 列インデックスを示す **int** です。  
  
 *x*  
  
 **バイト**値です。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 この updateByte メソッドは、java.sql.ResultSet インターフェイスの updateByte メソッドで規定されています。  
  
## <a name="see-also"></a>参照  
 [updateByte メソッド &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatebyte-method-sqlserverresultset.md)   
 [SQLServerResultSet のメンバー](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet クラス](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
