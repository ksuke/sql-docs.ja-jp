---
title: オペレーティングシステムの認証を使用する |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC driver for Oracle [ODBC], authentication
- authentication [ODBC]
ms.assetid: 613daef7-3171-42d0-b7e3-3879280f864d
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 56f09a82c2e67ee74ce140f4742bfaf0bcce247f
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68088125"
---
# <a name="using-operating-system-authentication"></a>オペレーティング システムの認証の使用
> [!IMPORTANT]  
>  この機能は、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 代わりに、Oracle によって提供される ODBC ドライバーを使用してください。  
  
 Oracle オペレーティングシステム認証は、データベースアカウントへのアクセスを制御するために、基になるオペレーティングシステムに依存します。 この種類のログインを使用する場合、ユーザーはパスワードを入力する必要はありません。  
  
 この機能を利用するには、ユーザー ID として "/" を指定し、接続 Api ( [SQLBrowseConnect](../../odbc/microsoft/level-2-api-functions-odbc-driver-for-oracle.md)、 [SQLConnect](../../odbc/microsoft/core-level-api-functions-odbc-driver-for-oracle.md)、または[SQLDriverConnect](../../odbc/microsoft/level-1-api-functions-odbc-driver-for-oracle.md)) のいずれかを使用して接続するときにパスワードを指定しないようにします。  
  
 Oracle データベースでは、SQL * Net 認証サービスを使用して、ログオンしているユーザーを認証します。 このサービスは、ユーザーが SQLPlus を使用して Oracle にログインしている場合に適しています。ただし、ログインしているユーザーがインターネットインフォメーションサービスなどのサービスである場合、認証は失敗します。 これは SQL\*Net 認証の既知の制限であり、次のエラーが発生します。 "[Microsoft] [ODBC Driver for Oracle] [ORACLE] ORA-12641: TNS: Authentication service は初期化できませんでした。"  
  
 この問題を修正するには、Sqlnet. ora ファイルを編集します。 通常、この構成ファイルは、Oracle ホームディレクトリの Network\ Admin サブディレクトリに格納されます。 次の行を Sqlnet. ora に追加します。  
  
```  
SQLNET.AUTHENTICATION_SERVICES = (none)  
```
