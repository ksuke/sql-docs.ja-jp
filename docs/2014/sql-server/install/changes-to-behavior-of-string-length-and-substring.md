---
title: 文字列長と substring | の動作の変更Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 18643dfc11d2b1b1d875a19c478f9ec8cbdd5be6
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66428846"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a>string-length および substring の動作の変更
  [文字列長関数 &#40;xquery&#41;](/sql/xquery/functions-on-string-values-string-length)と[Substring 関数 &#40;xquery&#41;](/sql/xquery/functions-on-string-values-substring)関数は、サロゲート文字を含む XML データベースと共に使用すると、異なる結果を返す場合があります。  
  
## <a name="description"></a>[説明]  
 データベースがと[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]互換性があるように設定されている場合、[文字列長関数 &#40;xquery&#41;](/sql/xquery/functions-on-string-values-string-length)および[substring 関数](/sql/xquery/functions-on-string-values-substring)は、Unicode 補助文字を処理するときに、xquery&#41;関数の変更を &#40;ます。 U+FFFF より大きいコード ポイントで定義された各 Unicode 補助文字は、これらの関数では 1 文字としてカウントされます。前のバージョンでは 2 文字としてカウントされていました。  
  
 サロゲート文字の詳細については、「[サロゲートと補助文字](https://go.microsoft.com/fwlink/?LinkId=178317)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [データベースエンジンのアップグレードに関する問題](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [SQL Server 2014 Upgrade Advisor &#91;新しい&#93;](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
