---
title: DQS 操作のためのデータへのアクセス | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology:
- data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2e8b7a9d2061b32217ae06fe36fb71a924f4d408
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47621920"
---
# <a name="access-data-for-the-dqs-operations"></a>DQS 操作のためのデータへのアクセス

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) 操作にソース データを使用し、処理後のデータをエクスポートするには、次のいずれかの方法を使用できます。  
  
-   ソース データを DQS_STAGING_DATA データベース内のテーブル/ビューにコピーし、その後、それを DQS 操作に使用する。 処理後のデータを、DQS_STAGING_DATA データベース内の新しいテーブルにエクスポートすることもできます。 これを行うには、Windows ユーザー アカウントに DQS_STAGING_DATA データベースへの読み取り/書き込みアクセス権を与える必要があります。  
  
-   DQS 操作のソース データと、処理後のデータのエクスポート先に、自分専用のデータベースを使用する。 これを行うには、自分のデータベースが、Data Quality Server データベースと同じ SQL Server インスタンス内に存在する必要があります。 それ以外の場合、DQS 操作を行うために Data Quality Client でデータベースを利用することはできません。 また、Windows ユーザー アカウントには、照合結果をエクスポートする DQS_STAGING_DATA データベースへのアクセス権も付与する必要があります。これは、照合結果のエクスポートが、最初に照合結果が DQS_STAGING_DATA データベース内の一時テーブルにエクスポートされてから、エクスポート先データベース内のテーブルに移動されるという 2 段階で構成されるためです。  
  
## <a name="prerequisites"></a>Prerequisites  
  
-   DQSInstaller.exe ファイルを実行して [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] のインストールを完了しておく必要があります。 詳細については、「 [Data Quality Server のインストールを完了するための DQSInstaller.exe の実行](../../data-quality-services/install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md)」をご覧ください。  
  
-   データベースの SQL ログインへのアクセスを付与または変更するには、Windows ユーザー アカウントがデータベース エンジン インスタンスの適切な固定サーバー ロール (securityadmin、serveradmin、sysadmin など) のメンバーであることが必要です。  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqsstagingdata-database"></a>DQS_STAGING_DATA データベースへの読み取り/書き込みアクセス権をユーザーに付与するには  
  
1.  Microsoft SQL Server Management Studio を起動します。  
  
2.  Microsoft SQL Server Management Studio で、SQL Server インスタンスを展開し、 **[セキュリティ]** を展開し、 **[ログイン]** を展開します。  
  
3.  SQL ログインを右クリックし、 **[プロパティ]** をクリックします。  
  
4.  **[ログインのプロパティ]** ダイアログ ボックスの左ペインで **[ユーザー マッピング]** をクリックします。  
  
5.  右ペインで、 **[DQS_STAGING_DATA]** データベースの **[マップ]** 列のチェック ボックスをオンにし、 **[DQS_STAGING_DATA のデータベース ロール メンバーシップ]** ペインで次のロールを選択します。  
  
    -   **db_datareader**: テーブル/ビューからのデータの読み取り。  
  
    -   **db_datawriter**: テーブル内のデータの追加、削除、または変更。  
  
    -   **db_ddladmin**: テーブル/ビューの作成、変更、または削除。  
  
6.  **[ログインのプロパティ]** ダイアログ ボックスで、 **[OK]** をクリックして変更を適用します。  
  
## <a name="next-steps"></a>Next Steps  
 DQS 操作のデータ ソースとしてデータベースにアクセスする DQS 操作を実行してから、処理後のデータをデータベースにエクスポートしてください。  
  
## <a name="see-also"></a>参照  
 [Data Quality Services のインストール](../../data-quality-services/install-windows/install-data-quality-services.md)  
  
  
