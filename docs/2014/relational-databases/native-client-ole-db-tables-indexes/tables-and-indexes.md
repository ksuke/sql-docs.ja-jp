---
title: テーブルとインデックス |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a4f0b3fcf58f3f2767fbdc653327bec334545bdd
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63213528"
---
# <a name="tables-and-indexes"></a>テーブルとインデックス
  Native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB プロバイダーは、 **iindexdefinition**インターフェイスと**itabledefinition**インターフェイスを公開します。これにより、コンシューマー [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]はテーブルとインデックスを作成、変更、および削除できます。 有効なテーブルやインデックスの定義は、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のバージョンによって異なります。  
  
 テーブルやインデックスを作成または削除できるかどうかは、コンシューマー アプリケーション ユーザーの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] アクセス権によって決まります。 テーブルの削除は、宣言参照整合性制約やその他の要因の指定によってさらに制約できます。  
  
 を対象[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]とするほとんどのアプリケーションは、これら[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]の Native Client OLE DB プロバイダーインターフェイスではなく、sql-dmo を使用します。 SQL-DMO は、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のすべての管理機能をサポートする OLE オートメーション オブジェクトの集まりです。 複数の OLE DB プロバイダーを対象とするアプリケーションでは、さまざまな OLE DB プロバイダーでサポートされる、これらの汎用 OLE DB インターフェイスを使用します。  
  
 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では、プロバイダー固有の DBPROPSET_SQLSERVERCOLUMN プロパティ セットで、次のプロパティを定義しています。  
  
|プロパティ ID|[説明]|  
|-----------------|-----------------|  
|SSPROP_COL_COLLATIONNAME|型 : VT_BSTR<br /><br /> R/W: 書き込み<br /><br /> 既定値 : NULL<br /><br /> 説明 : このプロパティは、**ITableDefinition** でのみ使用します。 このプロパティに指定した文字列は、[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) ステートメントの作成時に<br /><br /> ステートメントの使用などがあります。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server テーブルの作成](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [SQL Server テーブルへの列の追加](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [SQL Server テーブルからの列の削除](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [SQL Server テーブルの削除](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [SQL Server インデックスの作成](../../relational-databases/indexes/indexes.md)  
  
-   [SQL Server インデックスの削除](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)   
 [DROP TABLE &#40;Transact-sql&#41;](/sql/t-sql/statements/drop-table-transact-sql)   
 [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)   
 [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
