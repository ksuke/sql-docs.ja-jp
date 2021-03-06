---
title: 'C から SQL へ: Time |Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data conversions from C to SQL types [ODBC], time
- time data type [ODBC]
- converting data from c to SQL types [ODBC], time
ms.assetid: a8da43c9-d9a5-45e5-bd9a-1dd633db2ee0
author: MightyPen
ms.author: genemi
ms.openlocfilehash: c4a3734ff8d9f0cb120e1d33433ee3a301bb59ae
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68019303"
---
# <a name="c-to-sql-time"></a>C から SQL へ: 時刻
Time ODBC C データ型の識別子は次のとおりです。  
  
 SQL_C_TYPE_TIME  
  
 次の表は、C データを変換する必要がある ODBC SQL データ型を示しています。 テーブル内の列と用語の詳細については、「[データを C から SQL データ型に変換する](../../../odbc/reference/appendixes/converting-data-from-c-to-sql-data-types.md)」を参照してください。  
  
|SQL 型識別子|テスト|SQLSTATE|  
|-------------------------|----------|--------------|  
|SQL_CHAR<br /><br /> SQL_VARCHAR<br /><br /> SQL_LONGVARCHAR|列のバイト長 >= 8<br /><br /> 列のバイト長 < 8<br /><br /> データ値が有効な時刻ではありません|該当なし<br /><br /> 22001<br /><br /> 22008|  
|SQL_WCHAR<br /><br /> SQL_WVARCHAR<br /><br /> SQL_WLONGVARCHAR|列の文字長 >= 8<br /><br /> 列の文字長 < 8<br /><br /> データ値が有効な時刻ではありません|該当なし<br /><br /> 22001<br /><br /> 22008|  
|SQL_TYPE_TIME|データ値は有効な時間です<br /><br /> データ値が有効な時刻ではありません|該当なし<br /><br /> 22007|  
|SQL_TYPE_TIMESTAMP|データ値は有効な時刻 [a] です<br /><br /> データ値が有効な時刻ではありません|該当なし<br /><br /> 22007|  
  
 [a] タイムスタンプの日付部分が現在の日付に設定され、タイムスタンプの秒部分の小数部が0に設定されます。  
  
 SQL_C_TYPE_TIME 構造体で有効な値の詳細については、この付録の「 [C データ型](../../../odbc/reference/appendixes/c-data-types.md)」を参照してください。  
  
 時間 C データを文字 SQL データに変換すると、結果として得られる文字データは "*hh*:*mm*:*ss*" 形式になります。  
  
 このドライバーは、time C データ型からデータを変換するときの長さとインジケーターの値を無視し、データバッファーのサイズが time C データ型のサイズであると想定しています。 長さ/インジケーターの値は、 **Sqlputdata**の*StrLen_or_Ind*引数と、 **SQLBindParameter**の*StrLen_or_IndPtr*引数で指定されたバッファーに渡されます。 データバッファーは、 **Sqlputdata**の*DataPtr*引数と**SQLBindParameter**の*parametervalueptr*引数を使用して指定します。
