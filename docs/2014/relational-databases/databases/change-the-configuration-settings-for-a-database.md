---
title: データベースの構成設定の変更 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: c862639952e9d77c5de85f77c090b9fdd019d451
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48071902"
---
# <a name="change-the-configuration-settings-for-a-database"></a>データベースの構成設定の変更
  このトピックでは、 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] または [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] を使用して、 [!INCLUDE[tsql](../../includes/tsql-md.md)]のデータベース レベルのオプションを変更する方法について説明します。 データベース オプションは各データベースに一意であり、他のデータベースには影響しません。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Restrictions)  
  
     [Security](#Security)  
  
-   **以下を使用してデータベースのオプション設定を変更するには:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 作業を開始する準備  
  
###  <a name="Restrictions"></a> 制限事項と制約事項  
  
-   これらのオプションを変更できるのは、システム管理者、データベース所有者、または **sysadmin** 固定サーバー ロールおよび **dbcreator** 固定サーバー ロールと **db_owner** 固定データベース ロールのメンバーだけです。  
  
###  <a name="Security"></a> セキュリティ  
  
####  <a name="Permissions"></a> Permissions  
 データベースに対する ALTER 権限が必要です。  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-change-the-option-settings-for-a-database"></a>データベースのオプション設定を変更するには  
  
1.  オブジェクト エクスプローラーで、 [!INCLUDE[ssDE](../../includes/ssde-md.md)] のインスタンスに接続し、サーバーを展開して **[データベース]** を展開します。データベースを右クリックし、 **[プロパティ]** をクリックします。  
  
2.  **[データベースのプロパティ]** ダイアログ ボックスで、 **[オプション]** をクリックします。ほとんどの構成設定にアクセスできます。 ファイルとファイル グループの構成、ミラーリングとログ配布の設定については、それぞれ専用のページにあります。  
  
##  <a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-change-the-option-settings-for-a-database"></a>データベースのオプション設定を変更するには  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]に接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。 この例では、[!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] サンプル データベースに対して、復旧モデルおよびデータ ページ検証のオプションを設定します。  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 詳細については、「[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ALTER DATABASE 互換性レベル &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)   
 [ALTER DATABASE データベース ミラーリング &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring)   
 [ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)   
 [データベースの名前変更](rename-a-database.md)   
 [データベースの圧縮](shrink-a-database.md)  
  
  
