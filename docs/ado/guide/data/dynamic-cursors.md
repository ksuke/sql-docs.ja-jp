---
title: 動的カーソル |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- cursors [ADO], dynamic
- dynamic cursors [ADO]
ms.assetid: 00460f30-8cf7-494e-82df-41012f40ae51
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 86e51b7880004117e8efc96bd310c6de705d43a6
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67925502"
---
# <a name="dynamic-cursors"></a>動的カーソル
動的カーソルは、結果セット内の行に対して行われたすべての変更を検出します。変更がカーソルの内部から行われるか、カーソル外の他のユーザーによって行われるかは関係ありません。 すべてのユーザーによって行われたすべての insert、update、および delete ステートメントは、カーソルを通じて表示されます。 動的カーソルは、カーソルを開いた後に、結果セットの行、順序、および値に対して行われたすべての変更を検出できます。 カーソルの外部で行われた更新は、コミットされるまで表示されません (カーソルトランザクション分離レベルが "未コミット" に設定されている場合を除く)。  
  
 たとえば、動的カーソルが2つの行と別のアプリケーションをフェッチし、その行の1つを更新し、もう一方を削除するとします。 その後、動的カーソルでこれらの行がフェッチされた場合、削除された行は検出されませんが、更新された行は新しい値が表示されます。  
  
 動的カーソルは、他のユーザーが行ったすべての同時更新をアプリケーションで検出する必要がある場合に適しています。 ADO で動的カーソルを使用することを示すには、 **AdOpenDynamic Cursor Typeenum**を使用します。  
  
## <a name="see-also"></a>参照  
 [順方向専用カーソル](../../../ado/guide/data/forward-only-cursors.md)   
 [静的カーソル](../../../ado/guide/data/static-cursors.md)   
 [Keyset カーソル](../../../ado/guide/data/keyset-cursors.md)
