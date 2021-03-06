---
title: パブリケーション情報、[すべてのサブスクリプション](スナップショット パブリケーション) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.snapshot.f1
ms.assetid: 7ce656c2-6e60-4625-8955-1daff641070c
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 3665647e89c03b75230acf58d2f5193fceefe878
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63021827"
---
# <a name="publication-information-all-subscriptions-snapshot-publication"></a>パブリケーション情報、[すべてのサブスクリプション] (スナップショット パブリケーション)
  
  **[すべてのサブスクリプション]** タブには、選択したスナップショット パブリケーションに対するすべてのサブスクリプションの情報が表示されます。  
  
## <a name="options"></a>オプション  
 サブスクリプションに関する詳細情報やタスクを調べるには、そのサブスクリプションの行を右クリックし、ショートカット メニューのオプションをクリックします。 グリッドにデータを表示する方法を変更するには、グリッドを右クリックし、次のいずれかのオプションをクリックします。  
  
-   **Sort**: [**列の並べ替え**] ダイアログボックス内の1つまたは複数の列を基準にして並べ替えを行います。  
  
-   表示**する列の選択**: 表示する列と、[**列の選択**] ダイアログボックスで表示する順序を選択します。  
  
-   [**フィルター**]: [**フィルターの設定**] ダイアログボックスの列の値に基づいて、グリッド内の行をフィルター処理します。  
  
-   [**フィルターのクリア**]: グリッドのフィルター設定をすべてクリアします。  
  
 フィルター設定は各グリッドに固有です。 列の選択と並べ替えは、各パブリッシャーのパブリケーション グリッドなど、同じ種類のすべてのグリッドに適用されます。  
  
 **示**  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]以降のバージョンのみ。 サブスクリプション状態を選択すると、選択した種類の状態のサブスクリプションが表示されます。 たとえば、エラーを含むサブスクリプションのみを表示するように設定できます。  
  
 **状態**  
 各サブスクリプションの状態です。スナップショット エージェントまたはディストリビューション エージェントの状態 (より高い優先度の状態が表示されます) によって決定されます。  
  
 既定では、サブスクリプション情報を表示するグリッドは **[状態]** 列の順序で並べられています。 表示される状態の値と、その値の並べ替え順 (たとえば、エラーは常にグリッドの上部に表示されます) を次に示します。  
  
-   エラー  
  
-   [まもなく期限切れ/期限切れ]\([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 以降のバージョンのみ)  
  
-   [初期化されていないサブスクリプション]\([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 以降のバージョンのみ)  
  
-   [失敗したコマンドの再試行]  
  
-   [同期中]  
  
-   [同期されていません]  
  
 特定のサブスクリプションが複数の状態である場合に表示される値も、並べ替え順によって決まります。 たとえば、サブスクリプションにエラーがあり、まもなく期限切れになる場合、 **[状態]** 列には **[エラー]** と表示されます。  
  
 状態値 **[まもなく期限切れ/期限切れ]** および **[初期化されていないサブスクリプション]** は警告です。 警告が表示される場合、 **[状態]** 列にはエージェントが実行中かどうかも表示されます。 たとえば、 **[実行中]、[まもなく期限切れ/期限切れ]** という形式で状態が表示されます。  
  
 状態値 **[まもなく期限切れ/期限切れ]** は、しきい値が設定されている場合のみ表示されます。 しきい値の設定方法の詳細については、「[レプリケーション モニターのしきい値と警告の設定](monitor/set-thresholds-and-warnings-in-replication-monitor.md)」を参照してください。  
  
 **サブスクリプション**  
 各サブスクリプションの名前です。 *SubscriberName: SubscriptionDatabaseName*という形式になります。  
  
 **前回の同期**  
 ディストリビューション エージェントが最後に実行された時刻です。 同期が進行中の場合は、 **[実行中]** と表示されます。  
  
## <a name="see-also"></a>参照  
 [レプリケーション モニターの開始](monitor/start-the-replication-monitor.md)   
 [レプリケーションモニターを使用して情報を表示し、タスクを実行する](monitor/view-information-and-perform-tasks-replication-monitor.md)   
 [レプリケーションの監視](monitoring-replication.md)  
  
  
