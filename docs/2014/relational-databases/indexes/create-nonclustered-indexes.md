---
title: 非クラスター化インデックスの作成 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 3dc7c4b9b32ee872ec48e78ecb05a713f2cf8a12
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62651491"
---
# <a name="create-nonclustered-indexes"></a>非クラスター化インデックスの作成
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] では、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] または [!INCLUDE[tsql](../../includes/tsql-md.md)]を使用して非クラスター化インデックスを作成できます。 非クラスター化インデックスは、テーブルに格納されているデータとは別個の、選択された 1 つまたは複数の列を並べ替えるインデックス構造です。 非クラスター化インデックスを使用すると、基になるテーブルを検索するよりも迅速にデータを検索できるようになります。クエリの結果が非クラスター化インデックスのデータのみによって得られたり、非クラスター化インデックスによって基になるテーブル内の行を [!INCLUDE[ssDE](../../includes/ssde-md.md)] に対して指定できたりする場合があります。 一般に、非クラスター化インデックスは、クラスター化インデックスで対応できない、頻繁に使用されるクエリのパフォーマンスを向上させたり、クラスター化インデックスのないテーブル (ヒープと呼ばれます) 内の行を探すために作成します。 1 つのテーブルまたはインデックス付きビューに複数の非クラスター化インデックスを作成できます。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [一般的な実装](#Implementations)  
  
     [セキュリティ](#Security)  
  
-   **以下を使用して非クラスター化インデックスを作成するには:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> はじめに  
  
###  <a name="Implementations"></a>一般的な実装  
 非クラスター化インデックスは、次のように実装されます。  
  
-   **UNIQUE 制約**  
  
     UNIQUE 制約を作成すると、既定では、一意な非クラスター化インデックスが作成され、UNIQUE 制約が適用されます。 テーブルにクラスター化インデックスが存在しない場合は、一意なクラスター化インデックスを指定できます。 詳しくは、「 [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md)」をご覧ください。  
  
-   **制約に依存しないインデックス**  
  
     既定では、クラスター化オプションが指定されていない場合に、非クラスター化インデックスが作成されます。 非クラスター化インデックスは、1 つのテーブルに 999 個まで作成できます。 これには、PRIMARY KEY 制約または UNIQUE 制約によって作成されたインデックスを含みますが、XML インデックスは含みせん。  
  
-   **インデックス付きビューの非クラスター化インデックス**  
  
     非クラスター化インデックスは、ビューで一意なクラスター化インデックスが作成されるまで作成できません。 詳細については、「 [インデックス付きビューの作成](../views/views.md)」を参照してください。  
  
###  <a name="Security"></a> セキュリティ  
  
####  <a name="Permissions"></a> Permissions  
 テーブルまたはビューに対する ALTER 権限が必要です。 実行するには、 **sysadmin** 固定サーバー ロール、または **db_ddladmin** 固定データベース ロールおよび **db_owner** 固定データベース ロールのメンバーである必要があります。  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a>テーブル デザイナーを使用して非クラスター化インデックスを作成するには  
  
1.  オブジェクト エクスプローラーで、非クラスター化インデックスを作成するテーブルが格納されているデータベースをプラス記号をクリックして展開します。  
  
2.  
  **[テーブル]** フォルダーを展開します。  
  
3.  非クラスター化インデックスを作成するテーブルを右クリックし、 **[デザイン]** を選択します。  
  
4.  [**テーブルデザイナー** ] メニューの [**インデックス/キー**] をクリックします。  
  
5.  
  **[インデックス/キー]** ダイアログ ボックスで、 **[追加]** をクリックします。  
  
6.  
  **[選択された主/一意キーまたはインデックス]** ボックスで、新しいインデックスを選択します。  
  
7.  グリッドで、 **[CLUSTERED として作成]** を選択し、プロパティ右のドロップダウン リストの **[いいえ]** を選択します。  
  
8.  **[閉じる]** をクリックします。  
  
9. [**ファイル**] メニューの [ ****_table_name_の保存] をクリックします。  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a>オブジェクト エクスプ ローラーを使用して非クラスター化インデックスを作成するには  
  
1.  オブジェクト エクスプローラーで、非クラスター化インデックスを作成するテーブルが格納されているデータベースをプラス記号をクリックして展開します。  
  
2.  
  **[テーブル]** フォルダーを展開します。  
  
3.  非クラスター化インデックスを作成するテーブルを展開します。  
  
4.  
  **[インデックス]** フォルダーを右クリックし、**[新しいインデックス]** をポイントし、**[非クラスター化インデックス]** を選択します。  
  
5.  
  **[新しいインデックス]** ダイアログ ボックスの **[全般]** ページで、 **[インデックス名]** ボックスに新しいインデックスの名前を入力します。  
  
6.  
  **[インデックス キー列]** で、**[追加]** をクリックします。  
  
7.  [Table_name**から列を選択**__ ] ダイアログボックスで、非クラスター化インデックスに追加するテーブル列のチェックボックスをオンにします。  
  
8.  **[OK]** をクリックします。  
  
9. 
  **[新しいインデックス]** ダイアログ ボックスで、 **[OK]** をクリックします。  
  
##  <a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a>テーブルに非クラスター化インデックスを作成するには  
  
1.  **オブジェクト エクスプローラー**で、 [!INCLUDE[ssDE](../../includes/ssde-md.md)]のインスタンスに接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 詳細については、「[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)」を参照してください。  
  
  
