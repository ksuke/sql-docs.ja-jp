---
title: 高度なオブジェクトの選択 (DB2ToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: ca098c15-c343-4d7d-a284-c2fc405eb991
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 35e6c735fe0d9411d310298d4f32dbaab97b93c5
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67927788"
---
# <a name="advanced-object-selection-db2tosql"></a>高度なオブジェクトの選択 (DB2ToSQL)
[オブジェクトの**詳細設定**] ダイアログボックスでは、オブジェクト名に文字列と部分文字列を使用してデータベースオブジェクトをフィルター処理し、そのオブジェクトを選択または選択解除できます。 SSMA は、選択したオブジェクトに対して変換操作と移行操作を実行します。  
  
このダイアログボックスにアクセスするには、メタデータエクスプローラー内を右クリックし、[**オブジェクトの詳細選択**] を選択します。  
  
最初にダイアログボックスを開いたときに、[**サブカテゴリ項目の表示**] をクリックして、メタデータがプロジェクトに読み込まれているすべてのオブジェクトを表示します。 次に、文字列を入力して項目をフィルター処理できます。 たとえば、"company" という文字列を入力すると、その文字列を含む名前を持つすべての項目が表示されます。  
  
このダイアログボックスを使用する前に、スキーマを変換するか、プロジェクトを保存して、SSMA にすべてのメタデータを読み込むように強制することができます。  
  
## <a name="options"></a>オプション  
**すべての項目を確認**  
すべての項目の横にチェックマークを追加します。 これらの項目は、メタデータエクスプローラーですぐに選択されます。  
  
**すべての項目をオフにする**  
すべての項目の横にあるチェックマークを削除します。 これらの項目は、メタデータエクスプローラーですぐに消去されます。  
  
**リストビューモード**  
フィルター処理された項目を一覧に表示します。  
  
**テーブルビューモード**  
フィルター処理された項目をテーブルに表示します。  
  
**読み込まれた項目のみを表示します**  
カテゴリまたは項目の表示を切り替えます。 このボタンを選択すると、フィルター条件に一致するすべての項目と以前に読み込まれた項目が SSMA によって表示されます。 このボタンが選択されていない場合、SSMA はカテゴリフォルダーを表示します。  
  
**Assert**  
項目をフィルター処理するために使用する文字列を入力します。 たとえば、項目名に "ID" という文字列が含まれているすべての利用可能な項目を検索するには、**フィルター**ボックスに "id" という文字列を入力します。  
  
項目がフィルター条件に一致する場合は、文字列を入力したときにカテゴリまたは項目が表示されます。 一致する項目を表示するには、[**読み込まれた項目のみ**] をクリックすることをお勧めします。  
  
**フィルターのクリア**  
**フィルター**ボックスをクリアします。  
  
