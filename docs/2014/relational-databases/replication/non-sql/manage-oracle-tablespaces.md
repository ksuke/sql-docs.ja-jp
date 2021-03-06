---
title: Oracle テーブルスペースの管理 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9a6bf22c7649646506b65628f556b52fead23375
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "63022298"
---
# <a name="manage-oracle-tablespaces"></a>Oracle テーブルスペースの管理
  テーブルスペースは、のファイルグループ[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]とほぼ同等のデータベースストレージの単位です。 テーブルスペースでは、個々のグループ内でデータベース オブジェクトの格納および管理が可能です。 詳細については Oracle のマニュアルを参照してください。  
  
 Oracle パブリケーションの一部としてテーブルを構成する場合、必要に応じて、レプリケーション ログ情報を格納するときに既存の Oracle テーブルスペースを使用するように指定できます。 指定しない場合、レプリケーション オブジェクトのテーブルスペースは、パブリッシャーの構成時に構成したレプリケーション管理ユーザー スキーマに関連付けられた既定のテーブルスペースとなります。  
  
 **アーティクルログテーブルのテーブルスペースを指定するには、次のようにし**ます。  
  
-   
  **[アーティクルのプロパティ]** ダイアログ ボックスでテーブルスペースを指定します。 このダイアログ ボックスへのアクセス方法の詳細については、「[パブリケーション プロパティの表示および変更](../publish/view-and-modify-publication-properties.md)」を参照してください。  
  
-   
  [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql) を使用します。 
  **sp_changearticle**を使用するには、以下を指定します。  
  
    -   パラメーター **@publisher**に対して Oracle パブリッシャーの名前を指定します。  
  
    -   パラメーター **@publication**に対して Oracle パブリケーションの名前を指定します。  
  
    -   パラメーター **@article**のアーティクルの名前です。  
  
    -   パラメーター **@property**の値 ' テーブルスペース '。  
  
    -   パラメーター **@value**のテーブルスペースの名前。  
  
## <a name="see-also"></a>参照  
 [Oracle パブリッシャーの構成](configure-an-oracle-publisher.md)   
 [Oracle パブリッシャー上で作成されたオブジェクト](objects-created-on-the-oracle-publisher.md)  
  
  
