---
title: '[クエリ] ([データセットのプロパティ] ダイアログ ボックス) (レポート ビルダー) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10024"
ms.assetid: 75432318-0b00-4797-917c-0a2e74f9d951
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 30dea5e6c9df6f1bd7f22d0ff37ca8800b21b095
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48132992"
---
# <a name="dataset-properties-dialog-box-query-report-builder"></a>「クエリ」 (「データセットのプロパティ」 ダイアログ ボックス) (レポート ビルダー)
  **[データセットのプロパティ]** ダイアログ ボックスの **[クエリ]** を選択すると、レポート サーバーから共有データセットを選択したり、埋め込みデータセットを作成したりできます。 埋め込みデータセットを作成するには、データ ソースを選択し、クエリを構築する必要があります。  
  
 **[データセットのプロパティ]** ダイアログ ボックスには、次のカテゴリがあります。  
  
-   [「パラメーター」 (「データセットのプロパティ」 ダイアログ ボックス) &#40;レポート ビルダー&#41;](../dataset-properties-dialog-box-parameters-report-builder.md)  
  
-   [「フィールド」 (「データセットのプロパティ」ダイアログ ボックス) &#40;レポート ビルダー&#41;](../dataset-properties-dialog-box-fields-report-builder.md)  
  
-   [「オプション」 (「データセットのプロパティ」 ダイアログ ボックス) &#40;レポート ビルダー&#41;](dataset-properties-dialog-box-options-report-builder.md)  
  
-   [「フィルター」 (「データセットのプロパティ」 ダイアログ ボックス) &#40;レポート ビルダー&#41;](../dataset-properties-dialog-box-filters-report-builder.md)  
  
 詳細については、「 [レポート埋め込みデータセットと共有データセット &#40;レポート ビルダーおよび SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)と呼ばれます。  
  
## <a name="options"></a>および  
 **名前**  
 データセットの名前を入力します。 名前は、レポートのすべてのデータ領域名またはグループ名と異なっている必要があります。  
  
 **[共有データセットを使用する]**  
 レポート サーバーの事前定義済みデータセットを使用するには、このオプションを選択します。  
  
 **[参照]**  
 レポート サーバーまたは SharePoint サイト上のフォルダーを参照し、共有データセット (.rsd) を選択します。  
  
 **[レポート内の埋め込みデータセットを使用する]**  
 このレポートでのみ使用されるデータセットを作成する場合は、このオプションを選択します。  
  
 **[データ ソース]**  
 データセットが基づくデータ ソースを選択します。 新しいデータ ソースを作成するには、 **[新規作成]** をクリックします。  
  
 **[クエリの種類]**  
 データセットに使用するコマンドまたはクエリの種類を選択します。 データベースからデータを取得するクエリを実行するには、 **[テキスト]** を選択します。 **の** TableDirect **機能を使用してテーブル内のすべてのフィールドを選択するには、** [テーブル] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] を選択します。 名前を指定してストアド プロシージャを実行するには、 **[ストアド プロシージャ]** を選択します。 既定では、ほとんどのクエリに使用される **[テキスト]** が選択されています。 選択したデータ ソース クエリを編集するには、 **[クエリ デザイナー]** をクリックします。  
  
> [!NOTE]  
>  すべての種類のクエリがすべてのデータ ソースでサポートされるとは限りません。 たとえば、 **テーブル** をサポートしているデータ ソースの種類は **OLE DB** および **ODBC**のみです。  
  
 **[データセットのプロパティ]**  
 このオプションは、コマンドの種類のオプションとして **[テキスト]** を選択したときに表示されます。 クエリを入力するか、 **[インポート]** をクリックして既存のクエリをインポートします。 式を編集するには、 **「式」** (*fx*) ボタンをクリックします。  
  
> [!NOTE]  
>  クエリ デザイナーを使用してクエリを作成した場合は、クエリのテキストがこのボックスに表示されます。  
  
 **テーブル名**  
 データセットとして使用するテーブルの名前を入力します。 このオプションは **[テーブル]** を選択したときに表示されます。  
  
 **[ストアド プロシージャ名の選択または入力]**  
 使用するストアド プロシージャの名前を入力または選択します。 式を編集するには、 **[式]** (*fx*) ボタンをクリックします。 このオプションは、コマンドの種類のオプションとして [ストアド プロシージャ] を選択したときに表示されます。  
  
 **[タイムアウト (秒)]**  
 クエリがタイムアウトするまでの期間を秒数で入力します。既定値は 30 秒です。 **[タイムアウト]** には、値を指定しないか、0 より大きい値を指定する必要があります。 空の場合は、クエリはタイムアウトしません。  
  
 **[フィールドの更新]**  
 クエリ コマンドを実行して、 [[データセットのプロパティ] ダイアログ ボックスの [フィールド]](../dataset-properties-dialog-box-fields-report-builder.md) ページにあるフィールドの一覧を更新します。  
  
## <a name="see-also"></a>参照  
 [レポートにデータを追加&#40;レポート ビルダーおよび SSRS&#41;](report-datasets-ssrs.md)   
 [レポート ビルダーのダイアログ ボックス、ペイン、およびウィザードに関するヘルプ](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [クエリ デザイナー &#40;レポート ビルダー&#41;](../query-designers-report-builder.md)  
  
  
