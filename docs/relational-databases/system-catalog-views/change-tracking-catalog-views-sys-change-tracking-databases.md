---
title: sys.change_tracking_databases (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 08/08/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- change_tracking_databases
- sys.change_tracking_databases_TSQL
- sys.change_tracking_databases
- change_tracking_databases_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.change_tracking_databases
- change tracking [SQL Server], sys.change_tracking_databases
ms.assetid: bb233baa-2991-4904-a0eb-3772b81121a4
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5eb810817929132bfef67c543ddcb915852f923a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47637740"
---
# <a name="change-tracking-catalog-views---syschangetrackingdatabases"></a>変更の追跡カタログ ビューでは、sys.change_tracking_databases
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  変更の追跡が有効なデータベースごとに 1 行のデータを返します。  

|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|database_id|**int**|データベースの ID です。 インスタンス内で一意では、この[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]します。|  
|is_auto_cleanup_on|**bit**|構成された保有期間を過ぎると変更追跡データが自動的にクリーンアップされるかどうかを示します。<br /><br /> 0 = Off<br /><br /> 1 = On|  
|retention_period|**int**|自動クリーンアップが使用されている場合に、変更追跡データをデータベースに保持する期間を示します。|  
|retention_period_units_desc|**nvarchar(60)**|保有期間の説明を指定します。<br /><br /> 分<br /><br /> 時間<br /><br /> Days|  
|retention_period_units|**tinyint**|保有期間の時間の単位です。<br /><br /> 1 = 分<br /><br /> 2 = 時間<br /><br /> 3 = 日|  
  
## <a name="permissions"></a>アクセス許可  
 sys.change_tracking_databases には、sys.databases に行われるのと同じ権限チェックが行われます。 sys.change_tracking_databases の呼び出し元がデータベースの所有者でない場合、対応する行を表示するには、少なくとも、ALTER ANY DATABASE または VIEW ANY DATABASE のサーバー レベルの権限か、master データベースまたは現在のデータベースの CREATE DATABASE 権限が必要です。  
  
## <a name="see-also"></a>参照  
 [変更の追跡カタログ ビュー &#40;TRANSACT-SQL&#41;](http://msdn.microsoft.com/library/6e8fd949-5560-4b34-879f-4e25aa24b183)   
 [データ変更の追跡 &#40;SQL Server&#41;](../../relational-databases/track-changes/track-data-changes-sql-server.md)  
  
  
