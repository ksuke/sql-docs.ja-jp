---
title: 通常の接続とコンテキスト接続に関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 3b721409f0915cb1e13861f6481909e02af37cb2
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62919167"
---
# <a name="restrictions-on-regular-and-context-connections"></a>通常の接続とコンテキスト接続に関する制限事項
  このトピックでは、コンテキストと通常の接続を[!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)]使用してプロセスで実行されるコードに関連する制限事項について説明します。  
  
## <a name="restrictions-on-context-connections"></a>コンテキスト接続に関する制限事項  
 アプリケーションを開発するときは、コンテキスト接続に適用される次の制限事項を考慮してください。  
  
-   特定の接続に対して特定の時点に開くことができるコンテキスト接続は 1 つだけです。 複数のステートメントをそれぞれ独立した接続で同時に実行する場合、その中の 1 つの接続しか独自のコンテキスト接続を取得できません。 この制限事項は、異なる接続からの同時実行要求には影響しません。つまり、特定の接続の特定の要求にしか影響しません。  
  
-   コンテキスト接続では、MARS (複数のアクティブな結果セット) がサポートされません。  
  
-   コンテキスト接続では、`SqlBulkCopy` クラスを使用できません。  
  
-   コンテキスト接続では、更新バッチ処理がサポートされません。  
  
-   
  `SqlNotificationRequest` は、コンテキスト接続に対して実行するコマンドと併用できません。  
  
-   コンテキスト接続に対して実行しているコマンドはキャンセルできません。 
  `SqlCommand.Cancel` メソッドでは、この要求が暗黙に無視されます。  
  
-   "context connection=true" を使用する場合は、他の接続文字列キーワードを使用できません。  
  
-   
  `SqlConnection.DataSource` の接続文字列が、`SqlConnection` のインスタンス名ではなく、"context connection=true" である場合、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] プロパティは NULL を返します。  
  
-   コンテキスト接続に対してコマンドを実行する場合に `SqlCommand.CommandTimeout` プロパティを設定しても、影響はありません。  
  
## <a name="restrictions-on-regular-connections"></a>通常の接続に関する制限事項  
 アプリケーションを開発するときは、通常の接続に適用される次の制限事項を考慮してください。  
  
-   内部サーバーに対する非同期コマンドの実行はサポートされません。 コマンドの接続文字列に "async=true" を含めてコマンドを実行すると、`System.NotSupportedException` がスローされます。 このメッセージが表示されます。 "プロセス内で実行中[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]の非同期処理はサポートされていません。"  
  
-   
  `SqlDependency` オブジェクトはサポートされません。  
  
## <a name="see-also"></a>参照  
 [コンテキスト接続](context-connection.md)  
  
  
