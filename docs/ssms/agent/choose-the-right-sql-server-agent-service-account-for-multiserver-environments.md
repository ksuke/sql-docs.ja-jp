---
title: マルチサーバー環境に適したエージェント サービス アカウントを選択する
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: markingmyname
ms.author: maghan
ms.manager: jroth
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 01/19/2017
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: ecbf0a9d692092d61b3d10ae54f6d25afb4d7ba8
ms.sourcegitcommit: b78f7ab9281f570b87f96991ebd9a095812cc546
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "75242495"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a>マルチサーバー環境に適した SQL Server エージェント サービス アカウントの選択

[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスに対して選択する Windows アカウントによって、マルチサーバー環境の動作に次のような影響が生じることがあります。  
  
-   ローカルの Windows Administrators グループのメンバーではないアカウントで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスを実行する場合、マスター サーバーへのターゲット サーバーの参加は、失敗する可能性があります。 その場合は、次のエラー メッセージが返されます。  
  
    "参加操作に失敗しました"  
  
    この問題を解決するには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] サービスおよび [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスを再起動します。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスがローカル システム アカウントで実行されるとき、マスター サーバーとターゲット サーバー間の操作は、同じコンピューターにマスター サーバーとターゲット サーバーの両方が存在する場合にのみサポートされます。 この構成を使用している場合に、ターゲット サーバーをマスター サーバーに参加させると、次のメッセージが返されます。  
  
    " *<target_server_computer_name>* のエージェント開始アカウントに対象サーバーとしてのログオン権限があることを確認します"  
  
    情報提供を目的としたこのメッセージは無視できます。 参加操作は、正常に完了します。  
  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスのアカウントの選択の詳細については、「 [SQL Server エージェント サービスのアカウントの選択](../../ssms/agent/select-an-account-for-the-sql-server-agent-service.md)」を参照してください。  
  
