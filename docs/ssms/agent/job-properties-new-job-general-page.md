---
title: ジョブのプロパティ - [新しいジョブ]\([全般] ページ) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: d05a3c12177fb5a3b9e35aa0dfd03e451a424be1
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42774938"
---
# <a name="job-properties---new-job-general-page"></a>ジョブのプロパティ - [新しいジョブ]\([全般] ページ)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> 
  [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

このページを使用すると、[!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント ジョブの全般プロパティを表示したり、変更したりできます。  
  
## <a name="options"></a>および  
**名前**  
ジョブの名前を変更します。  
  
**[所有者]**  
ジョブの所有者を選択します。  
  
**カテゴリ**  
ジョブのカテゴリを選択します。  
  
**[[...]]**  
選択したカテゴリのジョブを表示します。  
  
**[説明]**  
ジョブの説明を変更します。  
  
**有効**  
ジョブを有効にします。 ジョブが有効ではない場合、スケジュールや警告に応じてジョブが実行されることはありませんが、 **sp_start_job** ストアド プロシージャを使用して引き続きジョブを開始することができます。  
  
**ソース**  
ジョブのマスター サーバーを表示します。 **[ジョブのプロパティ] の [全般]** ページでのみ表示されます。  
  
**Created**  
ジョブが作成された日時を表示します。 **[ジョブのプロパティ] の [全般]** ページでのみ表示されます。  
  
**[最終更新]**  
ジョブが最後に変更された日時を表示します。 **[ジョブのプロパティ] の [全般]** ページでのみ表示されます。  
  
**[最終実行]**  
ジョブの最後の実行の開始日時を表示します。 **[ジョブのプロパティ] の [全般]** ページでのみ表示されます。  
  
**[ジョブ履歴の表示]**  
ジョブ履歴を表示します。 **[ジョブのプロパティ] の [全般]** ページでのみ表示されます。  
  
## <a name="see-also"></a>参照  
[ジョブの実装](../../ssms/agent/implement-jobs.md)  
[[ジョブ カテゴリ] - [ジョブ カテゴリの管理]](../../ssms/agent/job-categories-manage-job-categories.md)  
  
