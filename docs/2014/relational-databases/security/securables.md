---
title: '[セキュリティ保護可能なリソース] | Microsoft Docs'
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: 7c4a82cfa4d8a82db1e01c49899c3c49c2e01ee9
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62745721"
---
# <a name="securables"></a>[セキュリティ保護可能なリソース]
  セキュリティ保護可能なリソースは、 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] の承認システムによりアクセスが制限されたリソースです。 たとえば、テーブルはセキュリティ保護可能です。 セキュリティ保護可能なリソースの中には他のセキュリティ保護可能なリソースに含まれているものがあります。これらは "スコープ" と呼ばれ、それ自体をセキュリティで保護できる入れ子構造の階層を形成しています。 セキュリティ保護可能なスコープは、 **サーバー**、 **データベース**、および **スキーマ**です。  
  
## <a name="securable-scope-server"></a>セキュリティ保護可能なスコープ: サーバー  
 **サーバー** セキュリティ保護可能なスコープには、次のセキュリティ保護可能なリソースが含まれています。  
  
-   可用性グループ  
  
-   エンドポイント  
  
-   ログイン  
  
-   サーバー ロール  
  
-   データベース  
  
## <a name="securable-scope-database"></a>セキュリティ保護可能なスコープ: データベース  
 **データベース** セキュリティ保護可能なスコープには、次のセキュリティ保護可能なリソースが含まれています。  
  
-   アプリケーション ロール  
  
-   アセンブリ  
  
-   非対称キー  
  
-   Certificate  
  
-   コントラクト  
  
-   フルテキスト カタログ  
  
-   フルテキスト ストップリスト  
  
-   メッセージ型  
  
-   リモート サービス バインド  
  
-   (データベース) ロール  
  
-   ルート  
  
-   スキーマ  
  
-   検索プロパティ リスト  
  
-   サービス  
  
-   対称キー  
  
-   User  
  
## <a name="securable-scope-schema"></a>セキュリティ保護可能なスコープ: スキーマ  
 **スキーマ** セキュリティ保護可能なスコープには、次のセキュリティ保護可能なリソースが含まれています。  
  
-   種類  
  
-   XML スキーマ コレクション  
  
-   オブジェクト - オブジェクト クラスのメンバーは次のとおりです。  
  
    -   Aggregate  
  
    -   Function  
  
    -   手順  
  
    -   キュー  
  
    -   シノニム  
  
    -   テーブル  
  
    -   表示  
  
## <a name="controlling-access-to-a-securable"></a>セキュリティ保護可能なものへのアクセスの制御  
 セキュリティ保護可能なものに対する権限を受け取るエンティティは、プリンシパルと呼ばれます。 最も一般的なプリンシパルは、ログインとデータベース ユーザーです。 セキュリティ保護可能なものへのアクセスは、権限を許可または拒否することや、アクセスが可能なロールにログインおよびユーザーを追加することによって制御されます。 アクセス許可を制御する方法の詳細については、「[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)」、「[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql)」、「[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql)」、「[sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)」および「[sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql)」を参照してください。  
  
> [!CAUTION]  
>  セットアップ時にシステム オブジェクトに付与された既定のアクセス許可は、発生する可能性のある脅威に対して慎重に評価されているため、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] のインストールの際、セキュリティ強化の一部として変更する必要はありません。 システム オブジェクトのアクセス許可の変更はどのようなものであっても、機能を制限または中断する可能性があり、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] のインストールがサポートされていない状態のままになる場合があります。  
  
## <a name="related-content"></a>関連コンテンツ  
 [SQL Server の保護](securing-sql-server.md)  
  
 [database_principals &#40;Transact-sql&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [database_role_members &#40;Transact-sql&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [server_principals &#40;Transact-sql&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [server_role_members &#40;Transact-sql&#41;](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [sql_logins &#40;Transact-sql&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
