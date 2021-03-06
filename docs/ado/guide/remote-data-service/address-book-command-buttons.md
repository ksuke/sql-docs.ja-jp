---
title: アドレス帳のコマンドボタン |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- address book application scenario [ADO], command buttons
- RDS scenarios [ADO], command buttons
ms.assetid: 80676831-6488-4dad-a558-c47c52256a22
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d1aa5b628bec9399374b94a2cd78090207bf09b7
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67922985"
---
# <a name="address-book-command-buttons"></a>アドレス帳のコマンド ボタン
アドレス帳アプリケーションには、次のコマンドボタンが含まれています。  
  
-   クエリをデータベースに送信するための [**検索**] ボタン。  
  
-   新しい検索を開始する前にテキストボックスをクリアする**クリア**ボタン。  
  
-   従業員レコードの変更を保存するための [**更新プロファイル**] ボタン。  
  
-   変更を破棄するための **[変更のキャンセル**] ボタン。  
  
> [!IMPORTANT]
>  Windows 8 と windows Server 2012 以降では、RDS サーバーコンポーネントが Windows オペレーティングシステムに含まれなくなりました (詳細については、「Windows 8 および[Windows server 2012 の互換性に関するクックブック](https://www.microsoft.com/download/details.aspx?id=27416)」を参照してください)。 RDS クライアントコンポーネントは、今後のバージョンの Windows では削除される予定です。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションは、 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)に移行する必要があります。  
  
## <a name="find-button"></a>[検索] ボタン  
 [**検索**] ボタンをクリックすると、VBScript の Find_OnClick サブプロシージャがアクティブ化され、SQL クエリが作成されて送信されます。 このボタンをクリックすると、データグリッドが設定されます。  
  
## <a name="building-the-sql-query"></a>SQL クエリの作成  
 Find_OnClick Sub プロシージャの最初の部分では、グローバル SQL SELECT ステートメントにテキスト文字列を追加することによって、1つの句で SQL クエリを作成します。 まず、変数`myQuery`に、データソーステーブルのすべてのデータ行を要求する SQL SELECT ステートメントを設定します。 次に、サブプロシージャは、ページ上の4つの入力ボックスのそれぞれをスキャンします。  
  
 このプログラムでは、SQL `like`ステートメントの作成に使用されている単語が使用されるため、クエリは完全一致ではなく、部分文字列検索になります。  
  
 たとえば、[**姓**] ボックスにエントリ "" "が含まれていて、[**タイトル**] ボックスに" プログラムマネージャー "というエントリが含まれ`myQuery`ている場合、SQL ステートメント (の値) は次のようになります。  
  
```sql
Select FirstName, LastName, Title, Email, Building, Room, Phone from Employee where lastname like 'Berge%' and title like 'Program Manager%'  
```  
  
 クエリが成功した場合、"Berger" などのテキストを含む姓を持つすべての人と、"プログラムマネージャー" (プログラムマネージャー、高度なテクノロジなど) という語を含むタイトルが HTML データグリッドに表示されます。  
  
## <a name="preparing-and-sending-the-query"></a>クエリの準備と送信  
 Find_OnClick サブプロシージャの最後の部分は、2つのステートメントで構成されます。 最初のステートメントは、RDS の[SQL](../../../ado/reference/rds-api/sql-property.md)プロパティを割り当て[ます。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)オブジェクトは、動的に構築された SQL クエリと同じです。 2番目のステートメントは、RDS を発生させ**ます。DataControl** object (`DC1`) を実行してデータベースを照会し、グリッドにクエリの新しい結果を表示します。  
  
```vb
Sub Find_OnClick  
   '...  
   DC1.SQL = myQuery  
   DC1.Refresh  
End Sub  
```  
  
## <a name="update-profile-button"></a>[プロファイルの更新] ボタン  
 [**プロファイルの更新**] ボタンをクリックすると、VBScript Update_OnClick サブプロシージャがアクティブ化され、RDS が実行さ[れます。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)オブジェクトの (`DC1`) [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md)メソッドと[Refresh](../../../ado/reference/rds-api/refresh-method-rds.md)メソッド。  
  
```vb
Sub Update_OnClick  
   DC1.SubmitChanges  
   DC1.Refresh  
End Sub  
```  
  
 が`DC1.SubmitChanges`実行されると、リモートデータサービスはすべての更新情報をパッケージ化し、HTTP 経由でサーバーに送信します。 更新プログラムがすべて-または何もありません。更新プログラムの一部が正常に実行されなかった場合、変更は一切行われず、ステータスメッセージが返されます。 `DC1.Refresh`リモートデータサービスと**SubmitChanges**した後には必要ありませんが、最新のデータが確保されます。  
  
## <a name="cancel-changes-button"></a>[変更の取り消し] ボタン  
 **[変更のキャンセル]** をクリックすると、RDS を実行する VBScript Cancel_OnClick サブプロシージャがアクティブ化され[ます。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)オブジェクトの (`DC1)` [CancelUpdate](../../../ado/reference/rds-api/cancelupdate-method-rds.md)メソッド)。  
  
```vb
Sub Cancel_OnClick  
   DC1.CancelUpdate  
End Sub  
```  
  
 を`DC1.CancelUpdate`実行すると、前回のクエリまたは更新以降にユーザーがデータグリッドの employee レコードに対して行ったすべての編集が破棄されます。 元の値を復元します。  
  
## <a name="see-also"></a>参照  
 [アドレス帳のナビゲーションボタン](../../../ado/guide/remote-data-service/address-book-navigation-buttons.md)   
 [DataControl オブジェクト (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)


