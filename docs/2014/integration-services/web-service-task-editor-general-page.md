---
title: '[Web サービスタスクエディター] ([全般] ページ)Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: c6f993f1f2386782bf8225f22b285b9385e2f8e3
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66054538"
---
# <a name="web-service-task-editor-general-page"></a>[Web サービス タスク エディター] ([全般] ページ)
  
  **[Web サービス タスク エディター]** ダイアログ ボックスの **[全般]** ページを使用すると、HTTP 接続マネージャーの指定、Web サービス タスクで使用する WSDL (Web サービス記述言語) ファイルの場所の指定、Web サービス タスクの記述、WSDL ファイルのダウンロードなどの操作を実行できます。  
  
 このタスクの詳細については、「 [Web サービス タスク](control-flow/web-service-task.md)」を参照してください。  
  
## <a name="options"></a>オプション  
 **HTTPConnection**  
 接続マネージャーを一覧から選択するか、[ \<**新しい接続...**> をクリックして新しい接続マネージャーを作成します。  
  
> [!IMPORTANT]  
>  HTTP 接続マネージャーでは、匿名認証と基本認証のみがサポートされています。 Windows 認証はサポートされていません。  
  
 **関連トピック:**  [http 接続マネージャー](connection-manager/http-connection-manager.md)、 [Http 接続マネージャーエディター &#40;サーバーページ&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)  
  
 **Wsdlfile]**  
 コンピューターのローカルにある WSDL ファイルの完全修飾パスを入力するか、参照ボタン ( **[...]** ) をクリックしてファイルを指定します。  
  
 WSDL ファイルを既に手動でコンピューターにダウンロードしている場合は、そのファイルを選択します。 ただし、WSDL ファイルをまだダウンロードしていない場合は、次の手順に従います。  
  
-   ファイル名拡張子が ".wsdl" の空のファイルを作成します。  
  
-   
  **[WSDLFile]** オプションで、この空のファイルを選択します。  
  
-   **[Overwritewsdlfile]** の値をに`True`設定して、空のファイルが実際の WSDL ファイルで上書きされるようにします。  
  
-   
  **[WSDL のダウンロード]** をクリックして実際の WSDL ファイルをダウンロードし、空のファイルを上書きします。  
  
    > [!NOTE]  
    >  
  **[WSDL のダウンロード]** オプションは、 **[WSDLFile]** ボックスに既存のローカル ファイルの名前を指定するまで有効になりません。  
  
 **[Overwritewsdlfile]**  
 Web サービス タスクの WSDL ファイルを上書きできるかどうかを示します。  
  
 [ **Wsdl のダウンロード**] ボタンを使用して wsdl ファイルをダウンロードする場合は、この`True`値をに設定します。  
  
 **名前**  
 Web サービス タスクの一意な名前を指定します。 この名前は、タスク アイコンのラベルとして使用されます。  
  
> [!NOTE]  
>  タスク名はパッケージ内で一意である必要があります。  
  
 **説明**  
 Web サービス タスクの説明を入力します。  
  
 **WSDL のダウンロード**  
 WSDL ファイルをダウンロードします。  
  
 このボタンは、 **[WSDLFile]** ボックスに既存のローカル ファイルの名前を指定するまで有効になりません。  
  
## <a name="see-also"></a>参照  
 [Integration Services のエラーとメッセージの参照](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [[Web サービスタスクエディター] &#40;入力ページ&#41;](../../2014/integration-services/web-service-task-editor-input-page.md)   
 [Web サービスタスクエディター &#40;出力ページ&#41;](../../2014/integration-services/web-service-task-editor-output-page.md)   
 [[式] ページ](expressions/expressions-page.md)  
  
  
