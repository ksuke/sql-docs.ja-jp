---
title: API 関数に関するスレッドセーフなメモ (ODBC Driver for Oracle) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC driver for Oracle [ODBC], threading
- threading options [ODBC]
- multiple concurrent statements [ODBC]
ms.assetid: f0c9bdfd-f79d-4088-9ecb-afcd8ca7fb73
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 926b2285bcce9a28579fffc4004c5454b2837392
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67912431"
---
# <a name="thread-safety-notes-on-api-functions-odbc-driver-for-oracle"></a>API 関数 (ODBC Driver for Oracle) のスレッド セーフの注意事項
> [!IMPORTANT]  
>  この機能は、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 代わりに、Oracle によって提供される ODBC ドライバーを使用してください。  
  
 Microsoft ODBC Driver for Oracle はスレッドセーフです。ただし、Oracle では、1つの接続で複数のステートメントを同時に使用することはできません。 ドライバーはこの制限を適用します。 つまり、マルチスレッドアプリケーションでは、どのスレッドも ODBC Driver for Oracle をいつでも呼び出すことができますが、ドライバーは元のスレッドがドライバーを終了するまで、同じ接続上の他のすべてのスレッドをブロックします。  
  
 2つの異なる接続に2つのステートメントがある場合、ドライバーはブロックしません。 ただし、2つのステートメントを含む単一の接続がある場合は、ブロックが発生する可能性があります。
