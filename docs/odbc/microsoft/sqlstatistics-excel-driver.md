---
title: SQLStatistics (Excel ドライバー) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- Excel driver [ODBC], SQLStatistics
- SQLStatistics function [ODBC], Excel Driver
ms.assetid: 02506664-8dcc-4bd0-a8bb-d49fcbdd5722
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 044ea7e2c536685afef3534eacb5745fb33edf49
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47619410"
---
# <a name="sqlstatistics-excel-driver"></a>SQLStatistics (Excel ドライバー)
> [!NOTE]  
>  このトピックでは、Excel ドライバー固有の情報を提供します。 この関数の詳細については、該当するトピックを参照してください。 [ODBC API リファレンス](../../odbc/reference/syntax/odbc-api-reference.md)します。  
  
|[列]|コメント|  
|------------|--------------|  
|TABLE_QUALIFIER|ディレクトリへのパス。<br /><br /> パターン マッチングはではサポートされていません、 *szTableQualifier*引数。|  
|TABLE_OWNER|所有者名がサポートされていないために、この列で NULL が返されます。|  
|TABLE_NAME|区切りのないテーブルの名前。<br /><br /> パターン マッチングはではサポートされていません、 *szTableName*引数。|  
|INDEX_QUALIFIER|NULL は常に返されます。|  
|INDEX_NAME|インデックスに依存します。|  
|TYPE|型の SQL_TABLE_STAT または SQL_INDEX_OTHER のみが返されます。|  
|SEQ_IN_INDEX|インデックスに依存します。|  
|COLUMN_NAME|インデックスに依存します。|  
|COLLATION|インデックスに依存します。|  
|PAGES|NULL は常に返されます。|  
  
 一意性に基づくフィルター処理は、(、 *fUnique*引数)。 *FAccuracy*パラメーターは無視されます。
