---
title: レポートのエクスポート (レポート ビルダー) | Microsoft Docs
ms.date: 05/30/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a213d0decf0b2765dca07faec69135ddd3e44d99
ms.sourcegitcommit: b87d36c46b39af8b929ad94ec707dee8800950f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "77078488"
---
# <a name="export-reports-report-builder-and-ssrs"></a>レポートのエクスポート (レポート ビルダーおよび SSRS)

  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] レポートは、PowerPoint、画像、PDF、 [!INCLUDE[ofprword](../../includes/ofprword-md.md)]、 [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] などの別の形式にエクスポートできます。また、レポートから利用できる Atom 準拠のデータ フィードを一覧表示する Atom サービス ドキュメントを生成してエクスポートすることもできます。 レポートはレポート ビルダー、レポート デザイナー ([!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)])、またはレポート サーバーからエクスポートできます。  
  
 レポートは、次の目的のためにエクスポートします。  
  
-   **レポート データを別のアプリケーションで操作する。** たとえば、レポートを Excel にエクスポートした後で、引き続きそのデータを Excel で編集できます。  
  
-   **レポートを異なる形式で印刷する。** たとえば、レポートを PDF ファイル形式にエクスポートして、印刷できます。  
  
-   **レポートのコピーを別の種類のファイルとして保存する。** たとえば、レポートを Word にエクスポートして保存することで、レポートのコピーを作成できます。  
  
-   **レポート データをデータ フィードとしてアプリケーションで使用する。** たとえば、Power Pivot または Power BI で使用できる Atom 準拠のデータ フィードを生成してから、そのデータを Power Pivot または Power BI で操作できます。 詳細については、「[1 つのレポートからのデータ フィードの生成](../../reporting-services/report-builder/generate-data-feeds-from-a-report-report-builder-and-ssrs.md)」を参照してください。  
  
-   レポート サーバーでレポートを変換するのが便利なのは、サブスクリプションを設定したり電子メールでレポートを配信したりする場合や、レポート サーバーで利用可能なレポートを保存する場合です。 詳細については「[サブスクリプションと配信 &#40;Reporting Services&#41;](../../reporting-services/subscriptions/subscriptions-and-delivery-reporting-services.md)」を参照してください。  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] では、さまざまな表示拡張機能が用意されており、一般的なファイル形式へのレポートのエクスポートがサポートされます。 これらの表示拡張機能では、ソフト改ページを含むファイル形式 (Word や Excel など)、ハード改ページを含むファイル形式 (PDF や TIFF など)、またデータのみのファイル形式 (CSV や Atom 準拠の XML など) がサポートされます。  
  
 異なる形式でレポートをエクスポートすると、レポートのページ割り当てに影響する場合があります。 レポートをプレビューすると、HTML 表示拡張機能により、ソフト改ページ規則に従ってレポートが表示されます。 レポートを、Adobe Acrobat (PDF) などの別のファイル形式にエクスポートする場合、改ページは、ハード改ページ規則に従う物理ページ サイズに基づきます。 また、レポートに追加した論理的な改ページによってページを区切ることもできますが、実際のページの長さは、使用するレンダラーの種類によって異なります。 レポートの改ページを変更するには、選択した表示拡張機能の改ページの動作を理解する必要があります。 この表示拡張機能に合わせてレポート レイアウトのデザインの調整が必要になる場合があります。 詳細については、「[ページ レイアウトとレンダリング](../../reporting-services/report-design/page-layout-and-rendering-report-builder-and-ssrs.md)」を参照してください。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

## <a name="bkmk_export_from_rb"></a> レポートをレポート ビルダーからエクスポートするには

1.  レポートを実行するか、プレビューします。  
  
2.  リボンの **[エクスポート]** をクリックします。  
  
     ![レポート ビルダー エクスポート](../../reporting-services/report-builder/media/ssrb-export.png "レポート ビルダー エクスポート")  
  
3.  使用する形式を選択します。  
  
     **[名前を付けて保存]** ダイアログが表示されます。 既定では、ファイル名はエクスポートしたレポートの名前になります。 必要に応じてファイル名を変更できます。  
  
##  <a name="bkmk_export_from_rm"></a> レポートを [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web ポータルからエクスポートするには  
  
1.  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web ポータルの **[ホーム]** ページから、エクスポートするレポートに移動します。  
  
2.  目的のレポートをクリックして、レポートを表示およびプレビューします。  
  
3.  レポート ビューアー ツール バーの **[エクスポート]** ボックスの矢印をクリックします。  
  
     ![Reporting Services Web ポータル エクスポート](../../reporting-services/report-builder/media/ssrsportal-export.png "Reporting Services Web ポータル エクスポート")  
  
4.  使用する形式を選択します。  
  
5.  **[エクスポート]** をクリックします。 ファイルを開くか保存するかを確認するダイアログが表示されます。  
  
6.  選択したエクスポート形式でレポートを表示するには、 **[開く]** をクリックします。  
  
     \- - または -  
  
     選択したエクスポート形式でレポートをすぐに保存するには、 **[保存]** をクリックします。  
  
     選択した形式に関連付けられているアプリケーションを使用して、レポートが表示または保存されます。 **[保存]** をクリックした場合、レポートを保存する場所を指定するよう求められます。  
  
##  <a name="bkmk_export_from_sharepoint"></a> レポートを SharePoint ライブラリからエクスポートするには  
  
1.  レポートをプレビューします。  
  
2.  ツール バーの **[アクション]** をクリックし、 **[エクスポート]** をポイントして、使用する形式を選択します。  
  
     **[ファイルのダウンロード]** ダイアログ ボックスが開きます。  
  
3.  選択したエクスポート形式でレポートを表示するには、 **[開く]** をクリックします。  
  
     \- - または -  
  
     選択したエクスポート形式でレポートをすぐに保存するには、 **[保存]** をクリックします。  
  
     選択した形式に関連付けられているアプリケーションを使用して、レポートが表示または保存されます。 **[保存]** をクリックした場合、レポートを保存する場所を指定するよう求められます。  
  
     必要に応じて、エクスポートしたレポートのファイル名を変更します。  
  
     **注** ファイルの種類に関連付けられたプログラムがないことが原因で、レポートを選択した形式で開くことができない場合は、エクスポートされたファイルを保存するか、レポートを開くためのプログラムをオンライン上で探すことが求められます。  
  
##  <a name="RendererTypes"></a> 表示拡張機能の種類  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] の表示拡張機能には、次の 3 種類があります。  
  
-   **データ表示拡張機能** データ表示拡張機能では、すべての書式設定とレイアウト情報がレポートから取り除かれ、データのみが表示されます。 生成されたファイルを使用して、生のレポート データを別のファイル形式 (Excel、他のデータベース、XML データ メッセージ、カスタム アプリケーションなど) にインポートできます。 データ表示拡張機能では、改ページはサポートされません。  
  
     サポートされているデータ表示拡張機能は、CSV、XML、Atom です。  
  
-   **ソフト改ページ表示拡張機能** ソフト改ページ表示拡張機能では、レポートのレイアウトと書式設定が維持されます。 生成されたファイルは、Web ページや **ReportViewer** コントロールなど、画面上での閲覧や配信に最適化されます。  
  
     サポートされているソフト改ページ表示拡張機能は、[!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel、[!INCLUDE[msCoName](../../includes/msconame-md.md)] Word、Web アーカイブ (MHTML) です。  
  
-   **ハード改ページ表示拡張機能** ハード改ページ表示拡張機能では、レポートのレイアウトと書式設定が維持されます。 生成されたファイルは、一貫した印刷結果を提供すること、または、レポートを印刷物のような形でオンライン配信する際の見やすさを優先して最適化されます。  
  
     サポートされているハード改ページ表示拡張機能は、TIFF および PDF です。  
  
##  <a name="ExportFormats"></a> レポートの表示中にエクスポートできる形式  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] には、さまざまな形式でレポートを表示する表示拡張機能が用意されています。 選択したファイル形式に合わせてレポート デザインを最適化する必要があります。  次の表に、ユーザー インターフェイスからエクスポートできる形式を示します。  これに加え、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] サブスクリプションで利用できる形式や URL へのアクセスによってエクスポートできる形式もあります。  このトピックの「 [レポートをエクスポートするその他の方法](#OtherWaysExportingReports)」セクションを参照してください。  
  
|Format|表示拡張機能の種類|説明|  
|------------|------------------------------|-----------------|  
|Acrobat (PDF) ファイル|ハード改ページ|PDF 表示拡張機能を使用すると、Adobe Acrobat および PDF 1.3 をサポートするその他のサードパーティ製 PDF ビューアーで開くことのできるファイルとしてレポートが表示されます。 PDF 1.3 は Adobe Acrobat 4 以降のバージョンと互換性がありますが、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] では Adobe Acrobat 6 以降がサポートされています。 この表示拡張機能では、レポートの表示処理に Adobe 製のソフトウェアは必要ありません。 ただし、レポートを PDF 形式で表示または印刷するには、Adobe Acrobat などの PDF ビューアーが必要です。<br /><br /> 詳細については、「[PDF ファイルへのエクスポート](../../reporting-services/report-builder/exporting-to-a-pdf-file-report-builder-and-ssrs.md)」を参照してください。|  
|Atom|Data|Atom 表示拡張機能では、Atom 準拠のデータ フィードがレポートから生成されます。 データ フィードは、Atom 準拠のデータ フィードを使用するアプリケーション (Power Pivot や Power BI など) で読み取りと交換が可能です。<br /><br /> 出力は、レポートで使用可能なデータ フィードを一覧表示する Atom サービス ドキュメントです。 レポート内の各データ領域について、少なくとも 1 つのデータ フィードが作成されます。 データ領域の種類およびデータ領域に表示されるデータによっては、複数のデータ フィードが生成される場合があります。<br /><br /> 詳細については、「[複数のレポートからのデータ フィードの生成](../../reporting-services/report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md)」を参照してください。|  
|CSV|Data|CSV (コンマ区切り) 表示拡張機能では、レポートのデータを平面的に表して、標準化されたプレーンテキスト形式でレポートを表示します。プレーンテキスト形式のレポートは、多くのアプリケーションで簡単に読み取ったり変換したりすることができます。<br /><br /> 詳細については、「[CSV ファイルへのエクスポート](../../reporting-services/report-builder/exporting-to-a-csv-file-report-builder-and-ssrs.md)」を参照してください。|  
|EXCELOPENXML|ソフト改ページ|レポートを表示するときにエクスポート メニューで "Excel" として表示されます。 Excel 表示拡張機能では、レポートは、 [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] 2013 と互換性のある Excel ドキュメント (.xlsx) として表示されます。  詳細については、「[Microsoft Excel へのエクスポート](../../reporting-services/report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md)」を参照してください。|  
|PowerPoint|ハード改ページ|PowerPoint 表示拡張機能では、レポートは、PowerPoint 2013 と互換性のある PowerPoint ドキュメント (.pptx) として表示されます。|  
|TIFF ファイル|ハード改ページ|画像表示拡張機能では、レポートがビットマップまたはメタファイルとして表示されます。 画像表示拡張機能では、既定でレポートの TIFF ファイルが生成されます。このファイルは、複数のページに表示することもできます。 クライアントは、受信した画像をイメージ ビューアーで表示したり、印刷したりできます。<br /><br /> 画像表示拡張機能では、[!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)] でサポートされている形式 (BMP、EMF、EMFPlus、GIF、JPEG、PNG、TIFF) でファイルを生成できます。<br /><br /> 詳細については、「[画像ファイルへのエクスポート](../../reporting-services/report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md)」を参照してください。|  
|Web アーカイブ|ソフト改ページ|HTML 表示拡張機能では、HTML 形式でレポートを表示します。 また、完全な HTML ページを生成することも、他の HTML ページに埋め込むための HTML の一部分を生成することもできます。 すべての HTML は、UTF-8 エンコードで生成されます。<br /><br /> HTML 表示拡張機能は、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web ポータルで実行する場合など、レポート ビルダーでプレビューされ、ブラウザーで表示されるレポートの既定の表示拡張機能です。<br /><br /> 詳細については、「[HTML での表示](../../reporting-services/report-builder/rendering-to-html-report-builder-and-ssrs.md)」を参照してください。|  
|WORDOPENXML|ソフト改ページ|レポートを表示するときにエクスポート メニューで "Word" として表示されます。 Word 表示拡張機能では、レポートは、 [!INCLUDE[ofprword](../../includes/ofprword-md.md)] 2013 と互換性のある Word 文書 (.docx) として表示されます。  詳細については、「[Microsoft Word へのエクスポート](../../reporting-services/report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md)」を参照してください。|  
|XML|Data|XML 表示拡張機能では、レポートが XML 形式で返されます。 レポート XML のスキーマは、レポート固有のものであり、データのみを含んでいます。 XML 表示拡張機能では、レイアウト情報はレンダリングされません。また、改ページ位置も維持されません。 この拡張機能で生成された XML は、データベースにインポートしたり、XML データ メッセージとして使用したり、カスタム アプリケーションに送信することができます。<br/><br/> 詳細については、「[XML へのエクスポート](../../reporting-services/report-builder/exporting-to-xml-report-builder-and-ssrs.md)」を参照してください。|  
  
##  <a name="GeneratingDataFeedsFromReport"></a> レポートからのデータ フィードの生成  
 レポートからデータ フィードを生成するには、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web ポータルでレポートを実行した後、Web ポータルのツール バーの **[データ フィードの生成]** アイコンをクリックします。 ファイルを保存するか、開くかを選択するメッセージが表示されます。 **[開く]** を選択すると、.atomsvc ファイル拡張子に関連付けられているアプリケーションで Atom サービス ドキュメントが開きます。 **[保存]** を選択すると、ドキュメントが .atomsvc ファイルとして保存されます。 既定では、ファイルの名前はレポートの名前です。 この名前は、わかりやすい名前に変更できます。  
  
 Atom サービス ドキュメントは自分のコンピューターに保存されます。 後でレポート サーバーまたは別のサーバーにレポートをアップロードして、他のユーザーがレポートを使用できるようにすることができます。 詳細については、「[複数のレポートからのデータ フィードの生成](../../reporting-services/report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md)」および「[1 つのレポートからのデータ フィードの生成](../../reporting-services/report-builder/generate-data-feeds-from-a-report-report-builder-and-ssrs.md)」を参照してください。  
  
##  <a name="Troubleshooting"></a> エクスポートされたレポートのトラブルシューティング  
 レポートを別の形式にエクスポートした場合、表示が変わったり、思いどおりに動作しなかったりすることがあります。 これは、特定の規則や制限がレンダラーに適用されることがあるためです。 多くの制限には、レポートの作成時に考慮することにより対処可能です。 場合によっては、レポートで若干異なるレイアウトを使用する、レポート内へのアイテムの配置を工夫する、レポートのフッターを 1 行のテキストに制限するなどの作業が必要になります。  
  
 レポートにアラビア数字の Unicode テキストが含まれている場合やアラビア語の日付が含まれている場合、レポートを次のいずれかの形式でエクスポートしたりレポートを印刷したりすると、日付と数字が正しく表示されません。  
  
-   PDF  
  
-   Word  
  
-   Excel  
  
-   Image/TIFF  
  
 レポートを HTML にエクスポートした場合、日付と数字は正しく表示されます。  
  
 特定のレンダラーについてのトピックで、レポート アイテムとデータ領域がどのように表示されるかと、レンダラーごとの制限とソリューションについて説明します。  
  
-   [CSV ファイルへのエクスポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/exporting-to-a-csv-file-report-builder-and-ssrs.md)  
  
-   [Microsoft Excel へのエクスポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md)  
  
-   [Microsoft Word へのエクスポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md)  
  
-   [HTML での表示 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
-   [PDF ファイルへのエクスポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/exporting-to-a-pdf-file-report-builder-and-ssrs.md)  
  
-   [画像ファイルへのエクスポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md)  
  
-   [XML へのエクスポート &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/exporting-to-xml-report-builder-and-ssrs.md)  
  
-   [複数のレポートからのデータ フィードの生成 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md)  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] には、他の形式でも適切に動作するレポートを作成できるように、次の追加機能が用意されています。 Tablix データ領域 (テーブル、マトリックス、一覧) の改ページ、グループ、四角形により、レポートのページ割り当てをより適切に制御できます。 改ページで区切られたレポートのページに、さまざまなページ名を付け、ページ番号をリセットできます。 式を使用すると、レポートの実行時にページ名とページ番号を動的に更新できます。 詳細については、「[Reporting Services の改ページ](../../reporting-services/report-design/pagination-in-reporting-services-report-builder-and-ssrs.md)」を参照してください。  
  
 また、組み込みの RenderFormat グローバルを使用することにより、条件に応じてレンダラーごとに異なるレポート レイアウトを適用することもできます。 詳細については、「[組み込み Globals および Users 参照](../../reporting-services/report-design/built-in-collections-built-in-globals-and-users-references-report-builder.md)」を参照してください。

##  <a name="OtherWaysExportingReports"></a> レポートをエクスポートするその他の方法  
 レポートのエクスポートは、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web ポータルまたはレポート ビルダーでレポートを開くときに必要に応じて実行するタスクです。 エクスポート操作を自動化する場合は (レポートを、定期的なスケジュールで特定のファイルの種類として共有フォルダーにエクスポートする場合など)、レポートを共有フォルダーに配信するサブスクリプションを作成します。 詳細については、「 [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md)」を参照してください。  
  
 レポート ツールでプレビューしたレポート、または [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web ポータルなどのブラウザー アプリケーションで開いたレポートは常に、まず HTML でレンダリングされます。 表示の既定として別の表示拡張機能を指定することはできません。 ただし、後から電子メールの受信ボックスや共有フォルダーに配信する際に必要な表示形式でレポートを生成するサブスクリプションを作成できます。 詳細については、「 [ネイティブ モード レポート サーバーのサブスクリプションの作成と管理](../../reporting-services/subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) 」および「 [データ ドリブン サブスクリプションを作成、変更、および削除する](../../reporting-services/subscriptions/create-modify-and-delete-data-driven-subscriptions.md)」を参照してください。  
  
 また、URL パラメーターとして表示拡張機能を指定する URL を使用してレポートにアクセスし、最初に HTML でレポートをレンダリングすることなく、指定した形式に直接レンダリングすることもできます。 次の例は、Excel 形式でレポートを表示します。  
  
```  
https://<Report Server Name>/reportserver?/Sales/YearlySalesSummary&rs:Format=Excel&rs:Command=Render  
```  
  
 次の例は、名前付きインスタンスから PowerPoint レポートを表示します。  
  
```  
https://<Report Server Name/ReportServer_THESQLINSTANCE/Pages/ReportViewer.aspx?%2freportfolder%2freport+name+with+spaces&rs:Format=pptx  
```  
  
 詳細については、「 [URL アクセスを使用してレポートをエクスポート](../../reporting-services/export-a-report-using-url-access.md)」を参照してください。  

## <a name="next-steps"></a>次のステップ

[改ページ、見出し、列、および行の制御 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md)   
[レポートの検索、表示、管理 (レポート ビルダーおよび SSRS)](../../reporting-services/report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)   
[レポートの印刷 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-builder/print-reports-report-builder-and-ssrs.md)   
[レポートの保存 &#40;レポート ビルダー&#41;](../../reporting-services/report-builder/saving-reports-report-builder.md)  

その他の質問 [Reporting Services のフォーラムに質問してみてください](https://go.microsoft.com/fwlink/?LinkId=620231)
