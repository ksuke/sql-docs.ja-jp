---
title: Audit Logout イベント クラス | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Logout event class
ms.assetid: 16a0178c-ca03-4078-bbdd-f481385fa2f1
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: e8c7c2f178391b93b1034d3e1bfb07ff9f7714ed
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63012572"
---
# <a name="audit-logout-event-class"></a>Audit Logout イベント クラス
  **Audit Logout**イベントクラスは、ユーザーがログアウト (ログオフ) [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]したことを示します。 このクラスのイベントは、新しい接続によって生じることも、接続プールから再利用された接続によって生じることもあります。  
  
## <a name="audit-logout-event-class-data-columns"></a>Audit Logout イベント クラスのデータ列  
  
|データ列名|データ型|[説明]|列 ID|フィルターの適用|  
|----------------------|---------------|-----------------|---------------|----------------|  
|**ApplicationName**|**nvarchar**|
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のインスタンスへの接続を作成したクライアント アプリケーションの名前。 この列には、プログラムの表示名ではなく、アプリケーションによって渡された値が格納されます。|10|はい|  
|**ClientProcessID**|**int**|クライアント アプリケーションが実行されているプロセスに対し、ホスト コンピューターが割り当てた ID。 クライアントでクライアント プロセス ID が指定されると、このデータ列が作成されます。|9|はい|  
|**CPU**|**int**|接続時にユーザーが使用した CPU 時間 (ミリ秒) です。|18|はい|  
|**DatabaseID**|**int**|USE *database*ステートメントで指定されたデータベースの ID、または特定のインスタンスに対して use *database*ステートメントが発行されていない場合は既定のデータベースの ID となります。 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]では、 **ServerName**データ列がトレースにキャプチャされ、そのサーバーが使用可能な場合、データベースの名前が表示されます。 データベースに対応する値は、DB_ID 関数を使用して特定します。|3|はい|  
|**DatabaseName**|**nvarchar**|ユーザーのステートメントが実行されているデータベースの名前。|35|はい|  
|**Duration**|**bigint**|ユーザーがログインしてからの時間 (概算) です。|13|はい|  
|**EndTime**|**DATETIME**|ログアウトの終了時刻です。|15|はい|  
|**EventClass**|**int**|イベントの種類 = 15。|27|いいえ|  
|**EventSequence**|**int**|要求内の特定のイベントのシーケンス。|51|いいえ|  
|**EventSubClass**|**int**|ログインに使用される接続の種類。 1 = プールされていない。2 = プールされた。|21|はい|  
|**名**|**nvarchar**|クライアントが実行されているコンピューターの名前。 このデータ列には、クライアントがホスト名を指定している場合にデータが格納されます。 ホスト名を指定するには、HOST_NAME 関数を使用します。|8|はい|  
|**Issystem で**|**int**|イベントがシステム プロセスとユーザー プロセスのどちらで発生したか。 1 はシステム、0 はユーザーです。|60|はい|  
|**ログイン**|**nvarchar**|ユーザーのログイン名 ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] セキュリティ ログイン、または DOMAIN\username の形式で表された [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ログイン資格情報)。|11|はい|  
|**LoginSid**|**絵**|ログイン ユーザーのセキュリティ ID 番号 (SID)。 この情報は、 **sys.server_principals** カタログ ビューで参照できます。 各 SID はサーバーのログインごとに一意です。|41|はい|  
|**NTDomainName**|**nvarchar**|ユーザーが所属する Windows ドメイン。|7|はい|  
|**NTUserName**|**nvarchar**|Windows のユーザー名。|6|はい|  
|**読み取り**|**bigint**|接続時にユーザーが実行した論理読み取り I/O の数です。|16|はい|  
|**RequestID**|**int**|ステートメントが含まれている要求の ID。|49|はい|  
|**Server**|**nvarchar**|トレースされている [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスの名前。|26||  
|**SessionLoginName**|**Nvarchar**|セッションを開始したユーザーのログイン名。 たとえば、Login1 を使用して[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]に接続し、Login2 としてステートメントを実行すると、 **Sessionloginは**Login1 と**loginLogin2**を表示します。 この列には、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ログインと Windows ログインの両方が表示されます。|64|はい|  
|**調べる**|**int**|イベントが発生したセッションの ID。|12|はい|  
|**StartTime**|**DATETIME**|イベントの開始時刻 (取得できた場合)。|14|はい|  
|**成功**|**int**|1 = 成功。 0 = 失敗。 たとえば、値 1 は権限チェックの成功を示し、値 0 は失敗を示します。|23|はい|  
|**書き込み**|**bigint**|接続時にユーザーが実行した論理書き込み I/O の数です。|17|はい|  
|**GroupID**|**int**|SQL トレース イベントが発生したワークロード グループの ID。|66|はい|  
  
## <a name="see-also"></a>参照  
 [sp_trace_setevent &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
