---
title: '[不明なサービス] ([ログオン] タブ) |Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 686eb039660efb6e3596b9dac88fc0d24deacaee
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63150527"
---
# <a name="unknown-service-log-on-tab"></a>[不明なサービス] ダイアログ ボックス ([ログオン] タブ)
  [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager がこのサービスを識別できません。  
  
 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 構成マネージャーは、サービスを実行しているコンピューターの WMI プロバイダーからそのサービスの情報を受け取ります。 そのサービスのプロパティの読み取り中にエラーが発生したか、そのサービスのプロパティに不備がありました。 この問題を解決するには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 構成マネージャーをいったん閉じてから再び開くか、そのサービスを実行しているコンピューターの WMI プロバイダーをチェックします。  
  
 WMI プロバイダーは、Windows のコンポーネントです。 WMI プロバイダーの権限をチェックする方法については、SQL Server オンライン ブックの「SQL Server ツールでサーバーの状態を表示できるように WMI を構成する方法」を参照してください。  
  
 適切なサービスを表示していると確信できる場合は、 **[不明なサービス]** ダイアログ ボックスの **[ログオン]** タブで、そのサービスが使用するアカウントの指定や、そのサービスの開始と停止を行います。  
  
## <a name="options"></a>オプション  
 **ローカルシステムアカウント**  
 ローカル システム アカウントを指定します。このアカウントはパスワードを必要としません。 ただし、ローカル システム アカウントに与えられている特権によっては、そのサービスが他のサーバーと対話できないこともあります。  
  
 **このアカウント**  
 Windows 認証を使用するローカル ユーザー アカウントまたはドメイン ユーザー アカウントを指定します。 サービスを実行できる必要最小限の権限が設定されたドメイン ユーザー アカウントを使用することをお勧めします。 アカウントの選択の詳細については、オンライン ブックの「Windows サービス アカウントの設定」を参照してください。  
  
 **アカウント名**  
 ローカル ユーザー アカウント名またはドメイン ユーザー アカウント名を指定します。  
  
 **パスワード**  
 アカウントのパスワードを入力します。  
  
 **[パスワードの確認入力]**  
 アカウントのパスワードを再度入力します。  
  
 **[開始]**  
 サービスを開始します。  
  
 **停止**  
 サービスを停止します。  
  
 **停止**  
 サービスを一時停止します。  
  
 **よる**  
 一時停止したサービスを再開します。  
  
  
