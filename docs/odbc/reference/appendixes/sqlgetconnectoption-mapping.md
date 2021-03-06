---
title: SQLGetConnectOption Mapping |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLGetConnectOption
- SQLGetConnectOption function [ODBC], mapping
ms.assetid: e3792fe4-a955-473a-a297-c1b2403660c4
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d0533a0ee616d4097793eca46c7d45a269142737
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68086405"
---
# <a name="sqlgetconnectoption-mapping"></a>SQLGetConnectOption のマッピング
アプリケーションが ODBC *3. x*ドライバーを介して**SQLGetConnectOption**を呼び出すとき、  
  
```  
SQLGetConnectOption(hdbc, fOption, pvParam)   
```  
  
 は次のようにマップされます。  
  
-   *Foption*が文字列を返す ODBC 定義の接続オプションを示す場合、ドライバーマネージャーはを呼び出します。  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
-   *Foption*が32ビットの整数値を返す ODBC 定義の接続オプションを示す場合、ドライバーマネージャーはを呼び出します。  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, 0, NULL)  
    ```  
  
-   *Foption*がドライバーで定義されたステートメントオプションを示す場合、ドライバーマネージャーはを呼び出します。  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
 上記の3つのケースでは、 *Connectionhandle*引数は*hdbc*の値に設定され、*属性*引数は*foption*の値に設定され、 *valueptr*引数は*pvparam*と同じ値に設定されます。  
  
 ODBC で定義された文字列接続オプションの場合、ドライバーマネージャーは、 **Sqlgetconnectattr**への呼び出しで*bufferlength*引数を事前に定義された最大長 (SQL_MAX_OPTION_STRING_LENGTH) に設定します。文字列以外の接続オプションでは、 *Bufferlength*は0に設定されます。  
  
 ODBC 3.x ドライバーの場合、ドライバーマネージャーは、*オプション*が SQL_CONN_OPT_MIN と SQL_CONN_OPT_MAX の間にあるかどうか、または SQL_CONNECT_OPT_DRVR_START より大きいかどうかを確認しなく*なります。* ドライバーは、オプション値の有効性を確認する必要があります。
