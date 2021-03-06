---
title: '[更新可能なサブスクリプション] のログイン | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: d8162c7654d99cd2ebab41d290c0a39c6c686686
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63058098"
---
# <a name="login-for-updatable-subscriptions"></a>[更新可能なサブスクリプション] のログイン
  このウィザードの **[更新可能なサブスクリプション]** ページで **[レプリケート]** を選択した場合は、サブスクリプションを即時更新するためにパブリッシャーに接続する際に使用する、サブスクライバーでのアカウントを指定する必要があります。 接続はサブスクライバーで起動されるトリガーによって使用され、サブスクライバーに変更を反映します。 このアカウントは、 **[更新可能なサブスクリプション]** ページで **[変更をキューに登録し、可能な場合はコミット]** を選択している場合でも必要です。サブスクリプションの新規作成ウィザードでは、必要に応じて即時更新に切り替えることができるキュー更新が、既定で構成されるためです。  
  
> [!IMPORTANT]  
>  接続用に指定するアカウントには、レプリケーションによってパブリケーション データベース内に作成されるビューのデータの挿入、更新、および削除だけを実行できる権限を与える必要があります。それ以外の権限は与えないでください。 各サブスクライバーで構成したアカウントに、 **syncobj_**_\<hexadecimalnumber>>_ の形式で名前が付けられたパブリケーションデータベースのビューに対する権限を許可します。  
  
 接続の種類として、3 つのオプションがあります。  
  
-   定義済みのリンク サーバーまたはリモート サーバー。  
  
-   レプリケーションによって作成されるリンク サーバー。このウィザードで指定した資格情報を使用して接続を行います。  
  
-   レプリケーションによって作成されるリンク サーバー。サブスクライバーで変更を行うユーザーの資格情報を使用して接続を行います。  
  
 最初の 2 つのオプションは、このウィザードで指定できます。 最後のオプションは、 [sp_link_publication &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql)を使用した場合にのみ指定できます。パラメーター **@security_mode**に値**1**を指定します。  
  
## <a name="options"></a>オプション  
 **次の SQL Server 認証ログインを使用して接続するリンクサーバーを作成します。**  
 レプリケーションにより、 **[ログイン]** フィールドおよび **[パスワード]** フィールドに指定された資格情報に基づいてリンク サーバーが作成されます。  
  
 **Login**  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]このトピックで説明されているアクセス許可のみを持つログインを入力します。  
  
 **パスワード**  
 
  **[ログイン]** に指定したログインに使用する複雑なパスワードを入力します。  
  
 **パスワードの確認入力**  
 パスワードが正常に入力されていることを確認するために、パスワードを再入力します。  
  
 **定義済みのリンクサーバーまたはリモートサーバーを使用します。**  
 このオプションを使用するには、定義済みのリンク サーバーまたはリモート サーバーが必要です。 詳細については、「[リンク サーバー &#40;データベース エンジン&#41;](../linked-servers/linked-servers-database-engine.md)」および「[リモート サーバー](../../database-engine/configure-windows/remote-servers.md)」を参照してください。 リンク サーバーまたはリモート サーバーに使用するログインに対して複雑なパスワードが設定されていて、このトピックに記載された権限だけが設定されていることを確認してください。  
  
## <a name="see-also"></a>参照  
 [トランザクションパブリケーションに対する更新可能なサブスクリプションの作成](publish/create-an-updatable-subscription-to-a-transactional-publication.md)   
 [レプリケーションのセキュリティ設定を表示および変更する](security/view-and-modify-replication-security-settings.md)   
 [トランザクションレプリケーションの更新可能なサブスクリプション](transactional/updatable-subscriptions-for-transactional-replication.md)   
 [パブリケーションのサブスクライブ](subscribe-to-publications.md)  
  
  
