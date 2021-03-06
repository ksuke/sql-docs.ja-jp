---
title: '[接続プロパティ] ダイアログ ボックス | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectionproperties.f1
helpviewer_keywords:
- Connection Properties dialog box
ms.assetid: 6df812ad-4d80-4503-8a23-47719ce85624
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 350e48c225814052655e4fced89d2f934efa188f
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62808400"
---
# <a name="connection-properties-dialog-box"></a>[接続プロパティ] ダイアログ ボックス
  このダイアログ ボックスを使用すると、現在の接続プロパティを表示できます。 このダイアログ ボックスは、オブジェクト エクスプローラーの各種のダイアログ ボックスで **[接続のプロパティを表示します]** をクリックすると表示されます。 このページに表示されるプロパティは読み取り専用です。  
  
 
  **[データベース]** などのプロパティを変更するには、オブジェクト エクスプローラーを使用して目的のデータベースに接続してから、 **[接続プロパティ]** ダイアログ ボックスを開きます。  
  
 SQL Azure のクエリ タイムアウト期間は 30 分であることに注意してください。  
  
## <a name="authentication"></a>認証  
 現在の接続の認証プロパティを表示します。 認証プロパティとは、接続が確立されたときのログインと認証方法です。 認証プロパティを変更するには、 [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]から切断してから、目的の接続オプションを使用してオブジェクトエクスプローラーサーバーにもう一度接続します。  
  
 **認証方法**  
 現在の接続に使用された認証方法。  
  
 **ユーザー名**  
 接続認証に使用されたログインのユーザーの名前。  
  
## <a name="connection-category"></a>[接続] カテゴリ  
 現在の接続の接続プロパティを表示します。 ほとんどの接続プロパティは、接続プロセス中に **[サーバーへの接続]** ダイアログ ボックスの **[接続プロパティ]** タブで選択されます。  
  
 **[データベース]**  
 現在接続されているデータベースの名前。 この値を変更するには、SQL エディター ツール バーを使用します。  
  
 **調べる**  
 サーバーから接続に割り当てられているシステム プロセス ID。 この接続に対してこの値を変更することはできません。  
  
 **ネットワークプロトコル**  
 
  [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] 接続のネットワーク プロトコル。 この値を変更するには、適切な接続プロパティを使用して接続し直します。  
  
 **ネットワークパケットサイズ**  
 サーバーとの通信に使用されるパケット サイズ。 この値を変更するには、適切な接続プロパティを使用して接続し直します。  
  
 **[接続タイムアウト]**  
 
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] への接続を待つ秒数。この時間が経過すると、タイムアウトが発生し、接続失敗エラーがユーザーに返されます。 この値を変更するには、適切な接続プロパティを使用して接続し直します。  
  
 **実行タイムアウト**  
 サーバー上でタスクの実行が完了するまで待つ秒数。 この値を変更するには、適切な接続プロパティを使用して接続し直します。  
  
 **暗号化**  
 現在の接続が暗号化されるかどうかを示します。 この値を変更するには、適切な接続プロパティを使用して接続し直します。  
  
## <a name="product-category"></a>製品カテゴリ  
 現在の接続の製品プロパティを表示します。 これらのプロパティは、サーバー製品、バージョン、インスタンス名、および照合順序を記述します。 これらのプロパティは、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] のインストール時に設定します。  
  
 **製品名**  
 
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] の製品名。  
  
 **製品バージョン**  
 
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] の製品バージョン。  
  
 **サーバー名**  
 
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]を実行しているコンピューターの名前。  
  
 **インスタンス名**  
 サーバーのインスタンス名。 既定のインスタンスは空白です。  
  
 **Language**  
 
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 製品の言語バージョン。  
  
 **Collation**  
 サーバーの照合順序。  
  
## <a name="server-environment-category"></a>[サーバー環境] カテゴリ  
 サーバーのハードウェアおよびオペレーティング システムに関係する、現在の接続のサーバー環境プロパティを表示します。 これらのプロパティは、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]では構成できません。  
  
 **コンピューター名**  
 
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]を実行しているサーバー コンピューターの名前。  
  
 **プラットフォーム**  
 サーバーのオペレーティング システム名、メーカー名、および CPU ファミリ。  
  
 **オペレーティング システム**  
 サーバーにインストールされている [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows バージョン。  
  
 **状況**  
 サーバーに搭載されているプロセッサの数。  
  
 **オペレーティングシステムのメモリ**  
 サーバーに搭載されている物理メモリの合計 (MB 単位)。  
  
## <a name="see-also"></a>参照  
 [SQL Server Management Studio のプロパティページ](../ssms/property-pages-in-sql-server-management-studio.md)   
 [サーバーへの接続 &#40;ログインページ&#41; データベースエンジン](../ssms/f1-help/connect-to-server-login-page-database-engine.md)  
  
  
