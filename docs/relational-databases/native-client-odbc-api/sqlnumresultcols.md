---
title: SQLNumResultCols |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: b240a9f9e2aa31ac40d134220d12711775008e0d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47683370"
---
# <a name="sqlnumresultcols"></a>SQLNumResultCols
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  実行されるステートメントを[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native Client ODBC ドライバーは結果セット内の列の数を報告するサーバーを利用しません。 この場合、 **SQLNumResultCols**サーバーとのやり取りは行われません。 ような[SQLDescribeCol](../../relational-databases/native-client-odbc-api/sqldescribecol.md)と[SQLColAttribute](../../relational-databases/native-client-odbc-api/sqlcolattribute.md)を呼び出すと、 **SQLNumResultCols**準備されていても実行されていないステートメントには、サーバーとのやり取りが生成されます。  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] ステートメントまたはステートメント バッチが複数の結果行セットを返すときは、結果セットの列数を報告する場合、あるセットから別のセットへ結果セットを変更することができます。 **SQLNumResultCols**セットごとに呼び出す必要があります。 列数が変化すると、アプリケーションでは行の結果をフェッチする前に、データ値を再バインドする必要があります。 セットを返す複数の結果の処理の詳細についてを参照してください[SQLMoreResults](../../relational-databases/native-client-odbc-api/sqlmoreresults.md)します。  
  
 以降では、データベース エンジンの機能強化[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]期待どおりの結果のより正確な記述を取得する SQLNumResultCols を許可します。 これらのより正確な結果の以前のバージョンの SQLNumResultCols によって返される値が異なる場合があります[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]します。 詳細については、次を参照してください。[メタデータ検出](../../relational-databases/native-client/features/metadata-discovery.md)します。  
  
## <a name="see-also"></a>参照  
 [SQLNumResultCols 関数](http://go.microsoft.com/fwlink/?LinkId=59359)   
 [ODBC API 実装の詳細](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
