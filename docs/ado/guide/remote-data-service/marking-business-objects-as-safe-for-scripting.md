---
title: スクリプトのためにビジネスオブジェクトを安全としてマークするMicrosoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- business objects in RDS [ADO]
ms.assetid: 0be98d1a-ab3d-4dce-a166-dacda10d154a
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 55ae560f35a06e77803bfb011f4d430d5079ea05
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67922602"
---
# <a name="marking-business-objects-as-safe-for-scripting"></a>スクリプト用にビジネス オブジェクトを安全とマークする
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および[Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416)」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
 セキュリティで保護されたインターネット環境を確保するために、RDS でインスタンス化されたビジネスオブジェクトをマークする必要があり[ます。](../../../ado/reference/rds-api/dataspace-object-rds.md)"スクリプトに対して安全" としての、オブジェクトの[CreateObject](../../../ado/reference/rds-api/createobject-method-rds.md)メソッド。 DCOM で使用する前に、システムレジストリのライセンス領域でそれらがマークされていることを確認する必要があります。  
  
> [!NOTE]
>  "安全なスクリプトを作成する" とマークされたビジネスオブジェクト、または初期化に安全なビジネスオブジェクトは、ネットワーク上のすべてのユーザーがインスタンス化して初期化できます。 ビジネスオブジェクトを "スクリプトに対して安全" にマークしても、安全ではありません。 このようなオブジェクトが機密データに対して保護されていないアクセスポイントを提示しないように、ビジネスオブジェクトが最高レベルのセキュリティでコーディングされていることを確認することが非常に重要です。  
  
 ビジネスオブジェクトをスクリプトの安全として手動でマークするには、次のテキストを含む .reg 拡張子を持つテキストファイルを作成します。 この例では\<、 *myactivexguid*> は、ビジネスオブジェクトの16進数の guid 番号です。 次の2つの数値を使用すると、安全なスクリプト作成機能が有効になります。  
  
```console
[HKEY_CLASSES_ROOT\CLSID\<MyActiveXGUID>\Implemented   
Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}]  
[HKEY_CLASSES_ROOT\CLSID\<MyActiveXGUID>\Implemented   
Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}]  
```  
  
 レジストリエディターを使用するか、エクスプローラーで .reg ファイルをダブルクリックして、ファイルを保存し、レジストリにマージします。  
  
 Microsoft Visual Basic で作成されたビジネスオブジェクトは、パッケージおよび配置ウィザードを使用して、自動的に "スクリプトに安全" としてマークできます。 ウィザードで安全性の設定を指定するように求められたら、[**初期化のために安全**] を選択し、**スクリプトの**安全性を確保します。  
  
 最後の手順では、アプリケーションのセットアップウィザードによって .htm ファイルと .cab ファイルが作成されます。 この2つのファイルを対象のコンピューターにコピーし、.htm ファイルをダブルクリックしてページを読み込み、サーバーを正しく登録することができます。  
  
 Business オブジェクトは既定では Windows\System32\Occache ディレクトリにインストールされるため、Windows\System32 ディレクトリに移動し、正しいパスに一致するように**HKEY_CLASSES_ROOT/\\CLSID**\<*myactivexguid*>\\**InprocServer32**レジストリキーを変更します。


