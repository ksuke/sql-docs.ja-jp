---
title: 'ノートブックを管理する: Azure Data Studio'
titleSuffix: SQL Server Big Data Clusters
description: Azure Data Studio でノートブックを管理する方法について学習します。 これには、ノートブックを開く、ノートブックの保存、ビッグ データ クラスター接続の変更などが含まれます。
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.metadata: seo-lt-2019
ms.date: 12/13/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 8cf37ff6a4ad5e2b627fa5d968391cc5a7597a4a
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "75244092"
---
# <a name="how-to-manage-notebooks-in-azure-data-studio"></a>Azure Data Studio でノートブックを管理する方法

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

この記事では、SQL Server を使用して Azure Data Studio でノートブック ファイルを開いて保存する方法について示します。 また、SQL Server ビッグ データ クラスターへの接続を変更する方法も示します。

## <a name="prerequisites"></a>前提条件

この記事では、Azure Data Studio で使用するノートブックが既にあることを前提としています。 ノートブックを作成する場合は、「[SQL Server でノートブックを使用する方法](notebooks-guidance.md)」を参照してください。 Azure Data Studio でノートブックを使用するには、次の前提条件を満たしている必要があります。

- [ビッグ データ クラスターを展開する](quickstart-big-data-cluster-deploy.md)
- [SQL Server 2019 ビッグ データ ツール](deploy-big-data-tools.md):
   - **Azure Data Studio**
   - **SQL Server 2019 の拡張機能**
   - **kubectl**

## <a name="open-a-notebook"></a>ノートブックを開く

**[ノートブックを開く]** ダイアログを開くには、いくつかの方法があります。 [ファイル] メニュー、ダッシュボード、コマンド パレットを使用できます。 次のセクションでは、各メソッドについて説明します。

### <a name="file-menu"></a>[ファイル] メニュー

[ファイル] メニューで **[ファイルを開く]** を選択します (Windows の場合は Ctrl + O キー、Mac の場合は Cmd + O キー)。

![[ファイルを開く] を選択して [ファイルを開く] ダイアログを開く](./media/notebooks-how-to-manage/open-file-1.png) 

### <a name="dashboard"></a>ダッシュボード

ダッシュボードで **[ノートブックを開く]** をクリックして、[ファイルを開く] ダイアログを開きます。

![ダッシュボードで [ノートブックを開く] を選択して [ファイルを開く] ダイアログを開く](./media/notebooks-how-to-manage/open-file-2.png) 

### <a name="command-palette"></a>コマンド パレット

コマンド パレットから「**File: Open**」コマンドを使用します (Windows の場合は Ctrl + Shift + P キー、Mac の場合は Cmd + Shift + P キーと入力)。

![コマンド パレットに「File: Open」と入力して [ファイルを開く] ダイアログを開く](./media/notebooks-how-to-manage/open-file-3.png)

## <a name="save-a-notebook"></a>ノートブックを保存する

現在、ノートブックを保存する方法は 1 つあります。 ノートブックのツール バーから **[保存]** を選択する必要があります。

![ノートブックのツール バーの [保存] をクリックしてファイルを保存する](./media/notebooks-how-to-manage/save-file-1.png)

> [!NOTE]
> 現在、次のメソッドではノートブックへの変更は保存されません。
>
> - [ファイル] メニューの **[ファイルの保存]** 、 **[名前を付けて保存]** 、 **[すべてのファイルを保存]** コマンド。
> - コマンド パレットに入力した「**File: Save**」コマンド。

## <a name="change-the-big-data-cluster"></a>ビッグ データ クラスターを変更する

ノートブック用の SQL Server ビッグ データ クラスターを変更するには

1. ノートブックのツール バーから **[アタッチ先]** メニューをクリックします。

   ![ノートブックのツール バーから [アタッチ先] メニューをクリックする](./media/notebooks-how-to-manage/select-attach-to-1.png)

2. **[アタッチ先]** メニューからサーバーをクリックします。

   ![[アタッチ先] メニューからサーバーを選択する](./media/notebooks-how-to-manage/select-attach-to-2.png)

## <a name="next-steps"></a>次のステップ

Azure Data Studio のノードブックの詳細については、「[SQL Server 2019 でノートブックを使用する方法](notebooks-guidance.md)」を参照してください。
