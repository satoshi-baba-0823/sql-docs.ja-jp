---
title: sp_help_maintenance_plan (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_help_maintenance_plan_TSQL
- sp_help_maintenance_plan
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_maintenance_plan
ms.assetid: e972a510-960e-41d6-93c5-c71cd581a585
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 665d4de0f1ee61942e4f1af431889672bcc313bb
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47757420"
---
# <a name="sphelpmaintenanceplan-transact-sql"></a>sp_help_maintenance_plan (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  指定したメンテナンス プランに関する情報を返します。 メンテナンス プランを指定しない場合は、すべてのメンテナンス プランに関する情報が返されます。  
  
> **注:** データベース メンテナンス プランと共にこのストアド プロシージャを使用します。 ただし、この機能は、このストアド プロシージャを使用しないメンテナンス プランでも実行できます。 このプロシージャは、以前のバージョンの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] からアップグレードしたプログラムでデータベース メンテナンス プランを管理する場合に使用します。  
  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_help_maintenance_plan [ [ @plan_id = ] 'plan_id' ]  
```  
  
## <a name="arguments"></a>引数  
 [  **@plan_id =**] **'***plan_id***'**  
 メンテナンス プランのプラン ID を指定します。 *plan_id*は**UNIQUEIDENTIFIER**します。 既定値は NULL です。  
  
## <a name="return-code-values"></a>リターン コードの値  
 なし  
  
## <a name="result-sets"></a>結果セット  
 場合*plan_id*が指定されている**sp_help_maintenance_plan**は 3 つのテーブルを返します: プラン、データベース、およびジョブ。  
  
### <a name="plan-table"></a>Plan テーブル  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**plan_id**|**uniqueidentifier**|メンテナンス プランの ID|  
|**plan_name**|**sysname**|メンテナンス プランの名前|  
|**date_created**|**datetime**|メンテナンス プランが作成された日付|  
|**所有者**|**sysname**|メンテナンス プランの所有者|  
|**max_history_rows**|**int**|システム テーブル内で、メンテナンス プランの履歴の記録用に割り当てられる行数の最大値|  
|**remote_history_server**|**int**|履歴レポートが書き込まれるリモート サーバーの名前|  
|**max_remote_history_rows**|**int**|履歴レポートが書き込まれるリモート サーバー上のシステム テーブルに割り当てられる行数の最大値|  
|**user_defined_1**|**int**|既定値は NULL|  
|**user_defined_2**|**nvarchar(100)**|既定値は NULL|  
|**user_defined_3**|**datetime**|既定値は NULL|  
|**user_defined_4**|**uniqueidentifier**|既定値は NULL|  
  
### <a name="database-table"></a>Database テーブル  
  
|列名|説明|  
|-----------------|-----------------|  
|**database_name**|メンテナンス プランに関連付けられているすべてのデータベースの名前。 *database_name* は **sysname** です。|  
  
### <a name="job-table"></a>Job テーブル  
  
|列名|説明|  
|-----------------|-----------------|  
|**job_id**|メンテナンス プランに関連付けられているすべてのジョブの ID。 *job_id*は**uniqueidentifier**します。|  
  
## <a name="remarks"></a>コメント  
 **sp_help_maintenance_plan**では、 **msdb**データベース。  
  
## <a name="permissions"></a>アクセス許可  
 メンバーのみ、 **sysadmin**固定サーバー ロールが実行できる**sp_help_maintenance_plan**します。  
  
## <a name="examples"></a>使用例  
 次の例では、メンテナンス プラン FAD6F2AB-3571-11D3-9D4A-00C04FB925FC に関する詳細情報を返します。  
  
```  
EXECUTE   sp_help_maintenance_plan   
   N'FAD6F2AB-3571-11D3-9D4A-00C04FB925FC';  
```  
  
## <a name="see-also"></a>参照  
 [メンテナンス プラン](../../relational-databases/maintenance-plans/maintenance-plans.md)   
 [データベース メンテナンス プラン ストアド プロシージャ&#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/database-maintenance-plan-stored-procedures-transact-sql.md)  
  
  
