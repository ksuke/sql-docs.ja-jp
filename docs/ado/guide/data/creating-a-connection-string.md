---
title: 接続文字列を作成する |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/20/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [ADO]
- connection strings [ADO]
ms.assetid: 14eae122-2d1e-40c8-b88e-b7cb8dfbc93b
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 3c9d81ef7be98f3c65167de24b3ff59ac6f05df5
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67925760"
---
# <a name="creating-a-connection-string"></a>接続文字列の作成
接続文字列は、セミコロンで区切られた引数と値のペアのリスト (パラメーター) で構成されます。 次に例を示します。  
  
```syntax
"arg1=val1; arg2=val2; ... argN=valN;"  
```  
  
 すべてのパラメーターは、ADO または指定されたプロバイダーによって認識される必要があります。  
  
 ADO は、接続文字列の次の5つの引数を認識します。  
  
|引数|[説明]|  
|--------------|-----------------|  
|*プロバイダー*|接続に使用するプロバイダーの名前を指定します。|  
|*ファイル名*|事前設定された接続情報を含むプロバイダー固有のファイル (永続化されたデータソースオブジェクトなど) の名前を指定します。|  
|*URL*|ファイルやディレクトリなど、リソースを識別する絶対 URL として接続文字列を指定します。|  
|*リモートプロバイダー*|クライアント側接続を開くときに使用するプロバイダーの名前を指定します。 (リモートデータサービスのみ)。|  
|*リモートサーバー*|クライアント側接続を開くときに使用するサーバーのパス名を指定します。 (リモートデータサービスのみ)。|  
  
 その他の引数は、ADO によって処理されることなく、 *provider*引数でという名前のプロバイダーに渡されます。  
  
 HelloData の HelloData アプリケーション[: 単純な ADO アプリケーション](../../../ado/guide/data/hellodata-a-simple-ado-application.md)では、次の接続文字列が使用されていました。  
  
```vb
m_sConnStr = "Provider=SQLOLEDB;Data Source=MySqlServer;" & _  
             "Initial Catalog=Northwind;Integrated Security='SSPI';"  
```  
  
 この接続文字列では、ado は`"Provider=SQLOLEDB"`パラメーターのみを認識します。これにより、ado データソースとして SQL Server の Microsoft OLE DB Provider が指定されます。 残りの引数と値のペア`"Data Source=MySqlServer; Initial Catalog=Northwind;Integrated Security='SSPI';"`は、そのままこのプロバイダーに渡されます。 このようなパラメーターの型と有効性は、プロバイダー固有です。 接続文字列に渡すことができる有効なパラメーターの詳細については、個々のプロバイダーのドキュメントを参照してください。  
  
 SQL Server ドキュメントの OLE DB プロバイダーに従って、*データソース*パラメーターに "Server" を、 *Initial Catalog*パラメーターに "Database" を使用できます。 したがって、次の接続文字列では、上記と同じ結果が得られます。  
  
```vb
m_sConnStr = "Provider=SQLOLEDB;Server=MySqlServer;" & _  
             "Database=Northwind;Integrated Security='SSPI';"  
```
