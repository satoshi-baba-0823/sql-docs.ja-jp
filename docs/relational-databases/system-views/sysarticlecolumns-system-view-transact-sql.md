---
title: sysarticlecolumns (システム ビュー) (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sysarticlecolumns
- sysarticlecolumns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysarticlecolumns view
ms.assetid: a8dd8d13-c827-45c4-87ba-802725301382
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f5e5deebbfc386b84cbac8dbff28b057b152278d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47762030"
---
# <a name="sysarticlecolumns-system-view-transact-sql"></a>sysarticlecolumns (システム ビュー) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **Sysarticlecolumns**ビューがパブリッシュされたアーティクル内の列に関する追加情報を公開します。 このビューは、ディストリビューション データベースに保存されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**artid**|**int**|アーティクルの識別子です。|  
|**colid**|**int**|アーティクル内の列の識別子。|  
|**is_udt**|**int**|列がユーザー定義データ型 (UDT) 列であるかどうかを示します。 値**1** UDT 列を示します。|  
|**is_xml**|**int**|列が、 **xml**列。 値**1**を示します、 **xml**列。|  
|**is_max**|**int**|列が大きな値データ型の列は、(**varchar (max)**、 **nvarchar (max)** または**varbinary (max)**)。 値**1**大きな値の列を示します。|  
  
## <a name="see-also"></a>関連項目  
 [sp_articlecolumn (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-articlecolumn-transact-sql.md)   
 [sysarticlecolumns &#40;TRANSACT-SQL&#41;](../../relational-databases/system-tables/sysarticlecolumns-transact-sql.md)  
  
  
