---
title: レポートとサブスクリプションの処理を一時停止する |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66100922"
---
# <a name="pause-report-and-subscription-processing"></a>レポートとサブスクリプションの処理を一時停止する
  レポートまたはサブスクリプションを直接一時停止することはできません。 ただし、処理の開始前、またはデータ ソースへの接続時に、レポートおよびサブスクリプションの処理を中断できます。 また、レポートやサブスクリプションにユーザーがアクセスできないようにして、レポートやサブスクリプションが処理されないようにすることもできます。  
  
 以下の操作は、一時的な処理の中断に使用できます。  
  
## <a name="modify-role-assignments-to-prevent-access"></a>アクセス防止のためのロールの割り当ての変更  
 レポートを使用できないようにする最善の方法は、レポートにアクセスするためのロールの割り当てを一時的に削除することです。 この方法は、データ ソースへの接続方法に関係なくすべてのレポートに使用できます。 この方法は、ロールの割り当てを一時的に削除したレポートのみに有効で、他のレポートやアイテムの操作には影響しません。  
  
 ロールの割り当てを削除するには、レポート マネージャーでレポートの [セキュリティ] プロパティ ページを開きます。 そのレポートが親レポートからセキュリティを継承している場合は、 **[アイテムのセキュリティを編集]** をクリックして、広範囲なアクセスを提供するロールの割り当てを削除する、制限付きのセキュリティ ポリシーを作成できます。たとえば、Everyone にアクセスを提供するロールの割り当てを削除し、Administrators など小さなユーザー グループにアクセスを提供するロールの割り当てを保持できます。  
  
## <a name="disable-a-shared-data-source"></a>共有データソースを無効にする  
 共有データ ソースを使用する利点の 1 つは、共有データ ソースを無効にして、レポートまたはデータ ドリブン サブスクリプションの実行を中止できることです。 共有データ ソースを無効にすると、レポートは外部ソースから切断されます。 共有データ ソースが無効な間は、すべてのレポートと共有データ ソースを使用するサブスクリプションで共有データ ソースを使用できません。 共有データソースを無効にするには、レポートマネージャーでデータソースを開き、[**このデータソースを有効に**する] チェックボックスをオフにします。  
  
 データ ソースが使用できない場合でも、レポートは読み込まれることに注意してください。 レポートにはデータは含まれていませんが、適切な権限を持ったユーザーは、レポートに関連付けられたプロパティ ページ、セキュリティ設定、レポート履歴、およびサブスクリプション情報にアクセスできます。  
  
## <a name="pause-a-shared-schedule"></a>共有スケジュールの一時停止  
 レポートまたはサブスクリプションが共有スケジュールから実行される場合、スケジュールを一時停止して処理を中止できます。 スケジュールによって駆動されるすべてのレポートおよびサブスクリプションの処理は、スケジュールが再開されるまで延期されます。 詳細については、「[共有スケジュールの一時停止と再開](schedules.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Reporting Services レポートサーバー &#40;ネイティブモード&#41;](../report-server/reporting-services-report-server-native-mode.md)   
 [レポート マネージャー &#40;SSRS ネイティブ モード&#41;](../report-manager-ssrs-native-mode.md)   
 [[セキュリティ] プロパティページ、アイテム &#40;レポートマネージャー&#41;](../security-properties-page-items-report-manager.md)  
  
  
