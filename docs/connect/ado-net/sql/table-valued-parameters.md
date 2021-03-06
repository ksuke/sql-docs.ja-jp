---
title: テーブル値パラメーター
description: SQL Server 2008 で導入されたテーブル値パラメーターを使用する方法について説明します。
ms.date: 08/15/2019
dev_langs:
- csharp
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.topic: conceptual
author: rothja
ms.author: jroth
ms.reviewer: v-kaywon
ms.openlocfilehash: 29c7be3fbcb027d1789357d0ce823ac6b1c59f2a
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "75243977"
---
# <a name="table-valued-parameters"></a>テーブル値パラメーター

![Download-DownArrow-Circled](../../../ssdt/media/download.png)[ADO.NET をダウンロードする](../../sql-connection-libraries.md#anchor-20-drivers-relational-access)

テーブル値パラメーターは、複数行のデータをクライアント アプリケーションから SQL Server に簡単にマーシャリングするための手段です。複数のラウンド トリップや、データ処理用の特別なサーバー側ロジックは必要ありません。 テーブル値パラメーターを使用すると、クライアント アプリケーションで複数行のデータをカプセル化してサーバーに送信する処理を 1 つのパラメーター化コマンドで実行できます。 受信データ行はテーブル変数に格納され、Transact-SQL を使用して操作できます。  
  
テーブル値パラメーターの列値には、Transact-SQL の標準的な SELECT ステートメントを使ってアクセスできます。 テーブル値パラメーターは厳密に型指定されており、その構造が自動的に検証されます。 テーブル値パラメーターのサイズは、サーバーのメモリによってのみ制限されます。  
  
> [!NOTE]
>  テーブル値パラメーターでデータを返すことはできません。 テーブル値パラメーターは入力専用です。OUTPUT キーワードはサポートされていません。  
  
テーブル値パラメーターの詳細については、次のリソースを参照してください。  
  
|リソース|説明|  
|--------------|-----------------|  
|SQL Server オンライン ブックの[テーブル値パラメーター (データベース エンジン)](https://go.microsoft.com/fwlink/?LinkId=98363)|テーブル値パラメーターを作成する方法について説明します。|  
|SQL Server オンライン ブックの[ユーザー定義テーブル型](https://go.microsoft.com/fwlink/?LinkId=98364)|テーブル値パラメーターを宣言する際に使用するユーザー定義テーブル型について説明します。|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a>複数行を以前のバージョンの SQL Server で渡す  
SQL Server 2008 にテーブル値パラメーターが導入されるまでは、複数行データをストアド プロシージャまたはパラメーター化 SQL コマンドに渡す方法は限られていました。 開発者が選択できる複数の行をサーバーに渡すためのオプションを次に示します。  
  
- 複数のデータ列とデータ行の値を表すには、一連の個別のパラメーターを使用します。 このメソッドを使用して渡すことができるデータの量は、許可されているパラメーター数によって制限されます。 SQL Server プロシージャが持つことのできるパラメーター数は最大 2,100 です。 これらの個々の値をテーブル変数または一時テーブルにまとめて処理するには、サーバー側ロジックが必要です。  
  
- 複数のデータ値を区切り文字列または XML ドキュメントにバンドルし、それらのテキスト値をプロシージャまたはステートメントに渡します。 これを行うには、そのプロシージャまたはステートメントに、データ構造の検証と値のバンドルの解除に必要なロジックが含まれている必要があります。  
  
- 複数の行 (<xref:Microsoft.Data.SqlClient.SqlDataAdapter> の `Update` メソッドを呼び出すことによって作成された行など) に影響を及ぼす、データを変更するための一連の個別 SQL ステートメントを作成します。 サーバーへの変更の送信は個別に行うことも、グループにまとめることもできます。 ただし、複数のステートメントをまとめてバッチ送信しても、サーバーで実行されるときはそれぞれ個別に処理されます。  
  
- `bcp` ユーティリティ プログラムまたは <xref:Microsoft.Data.SqlClient.SqlBulkCopy> オブジェクトを使用して、多数のデータ行をテーブルに読み込みます。 この手法は非常に効率的ですが、サーバー側の処理は、データが一時テーブルまたはテーブル変数に読み込まれない限りサポートされません。  
  
## <a name="creating-table-valued-parameter-types"></a>テーブル値パラメーターの型の作成  
テーブル値パラメーターは、Transact-SQL の CREATE TYPE ステートメントを使用して定義された厳密に型指定されたテーブルの構造に基づいています。 クライアント アプリケーションでテーブル値パラメーターを使用するには、まず SQL Server でテーブル型を作成し、その構造を定義する必要があります。 テーブル型の作成の詳細については、SQL Server オンライン ブックの「[ユーザー定義テーブル型](https://go.microsoft.com/fwlink/?LinkID=98364)」を参照してください。  
  
次のステートメントは、CategoryID 列と CategoryName 列で構成される、CategoryTableType という名前のテーブル型を作成しています。  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
テーブル型を作成したら、その型に基づいてテーブル値パラメーターを宣言できます。 次の Transact-SQL フラグメントは、ストアド プロシージャ定義の中でテーブル値パラメーターを宣言する方法を示しています。 テーブル値パラメーターを宣言するには、READONLY キーワードが必要であることに注意してください。  
  
```sql
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a>テーブル値パラメーターを使用したデータの変更 (transact-SQL)  
1 つのステートメントを実行することで、テーブル値パラメーターを、複数の行に影響を与えるセットベースのデータ変更で使用できます。 たとえば、テーブル値パラメーター内のすべての行を選択して、データベース テーブルに挿入できます。また、テーブル値パラメーターを更新対象テーブルに結合して、更新ステートメントを作成することもできます。  
  
次の Transact-SQL UPDATE ステートメントは、テーブル値パラメーターを Categories テーブルに結合して使用する方法を示しています。 テーブル値パラメーターを FROM 句で JOIN と共に使用する場合は、次に示すように、別名も使用する必要があります。ここでは、テーブル値パラメーターは "ec" という別名になっています。  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
この Transact-SQL の例は、単一のセット ベース操作で INSERT を実行するためにテーブル値パラメーターから行を選択する方法を示しています。  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a>テーブル値パラメーターの制限  
テーブル値パラメーターには制限がいくつかあります。  
  
- テーブル値パラメーターを [CLR ユーザー定義の関数](../../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)に渡すことはできません。  
  
- テーブル値パラメーターには、UNIQUE 制約または PRIMARY KEY 制約に対応する目的でのみインデックスを設定できます。 SQL Server では、テーブル値パラメーターの統計が保持されません。  
  
- テーブル値パラメーターは Transact-SQL コードの中では読み取り専用です。 テーブル値パラメーターの行では列の値を更新できません。また、行の挿入や削除もできません。 テーブル値パラメーターでストアド プロシージャまたはパラメーター化されたステートメントに渡されたデータを変更するには、そのデータを一時テーブルまたはテーブル変数に挿入する必要があります。  
  
- ALTER TABLE ステートメントを使用して、テーブル値パラメーターの設計を変更することはできません。  
  
## <a name="configuring-a-sqlparameter-example"></a>SqlParameter 構成の例  
<xref:Microsoft.Data.SqlClient> では、テーブル値パラメーターのデータを <xref:System.Data.DataTable>、<xref:System.Data.Common.DbDataReader>、または <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.Data.SqlClient.Server.SqlDataRecord> オブジェクトから読み込むことができます。 <xref:Microsoft.Data.SqlClient.SqlParameter> の <xref:Microsoft.Data.SqlClient.SqlParameter.TypeName%2A> プロパティを使用して、テーブル値パラメーターの型名を指定する必要があります。 `TypeName` は、サーバーで以前に作成した互換性のある型の名前と一致する必要があります。 次のコード フラグメントは、データを挿入するために <xref:Microsoft.Data.SqlClient.SqlParameter> を構成する方法を示しています。  
 
次の例では、`addedCategories` 変数に <xref:System.Data.DataTable> が含まれています。 変数がどのように設定されているかを確認するには、次の「[ストアド プロシージャへのテーブル値パラメーターの受け渡し](#passing)」を参照してください。

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```   
  
<xref:System.Data.Common.DbDataReader> から派生した任意のオブジェクトを使用して、一連の行データをテーブル値パラメーターに挿入することもできます。その方法を次のフラグメントに示します。  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
## <a name="passing"></a> ストアド プロシージャへのテーブル値パラメーターの受け渡し  
この例は、テーブル値パラメーターのデータをストアド プロシージャに渡す方法を示しています。 追加された行が、<xref:System.Data.DataTable.GetChanges%2A> メソッドを使って新しい <xref:System.Data.DataTable> に抽出された後、 <xref:Microsoft.Data.SqlClient.SqlCommand> が定義され、<xref:Microsoft.Data.SqlClient.SqlCommand.CommandType%2A> プロパティが <xref:System.Data.CommandType.StoredProcedure> に設定されます。 <xref:Microsoft.Data.SqlClient.SqlParameter> は <xref:Microsoft.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> メソッドを使って設定され、<xref:Microsoft.Data.SqlClient.SqlParameter.SqlDbType%2A> は `Structured` に設定されます。 その後、<xref:Microsoft.Data.SqlClient.SqlCommand> は、<xref:Microsoft.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> メソッドを使って実行されます。  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a>テーブル値パラメーターをパラメーター化 SQL ステートメントに渡す  
 次の例は、データ ソースとしてテーブル値パラメーターが指定されている INSERT ステートメントと SELECT サブクエリを使用して、dbo.Categories テーブルにデータを挿入する方法を示しています。 テーブル値パラメーターをパラメーター化 SQL ステートメントに渡すときは、<xref:Microsoft.Data.SqlClient.SqlParameter> の新しい <xref:Microsoft.Data.SqlClient.SqlParameter.TypeName%2A> プロパティを使用して、テーブル値パラメーターの型名を指定する必要があります。 この `TypeName` は、サーバーで以前に作成した互換性のある型の名前と一致する必要があります。 この例のコードは、`TypeName` プロパティを使用して、dbo.CategoryTableType で定義されている型構造体を参照しています。  
  
> [!NOTE]
>  テーブル値パラメーターの ID 列に値を指定する場合は、そのセッションに対して SET IDENTITY_INSERT ステートメントを発行する必要があります。  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =   
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
## <a name="streaming-rows-with-a-datareader"></a>DataReader を使用した行のストリーミング  
<xref:System.Data.Common.DbDataReader> から派生した任意のオブジェクトを使用して、一連の行データをテーブル値パラメーターに挿入することもできます。 次のコード フラグメントは、<xref:System.Data.OracleClient.OracleCommand> と <xref:System.Data.OracleClient.OracleDataReader> を使用して、Oracle データベースからデータを取得する方法を示しています。 その後、<xref:Microsoft.Data.SqlClient.SqlCommand> を、1 つの入力パラメーターを使用してストアド プロシージャを呼び出すように構成します。 <xref:Microsoft.Data.SqlClient.SqlParameter> の <xref:Microsoft.Data.SqlClient.SqlParameter.SqlDbType%2A> プロパティは `Structured` に設定されます。 <xref:Microsoft.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> は、`OracleDataReader` の結果セットを、テーブル値パラメーターとしてストアド プロシージャに渡します。  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
## <a name="next-steps"></a>次のステップ
- [ADO.NET での SQL Server のデータ操作](sql-server-data-operations.md)
