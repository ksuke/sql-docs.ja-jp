---
title: エクスポート (DMX) |Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 622f575541d1a111e5cda6a28617ad400a977292
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "68892804"
---
# <a name="export-dmx"></a>エクスポート (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  マイニングモデルまたはマイニング構造オブジェクトをサーバーから Analysis Services バックアップファイル (abf) に抽出します。  
  
## <a name="syntax"></a>構文  
  
```  
  
EXPORT <object type> <object name>[, <object name>] [<object type> <object name>[, <object name] ] TO <filename> [WITH DEPENDENCIES]  
```  
  
## <a name="arguments"></a>引数  
 *オブジェクトの種類*  
 省略可能。エクスポートするオブジェクトの種類です (マイニングモデルまたはマイニング構造のいずれか)。  
  
 *オブジェクト名*  
 省略可能。 エクスポートするオブジェクトの名前。  
  
 */db*  
 文字列としてエクスポートするファイルの名前と場所です。  
  
## <a name="remarks"></a>解説  
 ステートメントがマイニング モデルを指定する場合、結果ファイルは関連するマイニング構造も含みます。 ステートメントで**依存関係が**指定されている場合は、オブジェクトを処理するために必要なすべてのオブジェクト (たとえば、データソースとデータソースビュー) が abf ファイルに含まれます。  
  
 データベースから[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]オブジェクトをエクスポートまたはインポートするには、データベースまたはサーバーの管理者である必要があります。  
  
## <a name="export-mining-structure-example"></a>マイニング構造のエクスポートの例  
 次の例は、Targeted Mailing と Forecasting マイニング構造、および Association マイニング モデルを、指定したファイルの場所にエクスポートします。 Association モデルは Market Basket マイニング構造の一部であるため、例では Market Basket 構造もエクスポートします。 マーケットバスケットマイニング構造の一部として存在する可能性があるその他のマイニングモデルは、マイニング**構造**ではなく、**マイニングモデル**を使用してエクスポートされたため、エクスポートされません。  
  
```  
EXPORT MINING STRUCTURE [Targeted Mailing], [Forecasting] MINING MODEL Association TO 'C:\TM_NEW.abf'  
```  
  
## <a name="export-mining-model-example"></a>マイニングモデルのエクスポートの例  
 次の例では、指定されたファイルの場所にアソシエーションマイニングモデルをエクスポートします。 ステートメントでは**依存関係が**指定されているので、データソースとデータソースビューオブジェクトも abf ファイルに含まれます。  
  
```  
EXPORT MINING MODEL [Association] TO 'C:\Association_NEW.abf' WITH DEPENDENCIES  
```  
  
## <a name="see-also"></a>参照  
 [DMX&#41; データ定義ステートメント &#40;のデータマイニング拡張機能](../dmx/dmx-statements-data-definition.md)   
 [DMX&#41; データ操作ステートメントを &#40;データマイニング拡張機能](../dmx/dmx-statements-data-manipulation.md)   
 [DMX&#41; ステートメントリファレンス &#40;データマイニング拡張機能](../dmx/data-mining-extensions-dmx-statements.md)   
 [DMX&#41;のインポート &#40;](../dmx/import-dmx.md)   
 [データ マイニング オブジェクトのエクスポートおよびインポート](https://docs.microsoft.com/analysis-services/data-mining/export-and-import-data-mining-objects)  
  
  
