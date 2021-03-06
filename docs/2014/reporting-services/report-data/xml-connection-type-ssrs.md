---
title: XML の接続の種類 (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b55fff2-1b15-4156-83ef-15ad9cf9f509
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9f5c70e0457009f71c3b9087ecf9f1354a8835
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "66106925"
---
# <a name="xml-connection-type-ssrs"></a>XML の接続の種類 (SSRS)
  XML データ ソースのデータをレポートに含めるには、種類が XML のレポート データ ソースに基づいたデータセットが必要です。 このビルトイン データ ソースの種類は、XML データ拡張機能に基づいています。 このデータ ソースの種類を使用して、XML ドキュメント、Web サービス、またはクエリに埋め込まれた XML に接続し、データを取得します。  
  
 このデータ拡張機能は、接続文字列とは別に管理される資格情報およびパラメーターをサポートしています。  
  
 このトピックの情報を使用して、データ ソースを構築してください。 詳細な手順については、「[データ接続またはデータソース &#40;レポートビルダーと SSRS&#41;の追加と検証](add-and-verify-a-data-connection-report-builder-and-ssrs.md)」を参照してください。  
  
##  <a name="Connection"></a>接続文字列  
 接続文字列を、HTTP 経由でアクセス可能な Web サービス、Web ベース アプリケーション、または XML ドキュメントを指す URL に設定する必要があります。 XML ドキュメントの拡張子は XML にする必要があります。 データセット クエリに埋め込まれた XML データに対し、空の接続文字列を使用することもできます。  
  
 次の例に、それぞれ Web サービスと XML ドキュメントに対する接続文字列の構文を示します。 
  `file://` プロトコルはサポートされません。  
  
|XML ドキュメントの種類|接続文字列の例|  
|-----------------------|-------------------------------|  
|Web サービス|`http://adventure-works.com/results.aspx`|  
|XML ドキュメント|`http://localhost/XML/Customers.xml`|  
|埋め込み XML ドキュメント|*指定*|  
  
 接続文字列の例の詳細については、「 [レポート ビルダーでのデータ接続、データ ソース、および接続文字列](../data-connections-data-sources-and-connection-strings-in-report-builder.md)」を参照してください。  
  
##  <a name="Credentials"></a>認証  
 クエリの実行、ローカルでのレポートのプレビュー、およびレポート サーバーからのレポートのプレビューには、資格情報が必要です。  
  
 レポートをパブリッシュした後、レポートをレポート サーバーで実行するときに、データを取得するための権限が有効な状態になるように、データ ソースの資格情報を変更する必要が生じる場合があります。  
  
 レポート作成クライアントから、次のオプションを使用して資格情報を指定します。  
  
-   現在の Windows ユーザー (統合セキュリティとも呼ばれます)。  
  
-   資格情報を必要としない。 資格情報を選択しない場合には、匿名アクセスが使用されます。 レポート サーバーが外部データ ソースに接続するための自動実行アカウントが定義済みであることを確認してください。 XML データ処理拡張機能は、対象 URL または Web サービスに資格情報を渡しません。したがって、自動実行アカウントが定義されていないと接続に失敗します。 詳細については、msdn.microsoft.com の [](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)オンライン ブック[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]にある  ドキュメントの「[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [自動実行アカウントの構成 (SSRS 構成マネージャー)](https://go.microsoft.com/fwlink/?linkid=121312)」を参照してください。  
  
 保存された資格情報や要求された資格情報はサポートされていません。 Windows 統合セキュリティが無効になっていると、データの取得に Windows 統合セキュリティを使用できないので注意してください。 保存された資格情報や要求された資格情報を指定すると、実行時にエラーが発生します。  
  
 詳細については、「 [Reporting Services のデータ接続、データソース、および接続文字列](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)」または「[レポートビルダーで資格情報を指定する](../specify-credentials-in-report-builder.md)」を参照してください。  
  
##  <a name="Query"></a>問い合わせ  
 クエリでは、レポート データセット用に取得するデータを指定します。 クエリの結果セットの列には、データセットのフィールド コレクションが設定されます。 レポートによって処理されるのは、クエリから取得された最初の結果セットだけです。  
  
 クエリを作成するにはテキスト ベースのクエリ デザイナーを使用する必要があります。 クエリでは XML データを返す必要があります。  
  
 テキスト ベースのクエリ デザイナーについては、「[テキストベースのクエリ デザイナーのユーザー インターフェイス (レポート ビルダー)](text-based-query-designer-user-interface-report-builder.md)」を参照してください。  
  
 XML データ ソースに対して使用できるデータセット クエリの値を以下に示します。  
  
-   *Empty*: 空のクエリを使用して、既定の結果セットを作成します。 既定のクエリは、データ ソースを読み取り、最初のリーフ コレクションまで XML ノード階層をたどることによって作成されます。 結果セットには、テキスト値を持つすべてのノード、および、そのパス上に存在するすべてのノード属性が格納されます。 結果セットの列は、データセットのフィールドにマップされます。  
  
-   要素パス: データソースから XML データを取得するときに使用するノードのシーケンスを指定します。  
  
-   XML Query 要素: 次のオプションの要素を含む XML クエリの仕様。  
  
    -   **Web サービスの場合:**  
  
         必須の XML 要素:  
  
         `<Method Namespace=`*"namespace"*  `Name="MethodName" />`  
  
         `-- or --`  
  
         `<SoapAction>`*soap アクション*`</SoapAction>`  
  
         省略可能な XML 要素:  
  
         `<ElementPath>`  *要素パス*  `</ElementPath>`  
  
         `<Method Namespace=`*"namespace"*  `Name="MethodName" />`  
  
         `-- or --`  
  
         `<SoapAction>`*soap アクション*`</SoapAction>`  
  
    -   **XML ドキュメントの場合:**  
  
         省略可能な XML 要素:  
  
         `<ElementPath>`  *要素パス*  `</ElementPath>`  
  
    -   **埋め込み XML ドキュメントの場合:**  
  
         必須の XML 要素:  
  
         
  `<XmlData>` 内部 XML `</XmlData>`  
  
         省略可能な XML 要素:  
  
         `<ElementPath>`  *要素パス*  `</ElementPath>`  
  
         `-- or --`  
  
         `<ElementPath IgnoreNamespaces="true">`  *要素パス*  `</ElementPath>`  
  
 クエリ構文の詳細については、msdn.microsoft.com にある [ ドキュメント (](report-data-ssrs.md)[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]オンライン ブック) の「[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [XML レポート データの XML クエリ構文 (SSRS)](https://go.microsoft.com/fwlink/?linkid=121312)」を参照してください。  
  
 例については、「 [Reporting Services: XML と Web サービス データ ソースの使用](https://go.microsoft.com/fwlink/?LinkId=81654)」を参照してください。  
  
### <a name="requirements-for-retrieving-xml-web-service-data"></a>XML Web サービスのデータを取得するための要件  
 これらは XML データ処理拡張機能では検出されません。 そのため、必要なデータを取得する SOAP メソッドを検索するための、なんらかの手段が必要です。 また、Web サービスがそのデータに対して使用するアドレス指定スキームや名前空間を把握しておく必要もあります。  
  
 Web サービスの場合は、または SOAP アクション`Query`を呼び出すメソッドを指定する <> 要素を提供できます。 XML データ ソースが、レポートに必要なデータを取得できるような階層構造になっていれば、クエリを空にして、既定のクエリを使用することもできます。 クエリの実行時に取得される XML 要素ノードの値および属性は、レポートに使用されているデータセットのフィールドにマップされます。  
  
### <a name="requirements-for-retrieving-xml-document-data"></a>XML ドキュメントのデータを取得するための要件  
 サーバーから HTTP プロトコルを使って XML データを取得するか、XML データを XML `Query` 要素に埋め込む必要があります。 XML ドキュメントを HTTP プロトコルを使って直接参照する場合、拡張子を .xml にする必要があります。  
  
 必要なすべてのデータを取得するための XML クエリの作成方法を理解しておく必要があります。 要素パスを指定しない場合、XML ドキュメントを解析するときの既定の動作では、XML ドキュメントのリーフノード コレクションへの使用可能な最初のパスが選択されます。 XML ドキュメントに他の兄弟リーフノード コレクションへのパスが含まれている場合、クエリでパスを指定しない限り、それらのノードは無視されます。  
  
 XQuery と似た XML 構文を使って要素パスを指定できます。  
  
 詳細については、msdn.microsoft.com にある [ ドキュメント (](element-path-syntax-for-xml-report-data-ssrs.md)[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]オンライン ブック) の「[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [XML レポート データの要素パス構文 (SSRS)](https://go.microsoft.com/fwlink/?linkid=121312)」を参照してください。  
  
##  <a name="Parameters"></a> パラメーター  
 クエリの解析時にパラメーターは識別されません。  
  
 パラメーターを追加するには、 **[データセットのプロパティ]** ダイアログ ボックスの [[パラメーター]](../dataset-properties-dialog-box-parameters-report-builder.md) ページを使用して手動で作成する必要があります。  
  
##  <a name="Remarks"></a> 解説  
 XML データ拡張機能は、階層構造でない表形式の XML データからのレポート作成をサポートしています。 詳細については、「[外部データ ソースのデータを追加する (SSRS)](add-data-from-external-data-sources-ssrs.md)」を参照してください。  
  
 
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データベースから XML ドキュメントを取得するためのサポートは組み込まれていません。  
  
##  <a name="HowTo"></a> 操作方法に関するトピック  
 データ接続、データ ソース、およびデータセットを操作する手順について説明します。  
  
 [データ接続またはデータソース &#40;レポートビルダーと SSRS&#41;に追加して検証する](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [レポートビルダーおよび SSRS を &#40;共有データセットまたは埋め込みデータセットを作成&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [データセット &#40;レポートビルダーと SSRS&#41;にフィルターを追加する](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
##  <a name="Related"></a>関連セクション  
 次に示すセクションでは、レポート データの概念が詳細に説明されているほか、データに関連するレポートのパーツを定義、カスタマイズ、および使用する手順が説明されています。  
  
 [レポート &#40;レポートビルダーおよび SSRS&#41;にデータを追加する](report-datasets-ssrs.md)  
 レポートのデータへのアクセスの概要について説明します。  
  
 [レポート ビルダーでのデータ接続、データ ソース、および接続文字列](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 データ接続とデータ ソースについて説明します。  
  
 [レポート埋め込みデータセットと共有データセット (レポート ビルダーおよび SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 埋め込みデータセットと共有データセットについて説明します。  
  
 [データセット フィールド コレクション &#40;レポート ビルダーおよび SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md)  
 クエリによって生成されるデータセット フィールド コレクションについて説明します。  
  
 [Reporting Services によってサポートされるデータソース &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [オンラインブック](https://go.microsoft.com/fwlink/?linkid=121312)の[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]ドキュメントを参照してください。  
 各データ拡張機能のプラットフォームおよびバージョン サポートに関する詳細な情報です。  
  
## <a name="see-also"></a>参照  
 [レポート パラメーター (レポート ビルダーおよびレポート デザイナー)](../report-design/report-parameters-report-builder-and-report-designer.md)   
 [データのフィルター、グループ化、および並べ替え (レポート ビルダーおよび SSRS)](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)   
 [式 &#40;レポート ビルダーおよび SSRS&#41;](../report-design/expressions-report-builder-and-ssrs.md)  
  
  
