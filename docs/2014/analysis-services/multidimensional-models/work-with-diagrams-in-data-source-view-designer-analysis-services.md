---
title: データソースビューデザイナーでのダイアグラムの操作 (Analysis Services) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.diagramorganizerpane.f1
- sql12.asvs.dsvdesigner.findtable.f1
- sql12.asvs.dsvdesigner.diagrampane.f1
helpviewer_keywords:
- data source views [Analysis Services], diagrams
- diagrams [Analysis Services]
ms.assetid: 491fdd22-2326-4f27-a0dd-0a02faae3fd8
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1aa03174d82c7319ce0c7b1cf455916e37a1b117
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66072380"
---
# <a name="work-with-diagrams-in-data-source-view-designer-analysis-services"></a>データ ソース ビュー デザイナーでのダイアグラムの操作 (Analysis Services)
  データ ソース ビュー (DSV) ダイアグラムは、DSV でのオブジェクトの視覚的イメージです。 対話的な操作で特定のオブジェクトを追加、非表示、削除、または変更できます。 また、同じ DSV で複数のダイアグラムを作成して、オブジェクトのサブセットに焦点を絞ることができます。  
  
 ダイアグラム ペインに表示されるダイアグラムの領域を変更するには、ペインの右下隅で 4 方向の矢印をクリックし、選択する領域がダイアグラム ペインに表示されるまで、サムネイル ダイアグラム上で選択ボックスをドラッグします。  
  
 このトピックのセクションは次のとおりです。  
  
 [ダイアグラムの追加](#bkmk_add)  
  
 [ダイアグラムを編集または削除する](#bkmk_edit)  
  
 [ダイアグラム内のテーブルの検索](#bkmk_findtables)  
  
 [ダイアグラム内のオブジェクトの整列](#bkmk_arrangeobjects)  
  
 [オブジェクトの配置を保持する](#bkmk_preserve)  
  
##  <a name="bkmk_add"></a>ダイアグラムの追加  
 DSV ダイアグラムは、DSV を作成すると自動的に作成されます。 DSV の作成後、追加のダイアグラムの作成と削除を行ったり、または特定のオブジェクトを非表示にしたりして、DSV を管理しやすい表示にすることができます。  
  
 新しいダイアグラムを作成するには、 **[ダイアグラム オーガナイザー]** ペイン内を右クリックし、 **[新しいダイアグラム]** をクリックします。  
  
 Analysis Services プロジェクトでデータソースビュー (DSV) を最初に定義すると、データソースビューに追加されたすべてのテーブルとビューが\<、すべてのテーブル> ダイアグラムに追加されます。 このダイアグラムはデータ ソース ビュー デザイナーの [ダイアグラム オーガナイザー] ペインに表示され、このダイアグラム内のテーブルおよびその列とリレーションシップが [テーブル] ペインに一覧表示され、さらにスキーマ ペインにグラフィック表示されます。 ただし、テーブル、ビュー、および名前付きクエリを\<すべてのテーブル> ダイアグラムに追加すると、このダイアグラム内のオブジェクトの数が非常に多くなるため、特に複数のファクトテーブルがダイアグラムに追加され、ディメンションテーブルが複数のファクトテーブルに関連付けられている場合に、リレーションシップを視覚化するのが困難になります。  
  
 データ ソース ビューにテーブルのサブセットのみを表示する場合の表示を簡潔化するために、データ ソース ビューのテーブル、ビュー、および名前付きクエリのサブセットで構成されるサブダイアグラム (略してダイアグラムと呼ばれる) を定義できます。 ダイアグラムを使用すると、ビジネスやソリューションのニーズに応じてデータ ソース ビューの項目をグループ化できます。  
  
 関連するテーブルや名前付きクエリを業務上の目的に合わせて別々のダイアグラムにグループ化すると、多数のテーブル、ビュー、および名前付きクエリが含まれているデータ ソース ビューが理解しやすくなります。 \<すべてのテーブル> ダイアグラムを除き、同じテーブルまたは名前付きクエリを複数のダイアグラムに含めることができます。 [すべて\<のテーブル> ダイアグラム] では、データソースビューに含まれるすべてのオブジェクトが1回だけ表示されます。  
  
##  <a name="bkmk_edit"></a>ダイアグラムを編集または削除する  
 ダイアグラムの操作をするときは、オブジェクトの追加と削除に使用するコマンドに十分注意してください。 たとえば、オブジェクトをダイアグラムから削除すると DSV から削除されます。 オブジェクトをダイアグラムからのみ削除する場合は、 **[テーブルの非表示]** を使用します。  
  
 ![ダイアグラム ワークスペース (右クリック メニュー) のスクリーンショット](../media/ssas-olapdsv-diagram.gif "ダイアグラム ワークスペース (右クリック メニュー) のスクリーンショット")  
  
 オブジェクトを個別に非表示にすることができますが、[関連テーブルの表示] を使用して戻すと、ダイアグラムにすべての関連オブジェクトが返されます。 ワークスペースにどのオブジェクトが返されるかを制御するには、[テーブル] ペインからオブジェクトをドラッグします。  
  
##  <a name="bkmk_findtables"></a>ダイアグラム内のテーブルの検索  
 使用するスキーマが大きい場合、 **[ダイアグラム]** ペインで特定のテーブルにスクロールするのが困難な場合があります。 この場合、次のツールを使用すると、ダイアグラム内でテーブルを簡単に見つけることができます。  
  
-   
  **[テーブル]** ペインでテーブルの一覧をスクロールします。  
  
     現在表示されているダイアグラムにテーブルを含めるには、 **[テーブル]** ペインからダイアグラム ペインにテーブルをドラッグします。  
  
     既にダイアグラムに含まれているテーブルを中心に表示するには、 **[テーブル]** ペインでそのテーブルを選択します。  
  
-   **ダイアグラム**ペインのテーブルロケーター-テーブルロケーターは、**ダイアグラム**ペインの右下隅にある垂直スクロールバーと水平スクロールバーの交差部分にある4方向矢印アイコンです。 その中で、ダイアグラム ペインに表示されている現在のダイアグラムのサムネイルが表示されます。 このサムネイルを使用すると、ダイアグラム ペインの表示をダイアグラム上の任意の位置に変更できます。  
  
-   [**テーブルの検索**] ダイアログボックスを使用して、ダイアグラムペインの [空いている領域] を右クリックし、[**テーブルの検索**] をクリックします。 または、ツール バーか **[データ ソース ビュー]** メニューの **[テーブルの検索]** をクリックします。  
  
     [フィルター] ボックスに文字列およびワイルドカード文字を入力すると、ダイアグラム内のテーブルのサブセットを表示できます。  
  
##  <a name="bkmk_arrangeobjects"></a>ダイアグラム内のオブジェクトの整列  
 データ ソース ビュー デザイナーでは、複数のダイアグラムを定義して DSV をわかりやすくすることができますが、数十個のテーブルを含んでいるダイアグラムは読み取りにくく、テーブルのレイアウトを手動で再調整するのは面倒な作業です。 データ ソース ビュー デザイナーでは、現在のダイアグラムにあるテーブル間のリレーションシップに基づいた四角形レイアウトまたは斜線レイアウトを使用して、現在のダイアグラムにあるテーブルを自動的に再調整できます。  
  
-   四角形レイアウトでは、リレーションシップの線は列間ではなくテーブル間に引かれます。 リレーションシップの線は、テーブル間で横方向および縦方向に表示されます。  
  
-   斜線レイアウトでは、リレーションシップの線はテーブル内の関連する列間で、できるだけ直接的に引かれます。 複数の列へのリレーションシップは、テーブル内の関連する最初の列に接続しています。 テーブル内の列が表示されていない場合、線はテーブルの一番上に向かって引かれます。  
  
##  <a name="bkmk_preserve"></a>オブジェクトの配置を保持する  
 希望の方法に従ってテーブルを手動で配置した後、さらにテーブルをダイアグラムに追加すると、ダイアグラムが更新され、その結果、オブジェクトのレイアウトに対して加えた最近の変更が失われる可能性があります。  
  
 この動作が発生する可能性が高いのはテーブルを追加するときであり、ダイアグラム オーガナイザーは新しいテーブルを収容する場所を確保するために、他のテーブルを移動することになります。 その後、すべてのテーブルと接続線が正しく表現されるように、ダイアグラムが再描画されます。 この時点で、特定のオブジェクトの配置に対するすべての手動調整が失われる可能性があります。  
  
 この問題を回避するには、最終的な調整を行う前に、最初にすべてのテーブルを追加します。 この場合は、後でダイアグラムを再度開くときに、オブジェクトは自らの位置を保持しています。  
  
## <a name="see-also"></a>参照  
 [多次元モデルのデータソースビュー](data-source-views-in-multidimensional-models.md)   
 [データソースビューデザイナー &#40;Analysis Services-多次元データ&#41;](../data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
