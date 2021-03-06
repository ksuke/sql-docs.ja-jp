---
title: 予測クエリビルダーを使用して予測クエリを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 73a3058b0e7836c96f15e876f5cf4b5f2cf8bedc
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66085347"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a>予測クエリ ビルダーを使用した予測クエリの作成
  予測クエリは、BI Development Studio でデータ マイニング ソリューションを構築しているときに作成できます。また、SQL Server Management Studio で既存のマイニング モデルを右クリックし、 **[予測クエリの作成]** オプションを選択して、作成することもできます。  
  
 
  **予測クエリ ビルダー** には、次の 3 種類のデザイン モードがあります。これらのモードを切り替えるには、左上隅のアイコンをクリックします。  
  
-   **デザイン**  
  
-   **クエリ**  
  
-   **結果**  
  
 **デザイン**モードでは、入力データを選択し、データをモデルにマップし、グリッドを使用して作成したステートメントに予測関数を追加することにより、予測クエリを作成できます。 デザイン グリッドには、次の構成要素があります。  
  
 **ソース**  
 新しい列のソースを選択します。 マイニング モデル、データ ソース ビューに含まれる入力テーブル、予測関数、またはカスタマイズされた式からの列を使用できます。  
  
 **フィールド**  
 
  **[ソース]** 列の選択に関連付けられている特定の列または関数を決定します。  
  
 **エイリアス**  
 結果セット内で列に付けられる名前を決定します。  
  
 **示**  
 
  **[ソース]** 列の選択項目を結果に表示するかどうかを決定します。  
  
 **グループ**  
 
  **[ルールの適用条件]** 列と共に使用して、かっこで式をグループ化します。 たとえば、(expr1 or expr2) and expr3 のようになります。  
  
 **And/Or**  
 クエリでロジックを作成します。 たとえば、(expr1 or expr2) and expr3 のようになります。  
  
 **条件/引数**  
 列に適用される条件またはユーザー式を指定します。 列をテーブルからセルにドラッグできます。  
  
 **クエリ**モードには、データマイニング拡張機能 (DMX) 言語に直接アクセスできるテキストエディターと、入力データとモデル列のビューが用意されています。 
  **[クエリ]** モードを選択すると、クエリの定義に使用したグリッドが基本的なテキスト エディターに変わります。 このエディターでは、作成したクエリのコピーと保存、既存の DMX クエリへの貼り付け、クリップボードからの貼り付け、実行が可能です。  
  
 **結果**ビューでは、現在のクエリが実行され、結果がグリッドに表示されます。 基になるデータが変更された場合に、クエリを再実行するには、ステータス バーの [再生] ボタンをクリックします。  
  
 ビジュアル ツールとテキスト エディターを組み合わせて使用して、データ マイニング クエリをデザインできます。 テキスト エディターでクエリへの変更を入力して **[デザイン]** ビューに戻ると、変更はすべて失われ、クエリは予測クエリ ビルダーで作成した元のクエリに戻ります。このトピックでは、グラフィカル クエリ ビルダーの使用手順を示します。  
  
### <a name="to-create-a-prediction-query"></a>予測クエリを作成するには  
  
1.  データ マイニング デザイナーの **[マイニング モデル予測]** タブをクリックします。  
  
2.  
  **[マイニング モデル]** テーブルの **[モデルの選択]** をクリックします。  
  
     
  **[マイニング モデルの選択]** ダイアログ ボックスが開き、現在のプロジェクトにあるすべてのマイニング構造が表示されます。  
  
3.  予測を作成するモデルを選択して、 **[OK]** をクリックします。  
  
4.  
  **[入力テーブルの選択]** テーブルで、 **[ケース テーブルの選択]** をクリックします。  
  
     
  **[テーブルの選択]** ダイアログ ボックスが開きます。  
  
5.  
  **[データ ソース]** 一覧で、予測を作成するデータが含まれているデータ ソースを選択します。  
  
6.  
  **[テーブル名またはビュー名]** ボックスで、予測を作成するデータが含まれているテーブルを選択し、 **[OK]** をクリックします。  
  
     入力テーブルを選択すると、列名に基づいてマイニング モデルと入力テーブルの間に既定のマッピングが作成されます。 マッピングを削除するには、 **[マイニング モデル]** テーブル内の列が **[入力テーブルの選択]** テーブル内のマップ先の列にリンクしている線をクリックして選択し、Del キーを押します。 
  **[入力テーブルの選択]** テーブルの列をクリックし、 **[マイニング モデル]** テーブルの対応する列にドラッグして、マッピングを手動で作成することもできます。  
  
7.  次の 3 種類の情報を任意に組み合わせて、予測クエリ ビルダーのグリッドに追加します。  
  
    -   
  **[マイニング モデル]** ボックスの予測可能列  
  
    -   
  **[入力テーブルの選択]** ボックスの入力列の任意の組み合わせ  
  
    -   予測関数  
  
8.  
  **[マイニング モデル予測]** タブのツール バーにある最初のボタンをクリックし、 **[結果]** を選択して、クエリを実行します。  
  
## <a name="see-also"></a>参照  
 [データマイニングデザイナーでの単一クエリの作成](create-a-singleton-query-in-the-data-mining-designer.md)   
 [データ マイニング クエリ](data-mining-queries.md)  
  
  
