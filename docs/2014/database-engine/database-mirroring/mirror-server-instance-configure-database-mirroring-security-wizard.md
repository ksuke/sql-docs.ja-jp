---
title: '[ミラー サーバー インスタンス] (データベース ミラーリング セキュリティ構成ウィザード) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 83a92633a4c466e72c8cc2de0cc1c220e88e01bb
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62755161"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a>[ミラー サーバー インスタンス] (データベース ミラーリング セキュリティ構成ウィザード)
  このページを使用すると、ミラー データベースを持つサーバー インスタンスに関する情報を指定できます。  
  
> [!IMPORTANT]  
>  ミラー サーバー インスタンスでは、プリンシパル サーバー インスタンスと同じ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のエディション (Standard または Enterprise) を実行している必要があります。 また、ワークロードの処理能力が同程度のシステム上で運用することを強くお勧めします。  
  
 **SQL Server Management Studio を使用してデータベースミラーリングを構成するには**  
  
-   [Windows 認証 &#40;SQL Server Management Studio を使用してデータベースミラーリングセッションを確立&#41;](establish-database-mirroring-session-windows-authentication.md)  
  
-   [データベースミラーリングセキュリティ構成ウィザード &#40;SQL Server Management Studio を開始し&#41;](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a>オプション  
 **ミラーサーバーインスタンス**  
 
  **[データベースのプロパティ]** ダイアログ ボックスの **[ミラー化]** ページで、ミラー サーバー インスタンスが既に指定されている場合、そのインスタンスが表示されます。詳細については、「[[データベースのプロパティ] &#40;[ミラーリング] ページ&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)」を参照してください。  
  
 まだ指定されていない場合は、ミラー サーバー インスタンスの名前を入力します。 プリンシパル サーバー インスタンスと同じ名前をミラー サーバー インスタンスに指定しないように注意してください。  
  
 **接続する**  
 ミラー サーバー インスタンスが指定されていない場合、 **[接続]** をクリックします。 
  **[サーバーへの接続]** ダイアログ ボックスが表示されます。ここでサーバー インスタンスを指定し、接続を確立できます。  
  
 インスタンスが指定されていても、エンドポイントが存在するかどうかをチェックできる権限を持つ接続がない場合には、 **[接続]** をクリックします。 
  **[サーバーへの接続]** ダイアログ ボックスが表示されます。この場合、サーバー インスタンスは選択されており、変更できません。 十分な権限を持つドメイン アカウントを指定して、サーバー インスタンスに接続します。  
  
> [!NOTE]  
>  データベース ミラーリング セキュリティ構成ウィザードは、 **[サーバーへの接続]** ダイアログ ボックスで指定された資格情報を使ってサーバー インスタンスに接続します。 これらは、ミラーリング セッションの資格情報とは異なります。ミラーリング セッションでは、サーバー インスタンスをサービスとして実行している開始アカウントの資格情報が使用されます。  
  
 **リスナーポート**  
 このオプションでは、このサーバー インスタンスに対するミラーリング エンドポイントが存在するかどうかに応じて、次のような内容が表示されます。  
  
-   サーバー インスタンスに対するリスナー ポートが存在しない場合、 **[リスナー ポート]** テキスト ボックスにポート番号 5022 が表示されます。 使用可能な任意のポート番号を入力できます (7022 など)。  
  
-   ミラーリング エンドポイントが既に存在する場合、そのエンドポイントからのポート番号が表示されます。 ポートを変更する必要がある場合は、ALTER ENDPOINT コマンドを使用します。 詳細については、「 [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql)」を参照してください。  
  
    > [!NOTE]  
    >  ポート番号は必須です。  
  
 **エンドポイント名**  
 このサーバー インスタンスのミラーリング エンドポイントが存在する場合、ここにエンドポイント名が表示されます。 エンドポイントが存在しない場合には、エンドポイントの名前を指定できます。  
  
 **このエンドポイント経由で送信されるデータを暗号化する**  
 既定で、暗号化は有効になっています。 暗号化が有効な場合、暗号化は必須です (サポートされるだけではありません)。暗号化オプションにはすべて既定値が使用されます。 詳細については、「[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql)」を参照してください。  
  
 暗号化を無効にするには、チェック ボックスをオフにします。 暗号化を再度有効にするには、チェック ボックスをオンにします。  
  
## <a name="see-also"></a>参照  
 [データベースミラーリングエンドポイント &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md)   
 [[データベースのプロパティ] &#40;[ミラーリング] ページ&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Windows 認証 &#40;Transact-sql&#41;のデータベースミラーリングエンドポイントを作成する](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)   
 [&#40;SQL Server Management Studio を開始データベースミラーリングモニター&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)   
 [データベースミラーリング &#40;SQL Server&#41;](database-mirroring-sql-server.md)  
  
  
