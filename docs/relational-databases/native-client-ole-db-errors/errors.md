---
title: エラー | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: MightyPen
ms.author: genemi
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 45dd62bfcf1006bd675259c279b1f85a64ea630a
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "73769452"
---
# <a name="errors"></a>エラー
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  OLE オブジェクトや COM オブジェクトは、オブジェクト メンバー関数の HRESULT リターン コードによってエラーを報告します。 OLE と COM の HRESULT は、ビットがまとめられている構造体です。 OLE には、構造体のメンバーを取り出すマクロが用意されています。  
  
 OLE と COM は、**IErrorInfo** インターフェイスを指定します。 このインターフェイスでは、**GetDescription** などのメソッドを公開します。 これにより、クライアントは OLE サーバーや COM サーバーからエラーの詳細を取得できます。 OLE DB では、複数のエラー情報パケットを 1 回のメンバー関数の実行で返すことができるように **IErrorInfo** を拡張します。  
  
 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では複数のエラーを返すことができます。 アプリケーションで一度に 1 つずつサーバー エラーを取得するには、ISQLErrorInfo および IErrorRecords と組み合わせて [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) を呼び出します。  
  
 Native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client OLE DB プロバイダーは、OLE DB レコード拡張された**IErrorInfo**、カスタム**ISQLErrorInfo**、およびプロバイダー固有の[ISQLServerErrorInfo](https://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1) error オブジェクトインターフェイスを公開します。  
  
 エラーのトレースの詳細については、「[データ アクセスのトレース](https://go.microsoft.com/fwlink/?LinkId=125805)」を参照してください。 で[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]追加されたエラートレースの機能強化の詳細については、「[拡張イベントログの診断情報へのアクセス](../../relational-databases/native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [リターン コード](../../relational-databases/native-client-ole-db-errors/return-codes.md)  
  
-   [エラー インターフェイス内の情報](../../relational-databases/native-client-ole-db-errors/information-in-error-interfaces.md)  
  
-   [SQL Server エラーの詳細](../../relational-databases/native-client-ole-db-errors/sql-server-error-detail.md)  
  
-   [エラー情報の取得](../../relational-databases/native-client-ole-db-errors/retrieving-error-information.md)  
  
-   [SQL Server のメッセージ結果](../../relational-databases/native-client-ole-db-errors/sql-server-message-results.md)  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
