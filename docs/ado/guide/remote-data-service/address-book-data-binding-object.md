---
title: アドレス帳のデータバインディングオブジェクト |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS scenarios [ADO], data-binding object
- address book application scenario [ADO], data-binding object
ms.assetid: 080c1925-d453-4b89-92ac-c93591490518
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 43623bc100fdfe071fcd00926117400a3c96eebe
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67922972"
---
# <a name="address-book-data-binding-object"></a>アドレス帳のデータ バインディング オブジェクト
アドレス帳アプリケーションは、RDS を使用し[ます。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)データベースの SQL Server データを、アプリケーションのクライアント HTML ページ内のビジュアルオブジェクト (この場合は DHTML テーブル) にバインドするオブジェクト。 イベントドリブンの VBScript プログラムロジックは、RDS を使用し[ます。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) :  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および[Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416)」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
-   データベースに対してクエリを実行し、データベースに更新を送信して、データグリッドを更新します。  
  
-   データグリッドの最初、次、前、または最後のレコードにユーザーが移動できるようにします。  
  
 次のコードでは、RDS を定義し**ます。DataControl**コンポーネント:  
  
```vb
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33"  
   ID=DC1 Width=1 Height=1>  
   <PARAM NAME="SERVER" VALUE="https://<%=Request.ServerVariables("SERVER_NAME")%>">  
   <PARAM NAME="CONNECT" VALUE="Provider=sqloledb;  
Initial Catalog=AddrBookDb;Integrated Security=SSPI;">  
</OBJECT>  
```  
  
 オブジェクトタグは、RDS を定義し**ます。** プログラムの DataControl コンポーネント。 タグには、次の2種類のパラメーターがあります。  
  
-   ジェネリックオブジェクトタグに関連付けられているもの。  
  
-   RDS に固有のもの**です。DataControl**オブジェクト。  
  
## <a name="generic-object-tag-parameters"></a>汎用オブジェクトタグパラメーター  
 次の表では、オブジェクトタグに関連付けられているパラメーターについて説明します。  
  
|パラメーター|[説明]|  
|---------------|-----------------|  
|***CLASSID***|システムに埋め込まれたオブジェクトの型を識別する、128ビットの一意の数値。 この識別子は、ローカルコンピューターのシステムレジストリに保持されます。 (RDS のクラス Id の場合) **。DataControl**オブジェクト、「RDS」を参照してください[。DataControl オブジェクト](../../../ado/reference/rds-api/datacontrol-object-rds.md)。)|  
|***id***|コード内で識別するために使用される埋め込みオブジェクトのドキュメント全体の識別子を定義します。|  
  
## <a name="rdsdatacontrol-tag-parameters"></a>RDS.DataControl タグパラメーター  
 次の表では、RDS に固有のパラメーターについて説明し**ます。DataControl**オブジェクト。 (RDS の完全な一覧については、 **** オブジェクトのパラメーターを DataControl し、実装するタイミングについては、「RDS」を参照してください[。DataControl オブジェクト](../../../ado/reference/rds-api/datacontrol-object-rds.md)。)  
  
|パラメーター|[説明]|  
|---------------|-----------------|  
|[SERVER](../../../ado/reference/rds-api/server-property-rds.md)|HTTP を使用している場合、値は、の前に`https://`あるサーバーコンピューターの名前になります。|  
|[関連付け](../../../ado/reference/rds-api/connect-property-rds.md)|RDS に必要な接続情報を提供し**ます。** SQL Server に接続するための DataControl。|  
|[SERVER](../../../ado/reference/rds-api/sql-property.md)|[レコードセット](../../../ado/reference/ado-api/recordset-object-ado.md)を取得するために使用するクエリ文字列を設定または返します。|  
  
## <a name="see-also"></a>参照  
 [アドレス帳のコマンド ボタン](../../../ado/guide/remote-data-service/address-book-command-buttons.md)


