---
title: パフォーマンス監視およびチューニング ツール | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tools [SQL Server], monitoring performance
- monitoring server performance [SQL Server], tools
- monitoring performance [SQL Server], tools
- database performance [SQL Server], tools
- tuning databases [SQL Server], tools
- database monitoring [SQL Server], tools
- performance [SQL Server], monitoring tools
- server performance [SQL Server], tools
ms.assetid: 31529dfe-68e7-49f7-b3c2-39fcecf33a95
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 179944412ed72bc0055bf5c47b788a3a929e9844
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63150842"
---
# <a name="performance-monitoring-and-tuning-tools"></a>パフォーマンス監視およびチューニング ツール
  [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]には、の[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]イベントを監視し、物理データベースデザインをチューニングするための包括的なツールセットが用意されています。 どのツールを選択するかは、実行する監視またはチューニングの種類や、監視するイベントによって異なります。  
  
 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の監視およびチューニング用のツールは次のとおりです。  
  
|ツール|[説明]|  
|----------|-----------------|  
|[sp_trace_setfilter &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|
  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] では、バッチまたはトランザクションの開始などのエンジン プロセス イベントが追跡され、サーバーおよびデータベースの利用状況 (デッドロック、致命的なエラー、ログインの利用状況など) を監視できます。 
  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] のデータを [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] テーブルまたはファイルにキャプチャして、後で分析できます。また、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] でキャプチャしたイベントをステップごとに再生して、何が起こったかを正確に確認することもできます。|  
|[SQL Server Distributed Replay](../../tools/distributed-replay/sql-server-distributed-replay.md)|[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]分散再生は、複数のコンピューターを使用してトレースデータを再生し、ミッションクリティカルなワークロードをシミュレートできます。|  
|[リソース使用状況の監視 &#40;システムモニタ&#41;](../performance-monitor/monitor-resource-usage-system-monitor.md)|システム モニターでは、使用中のバッファー マネージャー ページ要求の数などのリソース使用量が主に追跡され、イベントを監視するための定義済みオブジェクトおよびカウンターやユーザー定義カウンターを使用して、サーバーのパフォーマンスおよび利用状況を監視できます。 システム モニター (Microsoft Windows NT 4.0 の場合はパフォーマンス モニター) は、イベントに関するデータではなく、メモリの使用量、アクティブなトランザクションの数、ブロックされたロックの数、CPU の利用状況など、イベントの数と比率を収集します。 特定のカウンターにしきい値を設定して、オペレーターに通知する警告を生成できます。<br /><br /> システム モニターは Microsoft Windows Server および Windows オペレーティング システムで機能します。 システム モニターでは、Windows NT 4.0 以降で実行されている [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスをリモートまたはローカルで監視できます。<br /><br /> 
  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] とシステム モニターの重要な違いは、 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] ではデータベース エンジンのイベントが監視されるのに対し、システム モニターではサーバー プロセスに関連したリソース使用量が監視されることです。|  
|[利用状況モニターを開く方法 &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] の利用状況モニターは、現在のアクティビティのカスタム ビューの場合に便利であり、次の情報をグラフィカルに表示します。<br /><br /> 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のインスタンスで実行中のプロセス<br /><br /> ブロックされているプロセス<br /><br /> ロック<br /><br /> ユーザーの利用状況|  
|[SQL トレース (SQL Trace)](../sql-trace/sql-trace.md)|
  [!INCLUDE[tsql](../../../includes/tsql-md.md)] ストアド プロシージャは次のとおりです。<br /><br /> [sp_trace_create &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)<br /><br /> [sp_trace_generateevent &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)<br /><br /> [sp_trace_setevent &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)<br /><br /> [sp_trace_setfilter &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)<br /><br /> [sp_trace_setstatus &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|  
|エラー ログ|Windows アプリケーション イベント ログでは、Windows Server と Windows オペレーティング システム全体で発生しているイベントと、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント、およびフルテキスト検索で発生しているイベントの全般的な概要が示されます。 他のツールでは提供されない [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のイベントに関する情報が含まれています。 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]に関連する問題のトラブルシューティングでエラー ログの情報を使用できます。|  
|[システムストアドプロシージャ &#40;Transact-sql&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)|次の [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] システム ストアド プロシージャでは、多くの監視タスクの強力な代替方法が提供されています。<br /><br /> [sp_who &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-who-transact-sql): <br />                    このシステム ストアド プロシージャは、現在実行中のステートメントとそのステートメントがブロックされているかどうかなど、現在の [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーザーおよびプロセスに関するスナップショット情報を報告します。<br /><br /> [sp_lock &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-lock-transact-sql): オブジェクト ID、インデックス ID、ロックの種類、ロックを適用する種類またはリソースなど、ロックに関するスナップショット情報を報告します。<br /><br /> [sp_spaceused &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql): テーブル (またはデータベース全体) によって使用されている現在のディスク領域の推定値が表示されます。<br /><br /> [sp_monitor &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-monitor-transact-sql): CPU 使用率、i/o 使用率、 **sp_monitor**最後に実行されてからのアイドル時間などの統計情報が表示されます。|  
|[DBCC &#40;Transact-sql&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql)|DBCC (データベース コンソール コマンド) ステートメントによって、パフォーマンス統計とデータベースの論理的および物理的一貫性を確認できます。|  
|[組み込み関数 &#40;Transact-SQL&#41;](/sql/t-sql/functions/functions)|組み込み関数では、サーバーが起動してからの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の利用状況に関するスナップショット統計が表示されます。この統計は、あらかじめ定義された [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] カウンターに格納されます。 たとえば、 **@@CPU_BUSY **には、CPU がコードを実行[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]していた時間が含まれます。**@@CONNECTIONS **には、接続[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]または試行した接続の数が含まれます。および **@@PACKET_ERRORS **には、接続で[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]発生しているネットワークパケットの数が含まれています。|  
|[Transact-sql&#41;&#40;トレースフラグ](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)|トレース フラグでは、サーバー内の特定の利用状況に関する情報が示されます。このトレース フラグを使用して、問題やデッドロック チェーンなどのパフォーマンスの問題を診断します。|  
|[Database Engine Tuning Advisor](database-engine-tuning-advisor.md)|データベース エンジン チューニング アドバイザーでは、チューニングするデータベースに対して実行した [!INCLUDE[tsql](../../../includes/tsql-md.md)] ステートメントのパフォーマンス効果が分析されます。 データベース エンジン チューニング アドバイザーでは、インデックス、インデックス付きビュー、およびパーティションを追加、削除、または変更するための推奨設定が提供されます。|  
  
## <a name="choosing-a-monitoring-tool"></a>監視ツールの選択  
 どの監視ツールを使用するかは、監視対象のイベントまたは利用状況によって決まります。  
  
|イベントまたは利用状況|SQL Server プロファイラー|Distributed Replay|システム モニター|利用状況モニター|Transact-SQL|エラー ログ|  
|-----------------------|-------------------------|------------------------|--------------------|----------------------|-------------------|----------------|  
|傾向分析|はい||はい||||  
|キャプチャしたイベントの再生|可 (1 台のコンピューターから)|可 (複数のコンピューターから)|||||  
|アドホック監視|はい|||はい|はい|はい|  
|警告の生成|||はい||||  
|グラフィカル インターフェイス|はい||はい|はい||はい|  
|カスタム アプリケーション内での使用|はい <sup>1</sup>||||はい||  
  
 <sup>1</sup>システム[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)]ストアドプロシージャを使用します。  
  
## <a name="windows-monitoring-tools"></a>Windows 監視ツール  
 Windows オペレーティング システムおよび Windows Server 2003 では、次の監視ツールが提供されています。  
  
|ツール|[説明]|  
|----------|-----------------|  
|タスク マネージャー|システム上で実行中のプロセスやアプリケーションの概要を示します。|  
|ネットワーク モニター エージェント|ネットワーク トラフィックを監視します。|  
  
 Windows オペレーティング システムまたは Windows Server ツールの詳細については、Windows のマニュアルを参照してください。  
  
  
