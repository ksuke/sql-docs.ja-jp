---
title: 接続文字列の形式と属性 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- connection strings [ODBC], ODBC driver for Oracle
- ODBC driver for Oracle [ODBC], connection strings
ms.assetid: 0c360112-8720-4e54-a1a6-b9b18d943557
author: MightyPen
ms.author: genemi
ms.openlocfilehash: a007f4c7c92bf4254e4d36638cf2d92ba0764be5
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68082019"
---
# <a name="connection-string-format-and-attributes"></a>接続文字列の形式と属性
> [!IMPORTANT]  
>  この機能は、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 代わりに、Oracle によって提供される ODBC ドライバーを使用してください。  
  
 ダイアログボックスを使用する代わりに、一部のアプリケーションでは、データソース接続情報を指定する接続文字列が必要になる場合があります。 接続文字列は、ドライバーがデータソースに接続する方法を指定する多数の属性で構成されています。 属性は、適切なデータソース接続を作成する前に、ドライバーが認識する必要がある特定の情報を識別します。 各ドライバーは異なる属性セットを持つ場合がありますが、接続文字列の形式は常に同じです。 接続文字列の形式は次のとおりです。  
  
```  
"DSN=data-source-name[;SERVER=value] [;PWD=value] [;UID=value] [;<Attribute>=<value>]"  
```  
  
> [!NOTE]  
>  Microsoft ODBC Driver for Oracle は、ドライバーの最初のバージョンの接続文字列形式をサポートしてい`CONNECTSTRING`ます。これ`SERVER=`は、の代わりに = が使用されています。  
  
 Windows 認証をサポートするデータソースプロバイダーに接続する場合は、接続文字列に`Trusted_Connection=yes`ユーザー ID とパスワードの情報ではなくを指定する必要があります。  
  
 UID、PWD、SERVER (または CONNECTSTRING)、およびドライバーの属性を指定しない場合は、データソース名を指定する必要があります。 ただし、その他のすべての属性は省略可能です。 属性を指定しない場合、その属性の既定値は、[ **ODBC データソースアドミニストレーター** ] ダイアログボックスの [関連する DSN] タブで指定されている属性になります。 属性値は大文字と小文字が区別されます。  
  
 接続文字列の属性は次のとおりです。  
  
|Attribute|[説明]|既定値|  
|---------------|-----------------|-------------------|  
|DSN (DSN)|[ **ODBC データソースアドミニストレーター** ] ダイアログボックスの [ドライバー] タブに表示されるデータソース名。|""|  
|PWD|アクセスする Oracle サーバーのパスワードです。 このドライバーは、Oracle がパスワードに配置する制限をサポートしています。|""|  
|SERVER|アクセスする Oracle サーバーの接続文字列。|""|  
|UID|Oracle サーバーのユーザー名。 システムによっては、この属性は省略可能でない場合があります。つまり、特定のデータベースとテーブルでは、セキュリティ上の理由からこの属性が必要になる場合があります。<br /><br /> Oracle のオペレーティングシステム認証を使用するには、"/" を使用します。|""|  
|BUFFERSIZE|列をフェッチするときに使用される最適なバッファーサイズ。<br /><br /> ドライバーは、Oracle サーバーからの1つのフェッチがこのサイズのバッファーを格納するために必要な行を返すように、フェッチを最適化します。 値が大きいほど、大量のデータをフェッチするとパフォーマンスが向上する傾向があります。|65,535|  
|SYNONYMCOLUMNS|この値が true (1) の場合、SQLColumn () API 呼び出しによって列情報が返されます。 それ以外の場合、SQLColumn () はテーブルとビューの列のみを返します。 ODBC Driver for Oracle では、この値が設定されていない場合にアクセスが高速になります。|1 で保護されたプロセスとして起動されました|  
|備考|この値が true (1) の場合、ドライバーは[sqlcolumns](../../odbc/microsoft/level-1-api-functions-odbc-driver-for-oracle.md)結果セットの注釈列を返します。 ODBC Driver for Oracle では、この値が設定されていない場合にアクセスが高速になります。|0|  
|StdDayOfWeek|DAYOFWEEK スカラーに ODBC 標準を適用します。 既定では、この設定は有効になっていますが、ローカライズされたバージョンを必要とするユーザーは、Oracle が返すあらゆる動作を使用するように動作を変更できます。|1 で保護されたプロセスとして起動されました|  
|GuessTheColDef|ドライバーが**SQLDescribeCol**の*cbcoldef*引数に対して0以外の値を返す必要があるかどうかを指定します。 計算された数値列や、精度や小数点以下桁数のない数値として定義された列など、Oracle によって定義された小数点以下桁数がない列にのみ適用されます。 Oracle がその情報を提供していない場合、 **SQLDescribeCol**の呼び出しでは、有効桁数として130が返されます。|0|  
  
 たとえば、MyOracleServerOracle サーバーと Oracle ユーザー Mydatasource を使用して MyDataSource データソースに接続する接続文字列は次のようになります。  
  
```  
"DSN={MyDataSource};UID={MyUserID};PWD={MyPassword};SERVER={MyOracleServer}"  
```  
  
 オペレーティングシステム認証および MyOtherOracleServerOracle サーバーを使用して MyOtherDataSource データソースに接続する接続文字列は次のようになります。  
  
```  
"DSN=MyOtherDataSource;UID=/;PWD=;SERVER=MyOtherOracleServer"  
```
