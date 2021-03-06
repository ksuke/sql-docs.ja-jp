---
title: Command オブジェクトの概要 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- command object [ADO]
ms.assetid: e84a14b1-3c2a-4f7d-a966-9e08a93948df
author: MightyPen
ms.author: genemi
ms.openlocfilehash: ef68a36f64fbaf72f18af9fba6f2e2781422574c
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "67925857"
---
# <a name="command-object-overview"></a>Command オブジェクトの概要
**Command**オブジェクトを使用すると、次の操作を実行できます。  
  
-   **CommandText**プロパティを使用して、コマンドの実行可能テキスト (SQL ステートメントやストアドプロシージャなど) を定義します。  
  
-   **パラメーター**オブジェクトと**Parameters**コレクションを使用して、パラメーター化クエリまたはストアドプロシージャの引数を定義します。  
  
-   **Execute**メソッドを使用して、コマンドを実行し、必要に応じて**レコードセット**オブジェクトを返します。  
  
-   実行前に**CommandType**プロパティを使用してコマンドの種類を指定し、パフォーマンスを最適化します。  
  
-   **Command オブジェクトの** **Dialect**プロパティを使用して、コマンドテキストに関する特定の情報を指定します。  
  
-   **準備されたプロパティを**使用して、準備済み (またはコンパイル済み) のコマンドを実行前にプロバイダーが保存するかどうかを制御します。  
  
-   **CommandTimeout**プロパティを使用して、プロバイダーがコマンドの実行を待機する秒数を設定します。  
  
-   **ActiveConnection**プロパティを設定して、開いている接続を**Command**オブジェクトに関連付けます。  
  
-   **Name**プロパティを設定して、関連付けられている**接続**オブジェクトのメソッドとして**コマンド**オブジェクトを識別します。  
  
-   データを取得するために、**レコードセット**の**Source**プロパティに**Command**オブジェクトを渡します。  
  
-   コマンドを含む**ストリーム**オブジェクト (XML コマンドなど) を、それをサポートするプロバイダーに渡します。
