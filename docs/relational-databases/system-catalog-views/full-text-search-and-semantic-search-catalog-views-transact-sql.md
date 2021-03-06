---
title: フルテキスト検索およびセマンティック検索カタログ ビュー (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- catalog views [SQL Server], full-text search
- full-text search [SQL Server], catalog views
- full-text indexes [SQL Server], catalog views
ms.assetid: b08ad2fd-e3d8-458f-96f1-678217e0f419
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 9a6785c198bedb99ea0fd5b42f54cab431535527
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47735030"
---
# <a name="full-text-search-and-semantic-search-catalog-views-transact-sql"></a>フルテキスト検索およびセマンティック検索カタログ ビュー (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  ここでは、フルテキスト インデックスおよびセマンティック インデックスに関する情報を提供するカタログ ビューについて説明します。  
  
## <a name="full-text-search-catalog-views"></a>フルテキスト検索カタログ ビュー  
 [sys.fulltext_catalogs](../../relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql.md)  
 フルテキスト カタログごとに 1 行のデータを格納します。  
  
 [sys.fulltext_document_types](../../relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql.md)  
 フルテキスト インデックス操作に使用できるドキュメント型ごとに 1 行のデータを返します。 各行を表す、 **IFilter** SQL Server のインスタンスに登録されているインターフェイス。  
  
 [sys.fulltext_index_catalog_usages](../../relational-databases/system-catalog-views/sys-fulltext-index-catalog-usages-transact-sql.md)  
 フルテキスト カタログからフルテキスト インデックスへの参照ごとに 1 行のデータを返します。  
  
 [sys.fulltext_index_columns](../../relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql.md)  
 フルテキスト インデックスの一部となっている列ごとに 1 行のデータを格納します。  
  
 [sys.fulltext_index_fragments](../../relational-databases/system-catalog-views/sys-fulltext-index-fragments-transact-sql.md)  
 フルテキスト インデックスが含まれているすべてのテーブルのフルテキスト インデックス フラグメントごとに 1 行のデータを保持します。  
  
 [sys.fulltext_indexes](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md)  
 表形式オブジェクトのフルテキスト インデックスごとに 1 行のデータを保持します。  
  
 [sys.fulltext_languages](../../relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql.md)  
 ワード ブレーカーが SQL Server に登録された言語ごとに 1 行のデータが格納されます。 各行には、LCID と言語の名前が表示されます。  
  
 [sys.fulltext_stoplists](../../relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql.md)  
 データベース内のフルテキスト ストップリストごとに 1 行のデータを格納します。  
  
 [sys.fulltext_stopwords](../../relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql.md)  
 データベース内のすべてのストップリストでストップワードごとに 1 行のデータを格納します。  
  
 [sys.fulltext_system_stopwords](../../relational-databases/system-catalog-views/sys-fulltext-system-stopwords-transact-sql.md)  
 システム ストップリストへのアクセスを提供します。  
  
 [sys.registered_search_properties &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-registered-search-properties-transact-sql.md)  
 現在のデータベースの任意の検索プロパティ リストに含まれている検索プロパティごとに 1 行のデータを格納します。  
  
 [sys.registered_search_property_lists &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql.md)  
 現在のデータベースの検索プロパティ リストごとに 1 行のデータを格納します。  
  
## <a name="semantic-search-catalog-views"></a>セマンティック検索カタログ ビュー  
 [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql.md)  
 現在のインスタンスにインストールされているセマンティック言語統計データベースに関する行を返します[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]します。  
  
 [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql.md)  
 統計モデルが [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスに登録されている各言語の行を返します。 言語モデルが登録されている場合、その言語はセマンティック インデックス作成に対応しています。  
  
## <a name="see-also"></a>関連項目  
 [システム ビュー &#40;TRANSACT-SQL&#41;](http://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [フルテキスト検索とセマンティック検索の動的管理ビューおよび関数&#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)  
  
  
