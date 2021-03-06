---
title: 'レッスン 2 : 接続情報の指定 (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69d7ad1e3a65f49aa850e016e5e5bd609039ccf3
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66108520"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a>レッスン 2 : 接続情報の指定 (Reporting Services)
  チュートリアル プロジェクトにレポートを追加した後、リレーショナル データベース、多次元データベース、その他のリソースのデータにアクセスするためにレポートで使用される接続情報である *データ ソース*を定義する必要があります。  
  
 このレッスンでは、[!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] サンプル データベースをデータ ソースとして使用します。 このチュートリアルでは、このデータベースがローカルコンピューターにインストールさ[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)]れているの既定のインスタンスに配置されていることを前提としています。  
  
### <a name="to-set-up-a-connection"></a>接続を設定するには  
  
1.  **レポートデータ**ペインで、[**新規作成**] をクリックし、[**データソース...**] をクリックします。  
  
    > [!NOTE]  
    >  
  **レポート データ** ペインが表示されていない場合は、 **[表示]** メニューの **[レポート データ]** をクリックします。  
  
2.  
  **[名前]** に「 [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)]」と入力します。  
  
3.  
  **[埋め込み接続]** が選択されていることを確認します。  
  
4.  
  **[種類]** で **[Microsoft SQL Server]** を選択します。  
  
5.  
  **[接続文字列]** に次を入力します。  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     この接続文字列は、 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]、レポート サーバー、および [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] データベースがすべてローカル コンピューターにインストールされていることと、ユーザーが [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] データベースにログオンする権限を持っていることが前提となります。  
  
    > [!NOTE]  
    >  
  [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services または名前付きインスタンスを使用している場合は、接続文字列にインスタンス情報を含める必要があります。  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  接続文字列の詳細については、「 [Reporting Services のデータ接続、データソース、および接続文字列](data-connections-data-sources-and-connection-strings-in-reporting-services.md)」および「 [[データソースのプロパティ] ダイアログボックス-全般](data-source-properties-dialog-box-general.md)」を参照してください。  
  
6.  左ペインで **[資格情報]** をクリックし、 **[Windows 認証 (統合セキュリティ) を使用する]** をクリックします。  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]データソース[!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)]が**レポートデータ**ペインに追加されます。  
  
## <a name="next-task"></a>次の作業  
 
  [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] サンプル データベースへの接続が正常に定義されました。 次に、レポートを作成します。 「[レッスン 3: テーブル レポートのデータセットの定義 &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Reporting Services でのデータ接続、データ ソース、および接続文字列](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
