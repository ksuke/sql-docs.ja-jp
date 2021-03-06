---
title: リフトチャート (Analysis Services-データマイニング) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- testing data mining models
- accuracy, charting
- viewing mining accuracy
- lift charts [Analysis Services]
- profit charts [Analysis Services]
- accuracy testing [data mining]
ms.assetid: ab77eca1-bd48-4fef-b27f-ff5b648e0501
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: feba3688947362847a95aea2d800c1fc6f15f6cf
ms.sourcegitcommit: 2d4067fc7f2157d10a526dcaa5d67948581ee49e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78174682"
---
# <a name="lift-chart-analysis-services---data-mining"></a>リフト チャート (Analysis Services - データ マイニング)
  **リフトチャート**は、ランダムな推測と比較してマイニングモデルが提供する改善をグラフィカルに表示し、*リフト*スコアの観点で変化を測定します。 データセットのさまざまな部分のリフトスコアを比較することによって、モデルごとにどのモデルが最適かを判断できます。また、データセット内のケースのうち、どの割合がモデルの予測を適用した方がメリットがあるかを判断することができます。

 リフト チャートにより、同じ予測属性を含む複数のモデルの予測の精度を比較できます。 また、1 つの結果 (予測属性の 1 つの値) またはすべての結果 (指定された属性のすべての値) のどちらかの予測精度を評価することもできます。

 利益チャートはリフト チャートと同類のチャートで、リフト チャートと同じ情報が含まれます。ただし、利益チャートには各モデルの使用に関連した利益の予測上の増加も表示されます。

##  <a name="bkmk_Top"></a>リフトチャートについて
 抽象のリフト チャートを理解することは難しい場合があります。 このため、リフト チャート ツールおよびチャートの情報の使用を示すために、ここでは、リフト チャートを使用してターゲット メーリング キャンペーンへの回答率を予測する 1 つのシナリオを考えます。

 このシナリオのマーケティング部門は、メーリング キャンペーンでは約 10% の回答率が一般的であることがわかっています。 データベースのテーブルには、10,000 人の潜在顧客のリストが保存されています。 この一般的な回答率から、通常、回答が期待できるのはわずか約 1,000 人の潜在顧客からのみです。 一方、このプロジェクトの予算は、データベース内の 10,000 人の顧客すべてを対象とするには不足しており、マーケティング部門は回答率の改善を図っています。 このシナリオの予算では、5,000 人の顧客のみに広告を郵送できるとします。 マーケティング部門には、次の 2 つの選択肢があります。

-   ターゲットとする 5,000 人の顧客をランダムに選択する。

-   回答する確率が高いと思われる 5,000 人の顧客をターゲットとするためにマイニング モデルを使用する。

 リフト チャートの使用により、両方の選択肢で予測される結果を比較できます。 たとえば、5,000 人の顧客をランダムに選択した場合、一般的な回答率に基づき、500 の回答しか期待できません。 このシナリオは、リフトチャートの*ランダム*線によって表されます。 一方、マーケティング部門がメーリングのターゲット選択にマイニング モデルを使用した場合は、これより大きな回答率を期待できます。これは、回答する確率の高い顧客をモデルが識別するためです。 このモデルが完全な場合、このモデルが絶対に誤らない予測を作成できると仮定でき、このモデルが推奨するわずか 1,000 人の潜在顧客に郵便を送ることで、1,000 の回答を得られることを期待できます。 このシナリオは、リフト チャートの *理想* 線によって示されています。

 現実には、マイニング モデルは、この 2 極、つまりランダムな推測と、完璧な予測の間に位置する確率が高くなります。 ランダムな推測に対する改善は、すべてリフトと見なされます。

 リフト チャートを作成する場合、特定の値をターゲットとしてその結果のみのリフトを測定したり、可能性のあるすべての結果のリフトを測定するモデルの一般的な評価を作成したりすることができます。 これらの選択は、次のセクションで説明されている最後のグラフに影響します。

 [トップに戻る](#bkmk_Top)

### <a name="lift-chart-with-target-value"></a>対象の値を持つリフト チャート
 次に示すチャートは、「 **基本的なデータ マイニング チュートリアル** 」で作成する [Targeted Mailing](../../tutorials/basic-data-mining-tutorial.md)モデルのリフト チャートです。 このチャートの対象の属性は [Bike Buyer] で、対象の値は 1 です。これは、自転車を購入したか、購入する可能性がある顧客を意味します。 したがって、このリフト チャートは、このモデルによって潜在顧客をより効率的に識別できることを示します。

 このグラフには、同じデータに基づく複数のモデルが含まれています。 これらのモデルの 1 つは、特定の顧客をターゲットとするようにカスタマイズされています。 モデルのトレーニングで使用するデータにフィルターを追加して、マイニング モデルをカスタマイズできます。 このフィルターは、トレーニングと評価の両方に使用するケースを、30 歳未満の顧客に制限します。 フィルターの 1 つの影響は、基本モデルとフィルターされたモデルとでは異なるデータ セットを使用するため、リフト チャートの評価に使用されるケースの数も異なることであることに注意してください。 予測結果やその他の統計情報を解釈する際は、この点に留意する必要があります。

 ![2 つのモデルを示すリフト チャート](../media/newliftchart-tm30-30.gif "2 つのモデルを示すリフト チャート")

 チャートの X 軸は、予測を比較するために使用されるテスト データセットの割合を示します。 チャートの Y 軸は、予測される値の割合を示します。

 ここで青で示されている斜めの直線は、すべてのチャートに表示されます。 これはランダムな推測の結果を表しており、リフトを評価するためのベースラインとなります。 これに加えて、リフト チャートに追加するモデルごとに 2 本の線が表示されます。1 本は、常に完璧な予測を行うモデルを作成できた場合のトレーニング データセットに対する理想的な結果を表し、もう 1 本はモデルに対する実際のリフト (結果の改善) を表します。

 この例では、フィルター選択されたモデルの理想線が濃い青で、実際のリフトの線が黄色で示されています。 チャートでは、理想線の最高点が約 40% を指しています。つまり、完璧なモデルを使用したとすれば、母集団の 40% にダイレクトメールを送信するだけで、ターゲットとする顧客の 100% に到達できることになります。 母集団の 40% をターゲットとするフィルター選択されたモデルの実際のリフトは、60 ～ 70% です。つまり、母集団の顧客の 40% にダイレクトメールを送信すると、ターゲットとする顧客の 60 ～ 70% に到達できます。

 
  **[マイニング凡例]** には、曲線上の任意のポイントにおける実際の値が含まれます。 測定される場所は、灰色の縦棒をクリックして移動することにより変更できます。 チャートの灰色の線は 30% まで移動されています。フィルター選択されたモデルとフィルター選択されていないモデルの両方が、このポイントにおいて最も効果的であると思われるためです。このポイントを過ぎると、リフトの量が小さくなります。

 
  **[マイニング凡例]** には、チャートの解釈に役立つスコアと統計も含まれます。 これらの結果は、灰色の線におけるモデルの精度を表します。このシナリオでは、この線がテスト ケース全体の 30% を含むよう位置しています。

|系列とモデル|Score|[対象になる母集団]|予測確率|
|-----------------------|-----------|-----------------------|-------------------------|
|メーリング対象全員|0.71|47.40%|61.38%|
|30 歳未満のメーリング対象|0.85|51.81%|46.62%|
|ランダム推測モデル||31.00%||
|理想モデル : メーリング対象全員||62.48%||
|理想モデル : 30 歳未満のメーリング対象||65.28%||

 [トップに戻る](#bkmk_Top)

#### <a name="interpreting-the-results"></a>結果の解釈
 これらの結果から、すべてのケースの 30% を測定すると、対象になる母集団のうち 47.40% の自転車の購買行動を汎用モデル (メーリング対象全員) で予測できることがわかります。 つまり、データベース内の顧客の 30% だけに対象を絞ってダイレクトメールを送信した場合、対象となる顧客の半数弱に到達できます。 フィルター選択されたモデルを使用した場合、少し良い結果を得ることができ、対象とする顧客の約 51% に到達できます。

 
  **[予測確率]** の値は、"購入する可能性がある" ケースに顧客を含めるために必要なしきい値を表します。 ケースごとに、モデルによって各予測の精度が推定され、その値が保存されます。この値を使用して、顧客をフィルター選択したり対象としたりできます。 たとえば、購入する可能性のある顧客を基本モデルから識別するには、予測確率が 61% 以上のケースを取得するクエリを使用します。 フィルター選択されたモデルで対象とする顧客を取得するには、すべての条件 (年齢、`PredictProbability` 値が 46% 以上) を満たすケースを取得するクエリを作成します。

 モデルを比較すると、おもしろいことがわかります。 フィルター選択されたモデルのほうが多くの潜在顧客を取得できるように思われますが、予測確率のスコアが 46% の顧客を対象とした場合、自転車を購入しない人にダイレクトメールを送信する確率も 53% あります。 したがって、どのモデルがより適しているかを判断する場合、フィルター選択されたモデルでは精度を高く、対象サイズを小さくして、基本モデルとの間のバランスを取る必要があります。

 
  **[スコア]** の値は、正規化された母集団におけるモデルの効果を計算することで、モデルどうしの比較に役立ちます。 スコアが高いほど良いため、この場合、予測確率は低くても、30 歳未満の顧客を対象とすると最も効果的であると結論できます。

 [トップに戻る](#bkmk_Top)

### <a name="lift-chart-for-model-with-no-target-value"></a>対象の値を持たないモデルのリフト チャート
 予測可能な列の状態を指定しない場合、次の図に示された種類のチャートが作成されます。 このチャートは、予測可能な属性のすべての状態に対してモデルがどのように実行されるかを表します。 たとえば、このチャートから、自転車を購入する可能性がある顧客と、自転車を購入する可能性が低い顧客の両方を、モデルでどの程度まで予測できるかがわかります。

 X 軸は予測可能な列を指定するチャートの場合と同じですが、Y 軸は今度は適正な予測の割合を示しています。 よって、ここでは理想線が斜めの線です。50% のデータで、50% のケースをモデルが適正に予測し、これが予想され得る最大値であることを表しています。

 ![適正な予測を示すリフト チャート](../media/lift1.gif "適正な予測を示すリフト チャート")

 チャート内をクリックすると灰色の縦棒を移動でき、 **[マイニング凡例]** には、ケース全体の割合と、適正に予測されたケースの割合が表示されます。 たとえば、灰色のスライダー バーを 50% の印に合わせると、 **[マイニング凡例]** に次の精度スコアが表示されます。 これらの数値は、「基本的なデータ マイニング チュートリアル」で作成した TM_Decision Tree モデルに基づいています。

|シリーズ、モデル|Score|[対象になる母集団]|予測確率|
|-------------------|-----------|-----------------------|-------------------------|
|TM_Decision Tree|0.77|40.50%|72.91%|
|理想モデル||50.00%||

 この表から、50% の母集団で、40% のケースを、作成したモデルが適正に予測することがわかります。 このモデルの精度には問題がないと考えられます。 ただし、このモデルは、予測可能な属性のすべての値を予測します。 このため、顧客の 90% が自転車を購入しないという、このモデルによる予測が正しい場合もあります。

 [トップに戻る](#bkmk_Top)

### <a name="restrictions-on-lift-charts"></a>リフト チャートの制限
 リフト チャートでは、予測可能な属性が離散値であることが必要です。 つまり、連続する数値を予測するモデルの精度の測定にリフト チャートを使用することはできません。

 予測可能な属性のすべての不連続値の予測精度は、1 行に表示されます。 予測可能な属性の個別の値に対する予測精度行を表示するには、各ターゲットの値に対するリフト チャートを別途作成する必要があります。

 1 つのリフト チャートに複数のモデルを追加することができます。ただし、すべてのモデルに同じ予測可能な属性が必要です。 属性を共有しないモデルは、 **[入力]** タブの選択で使用できません。

 タイム シリーズ モデルは、リフト チャートまたは利益チャートで表示できません。 タイム シリーズ予測の精度の測定は、履歴データの一部を取っておき、そのデータを予測と比較する方法が一般的です。 詳細については、「 [Microsoft Time Series アルゴリズム](microsoft-time-series-algorithm.md)」を参照してください。

### <a name="related-content"></a>関連コンテンツ
 [トップに戻る](#bkmk_Top)

## <a name="see-also"></a>参照
 [データマイニング&#41;のテストと検証 &#40;](testing-and-validation-data-mining.md)


