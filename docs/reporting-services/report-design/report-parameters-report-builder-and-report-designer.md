---
title: レポート パラメーター (レポート ビルダーおよびレポート デザイナー) | Microsoft Docs
ms.date: 10/17/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: report-design
ms.topic: conceptual
f1_keywords:
- sql13.rtp.rptdesigner.reportparameters.general.f1
- sql13.rtp.rptdesigner.subreportproperties.parameters.f1
- "10091"
- sql13.rtp.rptdesigner.reportparameters.advanced.f1
- "10073"
- "10070"
ms.assetid: 58b96555-d876-4f61-bff8-db5764b9f5f9
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 52e879b6b5cbfcd38b2532391f1640f2b8f85681
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47681490"
---
# <a name="report-parameters-report-builder-and-report-designer"></a>レポート パラメーター (レポート ビルダーおよびレポート デザイナー)
  このトピックでは、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] レポート パラメーターの一般的な使用方法、設定できるプロパティ、その他について説明します。 レポート パラメーターを使用すると、レポート データの制御、他のレポートとの関連付け、およびレポートの表示方法の変更が可能になります。 レポート パラメーターは、[!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion.md)] やレポート デザイナーで作成するページ分割されたレポートのほか、[!INCLUDE[SS_MobileReptPub_Long](../../includes/ss-mobilereptpub-long.md)] で作成するモバイル レポートで使用できます。 詳細については、「 [レポート パラメーターの概念](../../reporting-services/report-design/report-parameters-concepts-report-builder-and-ssrs.md)」を参照してください。  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)] [!INCLUDE[ssRBnoversion](../../includes/ssrbnoversion.md)]、[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint モードおよびネイティブ モード|  
  
 ご自分でレポートにパラメーターを追加してみる場合には、「 [チュートリアル: レポートへのパラメーターの追加 (レポート ビルダー)](../../reporting-services/tutorial-add-a-parameter-to-your-report-report-builder.md)で作成するモバイル レポートで使用できます。  
    
##  <a name="bkmk_Common_Uses_for_Parameters"></a> パラメーターの一般的な使用方法  
 パラメーターの一般的な使用方法を以下に示します。  
  
 **改ページ調整されたレポート データおよびモバイル レポート データの制御**  
  
-   変数が含まれるデータセット クエリを記述して、データ ソース側で改ページ調整されたレポート データをフィルター処理する。  
  
-   共有データセットのデータをフィルター処理する。 改ページ調整されたレポートに共有データセットを追加する場合、クエリを変更することはできませんが、 レポート パラメーターを作成して、そのパラメーターへの参照を含むデータセット フィルターをレポートに追加することができます。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] モバイル レポート内で共有データセットのデータをフィルター処理する。 詳細については、「 [Create mobile reports with SQL Server Mobile Report Publisher](../../reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher.md) 」をご覧ください。  
  
-   ユーザーが値を指定して改ページ調整されたレポートのデータをカスタマイズできるようにする (2 つのパラメーターを用意して売上データの開始日と終了日を指定できるようにするなど)。  
  
 **他のレポートとの関連付け**  
  
-   パラメーターを使用してメイン レポートを詳細レポート、サブレポート、およびリンク レポートに関連付ける。 一連のレポートをデザインするときは、特定の情報を得るために各レポートをデザインできます。 各レポートでは、関連する情報について、さまざまな表示形式や詳細レベルで情報を示すことができます。 相互に関連する一連のレポートを提供するには、対象となる各レポート上のデータのうち、関連性を持つデータに対して、パラメーターを作成します。  
  
     詳細については、「[詳細レポート (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/drillthrough-reports-report-builder-and-ssrs.md)」、「[サブレポート (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/subreports-report-builder-and-ssrs.md)」、および「[リンク レポートを作成する](../../reporting-services/reports/create-a-linked-report.md)」を参照してください。  
  
-   複数のユーザー向けにパラメーター セットをカスタマイズする。 たとえば、売上レポートに基づく 2 つのリンク レポートをレポート サーバーに作成して、 一方のリンク レポートでは販売員用の定義済みパラメーター値を使用し、もう一方のリンク レポートでは販売責任者用の定義済みパラメーター値を使用することができます。 どちらのレポートも同じレポート定義を使用します。  
  
 **レポートの表示方法の変更**  
  
-   URL 要求を使用してレポート サーバーにコマンドを送信し、レポートの表示をカスタマイズする。 詳細については、「[URL アクセス (SSRS)](../../reporting-services/url-access-ssrs.md)」および「[URL 内でレポート パラメーターを渡す](../../reporting-services/pass-a-report-parameter-within-a-url.md)」を参照してください。  
  
-   ユーザーが値を指定してレポートの外観をカスタマイズできるようにする (ブール型のパラメーターを用意して、テーブルの入れ子になった行グループを展開するか折りたたむかを指定できるようにするなど)。  
  
-   式にパラメーターを含めることで、ユーザーがレポート データおよび外観をカスタマイズできるようにする。  
  
     詳細については、「[Parameters コレクションの参照 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/built-in-collections-parameters-collection-references-report-builder.md)」を参照してください。  
  
##  <a name="UserInterface"></a> パラメーターを持つレポートの表示  
 パラメーターを持つレポートを表示する場合、各パラメーターは、ユーザーが値を対話的に指定できるように、レポート ビューアー ツール バーに示されます。 次の図は、@ReportMonth、@ReportYear、@EmployeeID、@ShowAll、@ExpandTableRows、@CategoryQuota、および @SalesDate というパラメーターを持つレポートのパラメーター領域を示しています。  
  
 ![パラメーターを持つレポートの表示](../../reporting-services/report-design/media/ssrb-rptparamviewrpt.png "パラメーターを持つレポートの表示")  
  
1.  **パラメーター ペイン** 各パラメーターのプロンプトと既定値がレポート ビューアー ツール バーに表示されます。 パラメーター ペインのパラメーターのレイアウトをカスタマイズすることができます。 詳細については、「 [レポートのパラメーター ペインをカスタマイズする (レポート ビルダー)](../../reporting-services/report-design/customize-the-parameters-pane-in-a-report-report-builder.md)で作成するモバイル レポートで使用できます。  
  
2.  **@SalesDate パラメーター** @SalesDate パラメーターのデータ型は **DateTime** です。 テキスト ボックスの横に [日付を選択] というプロンプトが表示されます。 日付を変更するには、テキスト ボックスに新しい日付を入力するか、カレンダー コントロールを使用します。  
  
3.  **@ShowAll パラメーター** @ShowAll パラメーターのデータ型は **Boolean** です。 オプション ボタンを使用して、 **True** または **False**を指定します。  
  
4.  **[パラメーター エリアの表示/非表示の切り替え] ハンドル** レポート ビューアー ツール バーでこの矢印をクリックすると、パラメーター ペインの表示/非表示を切り替えることができます。  
  
5.  **@CategoryQuota パラメーター** @CategoryQuota パラメーターのデータ型は、 **Float** であるため、数値を指定します。  @CategoryQuota には、複数の値を設定できます。  
  
6.  **レポートの表示**  パラメーター値を入力した後にレポートを実行するには、 **[レポートの表示]** をクリックします。 すべてのパラメーターに既定値が定義されている場合、レポートは最初に表示するときに自動的に実行されます。  
  
##  <a name="bkmk_Create_Parameters"></a> パラメーターの作成  
 レポート パラメーターは、いくつかの異なる方法で作成できます。  
  
> [!NOTE]  
>  一部のデータ ソースでは、パラメーターがサポートされていません。  
  
 **パラメーターを持つデータセット クエリまたはストアド プロシージャ**  
  
 変数を含むデータセット クエリまたは入力パラメーターを含むデータセットのストアド プロシージャを追加する。 データセット パラメーターは変数または入力パラメーターごとに作成され、レポート パラメーターはデータセット パラメーターごとに作成されます。  
  
 ![レポート ビルダー パラメーター データセットのプロパティ](../../reporting-services/report-design/media/ssrb-paramdatasetprops.png "レポート ビルダー パラメーター データセットのプロパティ")  
  
 レポート ビルダーのこのイメージには、以下のものが示されています。  
  
1.  レポート データ ペインのレポート パラメーター。  
  
2.  パラメーターを持つデータセット。  
  
3.  パラメーター ペイン。  
  
4.  [データセットのプロパティ] ダイアログ ボックスにリストされているパラメーター。  
  
 データセットは、埋め込みデータセットまたは共有データセットにすることができます。 レポートに共有データセットを追加する場合、内部としてマークされているデータセット パラメーターはレポートでオーバーライドできません。 内部としてマークされていないデータセット パラメーターはオーバーライドできます。  
  
 詳細については、このトピックの「 [データセット クエリ](#bkmk_Dataset_Parameters) 」をご覧ください。  
  
 **パラメーターを手動で作成する**  
  
 パラメーターを手動でレポート データ ペインから作成する。 レポート パラメーターを構成すると、ユーザーが値を対話的に入力してレポートの内容や外観をカスタマイズできるようにすることができます。 構成済みの値をユーザーが変更できないようにすることもできます。  
  
> [!NOTE]  
>  パラメーターはサーバーで個別に管理されるため、新しいパラメーター設定でメイン レポートを再パブリッシュしても、レポートの既存のパラメーター設定は上書きされません。  
  
 **パラメーターを持つレポート パーツ**  
  
 パラメーターへの参照、または変数を含む共有データセットへの参照を含むレポート パーツを追加する。  
  
 レポート パーツはレポート サーバーに保存され、他のユーザーが各自のレポートで使用できます。 レポート パーツとして保存したパラメーターは、レポート サーバーからは管理できません。 レポート パーツ ギャラリーでパラメーターを検索し、レポートに追加してから構成します。 詳細については、「 [レポート パーツ (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/report-parts-report-builder-and-ssrs.md)」を参照してください。  
  
> [!NOTE]  
>  パラメーターは、依存データセットとパラメーターを持つデータ領域の別個のレポート パーツとしてパブリッシュできます。 パラメーターはレポート パーツとして表示されますが、レポート パーツ パラメーターをレポートに直接追加することはできません。 代わりに、レポート パーツを追加します。レポート パーツに含まれているか、レポート パーツによって参照されているデータセット クエリから、必要なレポート パラメーターが自動的に生成されます。 レポート パーツの詳細については、「[レポート パーツ (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/report-parts-report-builder-and-ssrs.md)」および「[レポート デザイナーでのレポート パーツ (SSRS)](../../reporting-services/report-design/report-parts-in-report-designer-ssrs.md)」を参照してください。  
  
### <a name="parameter-values"></a>パラメーター値  
 レポートのパラメーター値を選択するときに使用できるオプションを次に示します。  
  
-   ドロップダウン リストから 1 つのパラメーター値を選択する。  
  
-   ドロップダウン リストから複数のパラメーター値を選択する。  
  
-   1 つのパラメーターのドロップダウン リストから値を選択する。この値は、別のパラメーターのドロップダウン リストで使用できる値を決定します。 これらはカスケード型パラメーターです。 カスケード型パラメーターを使用すると、何千ものパラメーター値を管理しやすい数まで連続的にフィルター処理することができます。  
  
     詳細については、「 [カスケード型パラメーターのレポートへの追加 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)で作成するモバイル レポートで使用できます。  
  
-   パラメーターの既定値は作成済みなので、パラメーター値を最初に選択しないでレポートを実行する。  
  
##  <a name="bkmk_Report_Parameters"></a> レポート パラメーター プロパティ  
 [レポートのプロパティ] ダイアログ ボックスを使用して、レポート パラメーター プロパティを変更できます。 次の表に、各パラメーターに設定できるプロパティの概要を示します。  
  
|プロパティ|[説明]|  
|--------------|-----------------|  
|[オブジェクト名]|パラメーターの名前を入力します (大文字と小文字が区別されます)。 名前は文字で始まる必要があります。また、名前には、文字、数字、アンダースコア (_) を使用できます。 空白は使用しないでください。 自動的に生成されたパラメーターの名前は、データセット クエリのパラメーターと同じ名前になります。 既定では、手動で作成されたパラメーターの名前は、ReportParameter1 のようになります。|  
|[プロンプト]|レポート ビューアー ツール バーでパラメーターの横に表示されるテキストです。|  
|データ型|レポート パラメーターのデータ型は、次のいずれかである必要があります。<br /><br /> **[Boolean]**。 オプション ボタンから True または False を選択します。<br /><br /> **[DateTime]**。 カレンダー コントロールから日付を選択します。<br /><br /> **[Integer]**。 テキスト ボックスに値を入力します。<br /><br /> **[Float]**。 テキスト ボックスに値を入力します。<br /><br /> **[Text]**。 テキスト ボックスに値を入力します。<br /><br /> パラメーターに有効な値を定義した場合は、データ型が **DateTime**であっても、ユーザーはドロップダウン リストから値を選択することになります。<br /><br /> レポートのデータ型の詳細については、「 [RDL Data Types](../../reporting-services/reports/report-definition-language-ssrs.md#bkmk_RDL_Data_Types)」をご覧ください。|  
|[空白の値を許可]|パラメーターの値に空の文字列 (空白) を許可する場合に選択します。<br /><br /> パラメーターの有効な値の一覧を指定する場合に空白を有効な値にするには、指定する値の中に含める必要があります。 このオプションを選択すると自動的に空白が有効な値に含まれるわけではありません。|  
|[NULL 値を許可]|パラメーターの値に NULL 値を許可する場合に選択します。<br /><br /> パラメーターの有効な値の一覧を指定する場合に NULL を有効な値にするには、指定する値の中に含める必要があります。 このオプションを選択すると自動的に NULL が有効な値に含まれるわけではありません。|  
|[複数の値を許可]|使用可能な値を指定して、ユーザーがドロップダウン リストから値を選択できるようにすると、 データセット クエリで有効な値のみが送信されるようにすることができます。<br /><br /> パラメーターの値に、ドロップダウン リストに表示される複数の値を指定できる場合に選択します。 NULL 値は許容されません。 このチェック ボックスがオンの場合、パラメーターのドロップダウン リストで、使用可能な値の一覧にチェック ボックスが追加されます。 一覧の一番上には、 **[すべて選択]** チェック ボックスが表示されます。 ユーザーは、必要な値のチェック ボックスをオンにすることができます。<br /><br /> 値を提供するデータが急速に変化する場合は、ユーザーに最新の一覧が表示されるとは限りません。|  
|[表示]|レポートの実行時にレポートの上部にレポート パラメーターを表示する場合に選択します。 このオプションを選択すると、実行時にパラメーター値を選択できます。|  
|[非表示]|パブリッシュ済みレポート内のレポート パラメーターを非表示にする場合に選択します。 このレポート パラメーターの値は、レポートの URL やサブスクリプション定義で設定できます。また、レポート サーバーで設定することもできます。|  
|Internal|レポート パラメーターを非表示にする場合に選択します。 パブリッシュ済みレポートでは、レポート パラメーターはレポート定義でのみ参照できます。|  
|[使用できる値]|パラメーターに使用できる値を指定した場合、それらの値は常にドロップダウン リストとして表示されます。 たとえば、 **DateTime** パラメーターに使用できる値を指定すると、カレンダー コントロールの代わりに日付のドロップダウン リストがパラメーター ペインに表示されます。<br /><br /> レポートとサブレポートの間で値の一覧の一貫性を確保するには、データ ソースのオプションを設定して、データ ソースに関連付けられているデータセットのすべてのクエリに対して 1 つのトランザクションが使用されるようにします。<br /><br /> **セキュリティに関する注意** **Text** データ型のパラメーターが含まれるレポートでは、使用可能な値の一覧 (有効な値の一覧とも呼ばれる) を必ず使用してください。また、レポートを実行するすべてのユーザーに対して、レポートのデータの表示に必要なアクセス許可のみを与えてください。 詳細については、「 [セキュリティ (レポート ビルダー)](../../reporting-services/report-builder/security-report-builder.md)で作成するモバイル レポートで使用できます。|  
|[既定値]|クエリまたは静的な一覧から既定値を設定します。<br /><br /> 各パラメーターに既定値が指定されていれば、レポートは最初に表示したときに自動的に実行されます。|  
|詳細設定|このパラメーターがレポートのデータに直接的または間接的に影響するかどうかを示す値、レポート定義属性 **UsedInQuery**を設定します。<br /><br /> **[更新のタイミングを自動的に決定する]**<br /> レポート プロセッサでこの値の設定が決定されるようにする場合に選択します。 このパラメーターへの直接参照または間接参照が含まれているデータセット クエリがレポート プロセッサで検出された場合、またはレポートにサブレポートがある場合は、この値が **True** になります。<br /><br /> **[常に更新する]**<br /> データセット クエリまたはパラメーター式でレポート パラメーターを直接的または間接的に使用する場合に選択します。 このオプションを選択すると、 **UsedInQuery** が True に設定されます。<br /><br /> **[更新しない]**<br /> データセット クエリまたはパラメーター式でレポート パラメーターを直接的にも間接的にも使用しない場合に選択します。 このオプションを選択すると、 **UsedInQuery** が False に設定されます。<br /><br /> **注意** **[更新しない]** は注意して使用してください。 レポート サーバーでは、 **UsedInQuery** を使用してレポート データと表示レポートのキャッシュ オプション、およびスナップショット レポートのパラメーター オプションが制御されます。 **[更新しない]** を正しく設定しないと、正しいレポート データまたはレポートがキャッシュされなかったり、スナップショット レポートのデータの一貫性が損なわれたりする可能性があります。 詳細については、「[レポート定義言語 (SSRS)](../../reporting-services/reports/report-definition-language-ssrs.md)」を参照してください。|  
  
##  <a name="bkmk_Dataset_Parameters"></a> データセット クエリ  
 データセット クエリのデータをフィルター処理するには、結果セットに追加するか、結果セットから除外する値を指定して、取得データを制限する制限句を含めることができます。  
  
 データ ソースのクエリ デザイナーを使用すると、パラメーター化クエリの作成に役立ちます。  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] クエリの場合、データ ソースごとに異なるパラメーター構文がサポートされています。 サポートは、位置または名前によってクエリ内で識別されるパラメーターに応じて異なります。 詳細については、「[レポート データセット (SSRS)](../../reporting-services/report-data/report-datasets-ssrs.md)」で特定の外部データ ソースのトピックを参照してください。 リレーショナル クエリ デザイナーで、フィルターのパラメーター オプションを選択してパラメーター化クエリを作成する必要があります。 詳細については、「[リレーショナル クエリ デザイナーのユーザー インターフェイス &#40;レポート ビルダー&#41;](../../reporting-services/report-data/relational-query-designer-user-interface-report-builder.md)」を参照してください。  
  
-   Microsoft SQL Server Analysis Services、SAP NetWeaver BI、Hyperion Essbase などの多次元データ ソースに基づくクエリの場合は、クエリ デザイナーで指定したフィルターに基づくパラメーターを作成するかどうかを指定できます。 詳細については、「[クエリ デザイナー (レポート ビルダー)](http://msdn.microsoft.com/library/553f0d4e-8b1d-4148-9321-8b41a1e8e1b9)」で、データ拡張機能に対応するクエリ デザイナーのトピックを参照してください。  
  
##  <a name="bkmk_Manage_Parameters"></a> パブリッシュ済みレポートのパラメーターの管理  
 レポートをデザインするときは、レポート パラメーターはレポート定義に保存されます。 レポートをパブリッシュするときは、レポート パラメーターはレポート定義とは別に保存され管理されます。  
  
 パブリッシュ済みのレポートには、以下を使用できます。  
  
-   **レポート パラメーター プロパティ。** レポート パラメーターの値を (レポート定義とは関係なく) レポート サーバー上で直接変更する。  
  
-   **キャッシュされたレポート。** レポートのキャッシュ計画を作成するには、各パラメーターに既定値が指定されている必要があります。 詳細については、「 [レポートのキャッシュ (SSRS)](../../reporting-services/report-server/caching-reports-ssrs.md)でキャッシュを事前に読み込む唯一の方法でした。  
  
-   **キャッシュされた共有データセット。** 共有データセットのキャッシュ計画を作成するには、各パラメーターに既定値が指定されている必要があります。 詳細については、「 [レポートのキャッシュ (SSRS)](../../reporting-services/report-server/caching-reports-ssrs.md)でキャッシュを事前に読み込む唯一の方法でした。  
  
-   **リンク レポート。** さまざまな対象ユーザーのためにデータをフィルター処理するパラメーター値が事前に設定されたリンク レポートを作成できます。 詳細については、「 [リンク レポートを作成する](../../reporting-services/reports/create-a-linked-report.md)」を参照してください。  
  
-   **レポート サブスクリプション。** データをフィルター処理してレポートをサブスクリプションで配信するためのパラメーター値を指定できます。 詳細については「[サブスクリプションと配信 &#40;Reporting Services&#41](../../reporting-services/subscriptions/subscriptions-and-delivery-reporting-services.md)」を参照してください。  
  
-   **URL アクセス。** レポートへの URL でパラメーター値を指定できます。 URL アクセスを使用して、レポートを実行したりパラメーター値を指定したりすることもできます。 詳細については、「[URL アクセス (SSRS)](../../reporting-services/url-access-ssrs.md)」を参照してください。  
  
 レポート定義を再パブリッシュした場合には、通常、パブリッシュ済みレポートのパラメーター プロパティは保持されます。 レポート定義が同じレポートとして再パブリッシュされ、パラメーター名およびデータ型が同じである場合、プロパティ設定は保持されます。 レポート定義のパラメーターの追加や削除、または既存のパラメーターのデータ型やデータ名の変更を行った場合、パブリッシュ済みレポートのパラメーター プロパティの変更が必要になることがあります。  
  
 パラメーターは変更できない場合もあります。 レポート パラメーターがデータセット クエリから既定値を取得した場合、パブリッシュ済みレポートでその値を変更することも、レポート サーバーで変更することもできません。 実行時に使用される値は、クエリが実行されるとき (式ベースのパラメーターの場合は式が評価されるとき) に決定されます。  
  
 レポート実行オプションは、パラメーターの処理方法に影響します。 スナップショットとして実行されるレポートは、クエリがパラメーターの既定値を含まない限り、クエリから派生したパラメーターを使用できません。  
  
##  <a name="bkmk_Parameters_Subscription"></a> サブスクリプションのパラメーター  
 要求時レポートまたはスナップショット レポートにサブスクリプションを定義し、サブスクリプション処理で使用するパラメーター値を指定できます。  
  
-   **要求時レポート。**  要求時レポートでは、レポートに一覧表示された各パラメーターのパブリッシュされた値とは異なる、別のパラメーター値を指定できます。 たとえば、 *期間* パラメーターを使用して、顧客に現在の日付、週、または月のサービス要求を返すサービスの呼び出しレポートを保持していると仮定します。 レポートの既定のパラメーター値が **今日**に設定されている場合、サブスクリプションでは別のパラメーター値 ( **週** 、 **月**など) を使用して、週単位または月単位の数値を含むレポートを生成できます。  
  
-   **スナップショット。**  スナップショットでは、サブスクリプションはスナップショットに対して定義されているパラメーター値を使用する必要があります。 サブスクリプションを使用して、スナップショットに定義されているパラメーター値をオーバーライドすることはできません。 たとえば、レポート スナップショットとして実行される西地区の売上レポートをサブスクライブしていて、そのスナップショットに地域のパラメーター値として **Western** が指定されていると仮定します。 この場合、このレポートへのサブスクリプションを作成するには、サブスクリプションで **Western** パラメーター値を使用する必要があります。 パラメーターが無視されることを示すために、サブスクリプション ページのパラメーター フィールドは読み取り専用フィールドに設定されます。  
  
     レポート実行オプションは、パラメーターの処理方法に影響します。 レポート スナップショットとして実行されるパラメーター化されたレポートでは、レポート スナップショットに定義されているパラメーター値が使用されます。 パラメーター値は、レポートのパラメーター プロパティ ページで定義されています。 スナップショットとして実行されるレポートは、クエリがパラメーターの既定値を含まない限り、クエリから派生したパラメーターを使用できません。  
  
     サブスクリプションを定義した後にレポート スナップショットのパラメーター値が変わると、レポート サーバーでサブスクリプションが非アクティブ化されます。 サブスクリプションの非アクティブ化は、レポートが変更されたことを示します。 サブスクリプションをアクティブ化するには、サブスクリプションを開いてから保存します。  
  
> [!NOTE]  
>  データ ドリブン サブスクリプションでは、サブスクライバー データ ソースから取得したパラメーター値を使用できます。 詳細については、「[サブスクライバー データに対して外部データ ソースを使用する (データ ドリブン サブスクリプション)](../../reporting-services/subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)」を参照してください。  
  
 詳細については「[サブスクリプションと配信 &#40;Reporting Services&#41](../../reporting-services/subscriptions/subscriptions-and-delivery-reporting-services.md)」を参照してください。  
  
##  <a name="bkmk_Parameters_Security"></a> パラメーターとデータのセキュリティ保護  
 秘密性の高い情報を含むパラメーター化されたレポートを配布する際には注意が必要です。 レポート パラメーターは簡単に別の値に置き換えることができるので、予想外の情報が公開される可能性があるためです。  
  
 従業員データや個人データに対してパラメーターを使用する代わりに、Users コレクションの **UserID** フィールドを含む式に基づいてデータを選択すると、セキュリティを強化できます。 Users コレクションは、レポートを実行しているユーザーの ID を入手するための手段として利用できます。後は、その ID を使用して、ユーザー固有のデータを取得できます。  
  
> [!IMPORTANT]  
>  **String**型のパラメーターが含まれるレポートでは、使用可能な値の一覧 (有効な値の一覧とも呼ばれる) を必ず使用してください。また、レポートを実行するすべてのユーザーに対して、レポートのデータ表示に必要な権限のみを与えてください。 **String**型のパラメーターを定義する際には、任意の値が許容されるテキスト ボックスが表示されます。 使用可能な値の一覧を使用すると、入力できる値が制限されます。 データセット パラメーターにレポート パラメーターが関連付けられている場合に、使用可能な値の一覧を使用しないと、レポート ユーザーはテキスト ボックスに SQL 構文を入力できるため、レポートとサーバーで SQL インジェクション攻撃を受ける危険性が生じます。 さらに、ユーザーが新しい SQL ステートメントを実行するための十分な権限を持っている場合は、サーバーで予想外の結果が生じる可能性もあります。  
>   
>  データセット パラメーターと関連付けられていないレポート パラメーターがあり、このパラメーター値がレポートに含まれている場合、レポート ユーザーは、式の構文または URL をパラメーター値に入力して、このレポートを Excel または HTML に変換できます。 別のユーザーがこのレポートを表示して、表示されたパラメーター コンテンツをクリックすると、悪意のあるスクリプトまたはリンクが意図せず実行されてしまう可能性があります。  
>   
>  悪意のあるスクリプトを誤って実行するリスクを軽減するためには、信頼されたソースのレポートしか開かないようにする必要があります。 レポートのセキュリティ保護の詳細については、「 [レポートとリソースの保護](../../reporting-services/security/secure-reports-and-resources.md)」を参照してください。  
  
##  <a name="bkmk_How_To_Topics"></a> 操作方法に関するトピック  
 パラメーターとフィルターを扱う際の詳細な手順を紹介しているトピックの一覧を次に示します。  
  
-   [レポート パラメーターの追加、変更、または削除 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
-   [レポート パラメーターの値の追加、変更、または削除 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/add-change-or-delete-available-values-for-a-report-parameter.md)  
  
-   [レポート パラメーターの既定値の追加、変更、または削除 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/add-change-or-delete-default-values-for-a-report-parameter.md)  
  
-   [レポート パラメーターの順序の変更 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
-   [カスケード型パラメーターのレポートへの追加 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)  
  
-   [データセットへのフィルターの追加 (レポート ビルダーおよび SSRS)](../../reporting-services/report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
-   [サブレポートおよびパラメーターの追加 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md)  
  
-   [レポートのパラメーター ペインをカスタマイズする (レポート ビルダー)](../../reporting-services/report-design/customize-the-parameters-pane-in-a-report-report-builder.md)  
  

##  <a name="bkmk_Related_Topics"></a> 関連項目  
 [SSRS レポート パラメーターの構成 (クイズ)](http://go.microsoft.com/fwlink/p/?LinkID=306443)  
  
 [チュートリアル: レポートへのパラメーターの追加 (レポート ビルダー)](../../reporting-services/tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
[レポート パラメーターの概念](../../reporting-services/report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
 [レポート サンプル (レポート ビルダーおよび SSRS)](http://go.microsoft.com/fwlink/?LinkId=198283)  
  
 [レポートでの式の使用 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)  
  
 [式 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md)  
  
 [データのフィルター、グループ化、および並べ替え &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
 [セキュリティ (レポート ビルダー)](../../reporting-services/report-builder/security-report-builder.md)  
  
 [対話的な並べ替え、ドキュメント マップ、およびリンク (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
 [ドリルスルー、ドリルダウン、サブレポート、および入れ子になったデータ領域 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
