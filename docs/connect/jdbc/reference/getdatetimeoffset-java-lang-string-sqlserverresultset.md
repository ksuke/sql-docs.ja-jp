---
title: getDateTimeOffset(java.lang.string) (SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: e585927c-0dee-43fd-b71e-c9f1701790bd
author: MightyPen
ms.author: genemi
ms.openlocfilehash: a929b5869e58f4f1207b14474302fdb247251850
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "67983858"
---
# <a name="getdatetimeoffsetjavalangstring-sqlserverresultset"></a>getDateTimeOffset(java.lang.string) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  このメソッドは [!INCLUDE[msCoName](../../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] JDBC Driver 3.0 で追加されました。  
  
 パラメーターに渡されたインデックスを使用して、指定された列の値が Java プログラミング言語の [DateTimeOffset Class](../../../connect/jdbc/reference/datetimeoffset-class.md) オブジェクトとして取得されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
public microsoft.sql.DateTimeOffset getDateTimeOffset(String columnName)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *columnName*  
  
 列の名前です。  
  
## <a name="return-value"></a>戻り値  
 [DateTimeOffset クラス](../../../connect/jdbc/reference/datetimeoffset-class.md) オブジェクト。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>解説  
 [DateTimeOffset クラス](../../../connect/jdbc/reference/datetimeoffset-class.md)値は [SQLServerResultSet.updateDateTimeOffset](../../../connect/jdbc/reference/updatedatetimeoffset-sqlserverresultset.md) を使用して取得できます。  
  
## <a name="see-also"></a>参照  
 [SQLServerResultSet のメンバー](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet クラス](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
