---
title: server trigger recursion サーバー構成オプション | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- recursive triggers [SQL Server]
- triggers [SQL Server], recursive
- server trigger recursion option
ms.assetid: da4c25f5-d04c-4951-a3db-409e71a1b468
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: f1fc67db5d7d62c9257f6d66359b0166b6ed8c0b
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "62808883"
---
# <a name="server-trigger-recursion-server-configuration-option"></a>server trigger recursion サーバー構成オプション
  サーバーレベルのトリガーを再帰的に起動できるようにするかどうかを指定するには、 **server trigger recursion** オプションを使用します。 このオプションを 1 (ON) に設定すると、サーバーレベルのトリガーを再帰的に起動できます。 このオプションを 0 (OFF) に設定すると、サーバーレベルのトリガーは再帰的に起動できません。 server trigger recursion オプションが 0 (OFF) の場合は、直接再帰のみが回避されます (間接再帰を無効にするには、 **nested triggers** オプションを 0 に設定します)。このオプションの既定値は 1 (ON) です。 この設定はすぐに適用されます。サーバーを再起動する必要はありません。  
  
 詳しくは、「 [入れ子になったトリガーの作成](../../relational-databases/triggers/create-nested-triggers.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [サーバー構成オプション &#40;SQL Server&#41;](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
