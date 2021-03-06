---
title: sys.dm_db_xtp_object_stats (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 08/29/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_db_xtp_object_stats_TSQL
- sys.dm_db_xtp_object_stats
- dm_db_xtp_object_stats
- sys.dm_db_xtp_object_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_db_xtp_object_stats dynamic management view
ms.assetid: 07300b59-3cab-4d3e-8138-5ea8f584f88f
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5b95073ccecbd2cca3663e4f48767764a0aa2590
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47780370"
---
# <a name="sysdmdbxtpobjectstats-transact-sql"></a>sys.dm_db_xtp_object_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-asdb-xxxx-xxx-md.md)]

  各操作によって影響を受ける行の数を報告、[!INCLUDE[hek_2](../../includes/hek-2-md.md)]以降、最後のデータベース オブジェクトを再起動します。 トランザクションがコミットされたかロールバックされたかに関係なく、統計情報は操作の実行時に更新されます。  
  
 sys.dm_db_xtp_object_stats は、変化の著しいメモリ最適化テーブルを特定するために役立ちます。 各インデックスはパフォーマンスに影響するため、テーブル内でまったく使用されていないインデックスまたはほとんど使用されていないインデックスの削除を検討することができます。 ハッシュ インデックスがあれば、バケット数を定期的に再評価する必要があります。 詳細については、次を参照してください。[ハッシュ インデックスの適切なバケット数を決定する](http://msdn.microsoft.com/library/6d1ac280-87db-4bd8-ad43-54353647d8b5)します。  
  
 sys.dm_db_xtp_object_stats は、書き込みと書き込みの競合が発生しているメモリ最適化テーブルを特定するために役立ちます。このような競合は、アプリケーションのパフォーマンスに影響します。 たとえば、トランザクションの再試行ロジックがあれば、同じステートメントの実行が複数回必要になることがあります。 また、この情報を使用して、書き込みと書き込みのエラー処理を必要とするテーブル (およびビジネス ロジック) を特定することもできます。  
  
 このビューには、データベース内のメモリ最適化テーブルごとに 1 行のデータが格納されます。  
  
 詳細については、「[インメモリ OLTP &#40;インメモリ最適化&#41;](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)」を参照してください。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|object_id|**bigint**|オブジェクトの ID です。|  
|row_insert_attempts|**bigint**|前回データベースが再起動されてから、コミットされたトランザクションおよび中断されたトランザクションの両方によってテーブルに挿入された行の数。|  
|row_update_attempts|**bigint**|前回データベースが再起動されてから、コミットされたトランザクションおよび中断されたトランザクションの両方によってテーブル内で更新された行の数。|  
|row_delete_attempts|**bigint**|前回データベースが再起動されてから、コミットされたトランザクションおよび中断されたトランザクションの両方によってテーブルから削除された行の数。|  
|write_conflicts|**bigint**|前回データベースが再起動されてから発生した書き込み競合の数。|  
|unique_constraint_violations|**bigint**|前回データベースが再起動されてから発生した UNIQUE 制約違反の数。|  
|object_address|**varbinary(8)**|内部使用のみです。|  
  
## <a name="permissions"></a>アクセス許可  
 現在のデータベースに対する VIEW DATABASE STATE 権限が必要です。  
  
## <a name="see-also"></a>参照  
 [メモリ最適化テーブルの動的管理ビュー &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/memory-optimized-table-dynamic-management-views-transact-sql.md)  
  
  
