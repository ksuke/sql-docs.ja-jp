---
title: コマンドプロンプトからのアップグレードアドバイザーのインストール |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4b694af5b760ae3c1ead1e4984c35ef61c0fa602
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66094336"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a>コマンド プロンプトからのアップグレード アドバイザーのインストール
  アップグレード アドバイザーをインストールするには、セットアップ ウィザードを使用する方法と、コマンド プロンプトを使用する方法があります。 コマンド プロンプトを使用すると、自動インストールを実行できます。  
  
## <a name="installation-syntax"></a>インストールの構文  
 コマンド プロンプトからのアップグレード アドバイザーのインストールに使用する基本構文は、次のとおりです。  
  
 `SQLUA.msi [options]`  
  
 次の表では、最も一般的なオプションを示します。  
  
|引数|[説明]|  
|--------------|-----------------|  
|/q [n&#124;b&#124;r&#124;f]|ユーザー インターフェイス (UI) レベルの設定:<br /><br /> n = UI なし<br /><br /> b = 基本 UI (進行状況のみ、プロンプトなし)<br /><br /> r = 一部 UI (インストール終了時のダイアログ ボックス)<br /><br /> f = 完全 UI|  
|/L|ログ ファイル オプションを指定します。 すべてのメッセージを*log_file_name*に記録するには、 **-\*L v**_log_file_name_を使用します。 エラーメッセージのみを記録するに`-Le`は、 *log_file_name*を使用します。|  
|ADDLOCAL = ALL&#124; REMOVE = ALL&#124;REINSTALL = ALL|アップグレード アドバイザーのインストール (ADDLOCAL)、削除 (REMOVE)、または再インストール (REINSTALL) を実行するように指定します。|  
|UAINSTALLDIR=path|アップグレード アドバイザーをパスで指定した場所にインストールします。|  
  
## <a name="installation-examples"></a>インストール例  
 次の例は、コマンド プロンプトを使用してアップグレード アドバイザーをインストールする方法を示します。  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 このコマンドの実行時に、Msiexec プログラムを使用することもできます。  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 これは、追加インストール オプションを使用する必要がある場合に役立ちます。  
  
## <a name="removal-examples"></a>削除例  
 次の例は、コマンド プロンプトを使用してアップグレード アドバイザーを削除する方法を示します。  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 このコマンドの実行時に、Msiexec プログラムを使用することもできます。  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a>参照  
 [アップグレードアドバイザーをインストールしています](../../../2014/sql-server/install/installing-upgrade-advisor.md)   
 [アップグレード アドバイザーの前提条件](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
