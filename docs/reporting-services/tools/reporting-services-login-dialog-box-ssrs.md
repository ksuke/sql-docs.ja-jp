---
title: '[Reporting Services ログイン] ダイアログ ボックス | Microsoft Docs'
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: tools
ms.topic: reference
f1_keywords:
- sql13.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3d60450f0f4c7feb7d6a00f66fcedeb89c764bf5
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "77082175"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a>[Reporting Services ログイン] ダイアログ ボックス (SSRS)
  **[Reporting Services ログイン]** ダイアログ ボックスを使用すると、レポートをレポート サーバーにパブリッシュする際に使用する資格情報を指定できます。  
  
-   **注** : プロジェクトの配置プロパティ **TargetServerURL** を設定してから初めてレポートをレポート サーバーにパブリッシュする場合は、サーバー名に **reports** ではなく **server**が含まれることを確認します。 たとえば、 `https://localhost/reportserver`ではなく `https://localhost/reports`のようになります。 ローカル サーバーの `reports` ディレクトリではなく `reportserver` ディレクトリを指定すると、このダイアログ ボックスが間接的に開かれます。 **TargetServerURL** の設定の詳細については、「[配置プロパティを設定する &#40;Reporting Services&#41;](../../reporting-services/tools/set-deployment-properties-reporting-services.md)」を参照してください。  
  
## <a name="options"></a>オプション  
 **[サーバー]**  
 レポート サーバーの名前を表示します。 たとえば、「 `https://localhost/reportserver` 」のように入力します。 既定のポート 80 と異なるポートを使用するレポート サーバーの場合は、ポート番号を含めます。 たとえば、「 `https://localhost:81/reportserver` 」のように入力します。  
  
 **ユーザー名**  
 Web サービスへのログインに使用するユーザー名を入力します。  
  
 **パスワード**  
 Web サービスへのログインに使用するパスワードを入力します。  
  
## <a name="see-also"></a>参照  
 [データ接続文字列を作成する - レポート ビルダーおよび SSRS](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)   
 [レポート データ ソースに関する資格情報と接続情報を指定する](../../reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources.md)   
 [レポート デザイナーの F1 ヘルプ](../../reporting-services/tools/report-designer-f1-help.md)  
  
  
