---
title: 一度に単一のイベントを再生する
titleSuffix: (SQL Server Profiler
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.openlocfilehash: e8f217e2117e22edbd5f763b71c51cb078d49301
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "75307515"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a>一度に単一のイベントの再生 (SQL Server Profiler)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

このトピックでは、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]を使用して、再生トレース ファイルまたはテーブルで一度に単一のイベントを再生する方法を説明します。  
  
### <a name="to-replay-a-single-event-at-a-time"></a>一度に単一のイベントを再生するには  
  
1.  再生するトレース ファイルまたはトレース テーブルを開きます。 詳細については、「 [トレース ファイルを開く &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) や [トレース テーブルを開く &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)に付属の定義済みチューニング テンプレートを使用します。  
  
     開いたトレース ファイルまたはトレース テーブルに、再生に必要なイベント クラスが含まれていることを確認します。 詳細については、「 [再生を実行するための必要条件](../../tools/sql-server-profiler/replay-requirements.md)」を参照してください。  
  
2.  **[再生]** メニューの **[ステップ実行]** をクリックし、トレースを再生するサーバー インスタンスに接続します。  
  
3.  **[構成の再生]** ダイアログ ボックスで設定を確認し、 **[OK]** をクリックします。 **[構成の再生]** ダイアログ ボックスで設定内容を指定する方法の詳細については、「[トレース ファイルの再生 &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)」または「[トレース テーブルの再生 &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)」を参照してください。  
  
4.  最初のイベントを再生するには、 **[構成の再生]** ダイアログ ボックスで **[OK]** をクリックします。  
  
5.  後続のイベントを再生するには、 **[再生]** メニューの **[ステップ実行]** をクリックするか、F10 キーを押します。 各イベントに対して **[ステップ実行]** をクリックするか、または F10 キーを押す操作を繰り返します。  
  
## <a name="see-also"></a>参照  
 [トレースの再生](../../tools/sql-server-profiler/replay-traces.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
