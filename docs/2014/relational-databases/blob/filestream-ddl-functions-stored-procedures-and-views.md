---
title: FILESTREAM DDL、関数、ストアド プロシージャ、およびビュー | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
ms.assetid: 9ecb49ee-f64e-4d30-a803-e4064a21950a
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7ec7d554c8dedd2fb48d1af8a44dbee550e376ef
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48189852"
---
# <a name="filestream-ddl-functions-stored-procedures-and-views"></a>FILESTREAM DDL、関数、ストアド プロシージャ、およびビュー
  FILESTREAM をサポートする Transact-SQL ステートメントおよび [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データベース オブジェクトの一覧を示します。  
  
 FileTable 機能をサポートするデータベース オブジェクトの一覧については、「 [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md)」を参照してください。  
  
##  <a name="ddl"></a> Transact-SQL データ定義言語 (DDL) ステートメント  
  
-   [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql)  
  
-   [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)  
  
-   [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)  
  
-   [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX  
  
##  <a name="func"></a> システム関数  
  
-   [GET_FILESTREAM_TRANSACTION_CONTEXT &#40;Transact-SQL&#41;](/sql/t-sql/functions/get-filestream-transaction-context-transact-sql)  
  
-   [PathName &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/pathname-transact-sql)  
  
##  <a name="proc"></a> システム ストアド プロシージャ  
  
-   [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [sp_filestream_force_garbage_collection &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-filestream-force-garbage-collection)  
  
##  <a name="cat"></a> システム ビュー: カタログ ビュー  
  
-   [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql)  
  
##  <a name="dmv"></a> システム ビュー: 動的管理ビュー  
  
-   [sys.dm_filestream_file_io_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-handles-transact-sql)  
  
-   [sys.dm_filestream_file_io_requests &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-requests-transact-sql)  
  
##  <a name="api"></a> プログラミング API  
  
-   [OpenSqlFilestream による FILESTREAM データへのアクセス](access-filestream-data-with-opensqlfilestream.md)  
  
-   [マネージド API: SqlFileStream クラス](http://go.microsoft.com/fwlink/?LinkId=220875)  
  
  
