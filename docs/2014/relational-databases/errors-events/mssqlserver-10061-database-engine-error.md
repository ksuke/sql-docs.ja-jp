---
title: MSSQLSERVER_10061 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b77e1d920f97891d173bfdcdcb23ceb6c0acf0c4
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62870710"
---
# <a name="mssqlserver_10061"></a>MSSQLSERVER_10061
    
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|SQL Server|  
|イベント ID|10061|  
|イベント ソース|MSSQLSERVER|  
|コンポーネント|SQLEngine|  
|シンボル名||  
|メッセージ テキスト|サーバーへの接続を確立中にエラーが発生しました。  SQL Server に接続している場合、既定の設定では SQL Server によるリモート接続が許可されていないために、このエラーが発生した可能性があります。 (プロバイダー: TCP プロバイダー、エラー: 0 - 対象のコンピューターによって拒否されたため、接続できませんでした。) (Microsoft SQL Server、エラー: 10061)|  
  
## <a name="explanation"></a>説明  
 サーバーがクライアント要求に応答しませんでした。 このエラーは、サーバーが起動していないことが原因で発生する可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 サーバーが起動していることを確認します。  
  
## <a name="see-also"></a>参照  
 [データベースエンジン Services を管理する](../../database-engine/configure-windows/manage-the-database-engine-services.md)   
 [クライアントプロトコルの構成](../../database-engine/configure-windows/configure-client-protocols.md)   
 [ネットワークプロトコルとネットワークライブラリ](../../sql-server/install/network-protocols-and-network-libraries.md)   
 [クライアントネットワークの構成](../../database-engine/configure-windows/client-network-configuration.md)   
 [クライアントプロトコルの構成](../../database-engine/configure-windows/configure-client-protocols.md)   
 [サーバー ネットワーク プロトコルの有効化または無効化](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
