---
title: 記述子フィールド |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- descriptors [ODBC], fields
- header fields [ODBC]
- record fields [ODBC]
ms.assetid: f38623c8-fdd4-4601-b1f0-97c593d31177
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b512ff83d0002ef4a7c79b48cd8829fc2dbb9ba3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47696581"
---
# <a name="descriptor-fields"></a>記述子フィールド
記述子が含まれて*ヘッダー*と*レコード*列またはパラメーターを完全に記述されるフィールド。  
  
 記述子には、次のヘッダー フィールドの 1 つのコピーが含まれています。 ヘッダー フィールドを変更するには、すべての列またはパラメーターに影響します。  
  
|||  
|-|-|  
|SQL_DESC_ALLOC_TYPE|SQL_DESC_BIND_TYPE|  
|SQL_DESC_ARRAY_SIZE|SQL_DESC_COUNT|  
|SQL_DESC_ARRAY_STATUS_PTR|SQL_DESC_ROWS_PROCESSED_PTR|  
|SQL_DESC_BIND_OFFSET_PTR||  
  
 記述子には、0 個以上の記述子レコードが含まれています。 各レコードは、列またはパラメーターの記述子の種類に応じて、について説明します。 新しい列またはパラメーターがバインドされると、新しいレコードは、記述子に追加されます。 列またはパラメーターがバインドできない場合は、レコードは、記述子から削除されます。 各レコードには、次のフィールドの 1 つのコピーが含まれています。  
  
|||  
|-|-|  
|SQL_DESC_AUTO_UNIQUE_VALUE|SQL_DESC_LOCAL_TYPE_NAME|  
|SQL_DESC_BASE_COLUMN_NAME|SQL_DESC_NAME|  
|SQL_DESC_BASE_TABLE_NAME|SQL_DESC_NULLABLE|  
|SQL_DESC_CASE_SENSITIVE|SQL_DESC_OCTET_LENGTH|  
|SQL_DESC_CATALOG_NAME|SQL_DESC_OCTET_LENGTH_PTR|  
|SQL_DESC_CONCISE_TYPE|SQL_DESC_PARAMETER_TYPE|  
|SQL_DESC_DATA_PTR|SQL_DESC_PRECISION|  
|SQL_DESC_DATETIME_INTERVAL_CODE|SQL_DESC_SCALE|  
|SQL_DESC_DATETIME_INTERVAL_PRECISION|SQL_DESC_SCHEMA_NAME|  
|SQL_DESC_DISPLAY_SIZE|SQL_DESC_SEARCHABLE|  
|SQL_DESC_FIXED_PREC_SCALE|SQL_DESC_TABLE_NAME|  
|SQL_DESC_INDICATOR_PTR|SQL_DESC_TYPE|  
|SQL_DESC_LABEL|SQL_DESC_TYPE_NAME|  
|SQL_DESC_LENGTH|SQL_DESC_UNNAMED|  
|SQL_DESC_LITERAL_PREFIX|SQL_DESC_UNSIGNED|  
|SQL_DESC_LITERAL_SUFFIX|SQL_DESC_UPDATABLE|  
  
 多くのステートメント属性は、記述子のヘッダー フィールドに対応します。 呼び出すことによってこれらの属性を設定**SQLSetStmtAttr**を呼び出して、対応する記述子のヘッダー フィールドを設定および**SQLSetDescField**同じ効果があります。 場合も同様**SQLGetStmtAttr**と**SQLGetDescField**、どちらも、同じ情報を取得します。 記述子の関数ではなくステートメントの関数を呼び出すと、記述子ハンドルを取得する必要はありませんが利点があります。  
  
 ステートメント属性を設定して、次のヘッダー フィールドを設定できます。  
  
|||  
|-|-|  
|SQL_DESC_ARRAY_SIZE|SQL_DESC_BIND_TYPE|  
|SQL_DESC_ARRAY_STATUS_PTR|SQL_DESC_ROWS_PROCESSED_PTR|  
|SQL_DESC_BIND_OFFSET_PTR||  
  
 このセクションでは、次のトピックを扱います。  
  
-   [レコード カウント](../../../odbc/reference/develop-app/record-count.md)  
  
-   [バインドされた記述子レコード](../../../odbc/reference/develop-app/bound-descriptor-records.md)  
  
-   [遅延フィールド](../../../odbc/reference/develop-app/deferred-fields.md)  
  
-   [整合性チェック](../../../odbc/reference/develop-app/consistency-check.md)
