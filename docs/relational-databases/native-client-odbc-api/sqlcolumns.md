---
title: SQLColumns |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLColumns function
ms.assetid: 69d3af44-8196-43ab-8037-cdd06207b171
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f6117efa06effea24fda8fac4c1567bbe8a6c390
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47697770"
---
# <a name="sqlcolumns"></a>SQLColumns
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  **SQLColumns**値が存在するかどうかに関係なく SQL_SUCCESS を返します、 *CatalogName*、 *TableName*、または*ColumnName*パラメーター。 **SQLFetch** SQL_NO_DATA が返されるこれらのパラメーターに無効な値を使用する場合。  
  
> [!NOTE]  
>  大きな値型の場合、すべての長さパラメーターが SQL_SS_LENGTH_UNLIMITED という値で返されます。  
  
 **SQLColumns**静的サーバー カーソルで実行できます。 実行しようとすると、 **SQLColumns**更新可能な (動的またはキーセット) カーソルでは、カーソルの種類が変更されたことを示す SQL_SUCCESS_WITH_INFO を返します。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーでは、リンク サーバー上のテーブルに関する情報のレポートをサポートの 2 つの部分名をそのまま使用して、 *CatalogName*パラメーター: *Linked_Server_Name.Catalog_Name*.  
  
 ODBC 2。*x*でワイルドカードを使用していないアプリケーション*TableName*、 **SQLColumns**テーブルの名前が一致をに関する情報を返します*TableName*、現在のユーザーによって所有されているとします。 現在のユーザーに名前が一致するテーブルが所有していないかどうか、 *TableName*パラメーター、 **SQLColumns**テーブル名が一致する他のユーザーによって所有されているすべてのテーブルに関する情報を返します、 *TableName*パラメーター。 ODBC 2。*x* 、ワイルドカードを使用してアプリケーション**SQLColumns**すべて名前と一致するテーブルを返します*TableName*します。 ODBC 3。*x*アプリケーション**SQLColumns**すべて名前と一致するテーブルを返します*TableName*所有者またはワイルドカードを使用するかどうかに関係なく。  
  
 次の表は、結果セットによって返される列の一覧です。  
  
|列名|説明|  
|-----------------|-----------------|  
|DATA_TYPE|SQL_VARCHAR、SQL_VARBINARY、または SQL_WVARCHAR を返します、 **varchar (max)** データ型。|  
|TYPE_NAME|"Varchar"、"varbinary"または"nvarchar"を返します、 **varchar (max)**、 **varbinary (max)**、および**nvarchar (max)** データ型。|  
|COLUMN_SIZE|SQL_SS_LENGTH_UNLIMITED を返します**varchar (max)** 列のサイズが制限されることを示すデータ型。|  
|BUFFER_LENGTH|SQL_SS_LENGTH_UNLIMITED を返します**varchar (max)** バッファーのサイズが制限されることを示すデータ型。|  
|SQL_DATA_TYPE|SQL_VARCHAR、SQL_VARBINARY、または SQL_WVARCHAR を返します、 **varchar (max)** データ型。|  
|CHAR_OCTET_LENGTH|char 型または binary 型の列の最大長を返します。 サイズが無制限であることを示す場合は 0 を返します。|  
|SS_XML_SCHEMACOLLECTION_CATALOG_NAME|XML スキーマ コレクション名が定義されているカタログの名前を返します。 カタログ名が見つからない場合は、この変数に空文字列が含まれます。|  
|SS_XML_SCHEMACOLLECTION_SCHEMA_NAME|XML スキーマ コレクション名が定義されているスキーマの名前を返します。 スキーマ名が見つからない場合は、この変数に空文字列が含まれます。|  
|SS_XML_SCHEMACOLLECTION_NAME|XML スキーマ コレクションの名前を返します。 名前が見つからない場合は、この変数に空文字列が含まれます。|  
|SS_UDT_CATALOG_NAME|UDT (ユーザー定義型) を含むカタログの名前です。|  
|SS_UDT_SCHEMA_NAME|UDT を含むスキーマの名前。|  
|SS_UDT_ASSEMBLY_TYPE_NAME|UDT のアセンブリ修飾名です。|  
  
 Udt の場合、既存の TYPE_NAME 列は、;、UDT の名前を示す使用します。したがって新しい列は追加されませんの結果セットに**SQLColumns**または[SQLProcedureColumns](../../relational-databases/native-client-odbc-api/sqlprocedurecolumns.md)します。 UDT 列または UDT パラメーターの場合、DATA_TYPE は SQL_SS_UDT です。  
  
 サーバーからパラメーターの UDT に関する追加のメタデータ プロパティを返したり、サーバーでこのメタデータ プロパティの情報が必要となる場合は、上記に定義したドライバー固有の新しい記述子を使用して、UDT のメタデータ プロパティの取得や設定を行えます。  
  
 クライアントが接続する[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]カタログ入力パラメーターは、他のカタログから情報を返しませんの値を NULL またはワイルドカードを使用して、SQLColumns を呼び出すとします。 代わりに、現在のカタログに関する情報だけが返されます。 クライアントでは、どのカタログでは、目的のテーブルがあるかを判断する SQLTables を呼び出すことができます最初。 クライアントはそのカタログの値をそのテーブル内の列に関する情報を取得するのに SQLColumns の呼び出しでカタログ入力パラメーターを使用し、できます。  
  
## <a name="sqlcolumns-and-table-valued-parameters"></a>SQLColumns とテーブル値パラメーター  
 SQLColumns によって返される結果セットは、SQL_SOPT_SS_NAME_SCOPE の設定に依存します。 詳細については、次を参照してください。 [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md)します。 テーブル値パラメーター用に次の列が追加されました。  
  
|列名|データ型|目次|  
|-----------------|---------------|--------------|  
|SS_IS_COMPUTED|Smallint|TABLE_TYPE の列では、列が計算列の場合は SQL_TRUE、それ以外の場合は SQL_FALSE になります。|  
|SS_IS_IDENTITY|Smallint|列が ID 列の場合は SQL_TRUE、それ以外の場合は SQL_FALSE になります。|  
  
 テーブル値パラメーターの詳細については、次を参照してください。[テーブル値パラメーター &#40;ODBC&#41;](../../relational-databases/native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)します。  
  
## <a name="sqlcolumns-support-for-enhanced-date-and-time-features"></a>SQLColumns による機能強化された日付と時刻のサポート  
 日付/時刻型に対して返される値については、次を参照してください。[カタログ メタデータ](../../relational-databases/native-client-odbc-date-time/metadata-catalog.md)します。  
  
 詳細については、次を参照してください。[日付と時刻の強化&#40;ODBC&#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md)します。  
  
## <a name="sqlcolumns-support-for-large-clr-udts"></a>SQLColumns による大きな CLR UDT のサポート  
 **SQLColumns**大きなの CLR ユーザー定義型 (Udt) をサポートしています。 詳細については、次を参照してください。 [Large CLR User-Defined 型&#40;ODBC&#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md)します。  
  
## <a name="sqlcolumns-support-for-sparse-columns"></a>SQLColumns によるスパース列のサポート  
 2 つ[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]SQLColumns の結果セットに特定の列が追加されています。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|SS_IS_SPARSE|**smallint**|列がスパース列の場合は SQL_TRUE、それ以外の場合は SQL_FALSE になります。|  
|SS_IS_COLUMN_SET|**smallint**|列の場合、 **column_set**列は SQL_TRUE、それ以外の sql_false になります。|  
  
 SS_IS_SPARSE と SS_IS_COLUMN_SET が前に追加されたすべてのドライバー固有の列の表示には、ODBC 仕様に準拠[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]バージョンよりも前[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]と後、すべての列が ODBC 自体によって指定します。  
  
 SQLColumns によって返される結果セットは、SQL_SOPT_SS_NAME_SCOPE の設定に依存します。 詳細については、次を参照してください。 [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md)します。  
  
 ODBC のスパース列の詳細については、次を参照してください。[スパース列のサポート&#40;ODBC&#41;](../../relational-databases/native-client/odbc/sparse-columns-support-odbc.md)します。  
  
## <a name="see-also"></a>参照  
 [SQLColumns 関数](http://go.microsoft.com/fwlink/?LinkId=59336)   
 [ODBC API 実装の詳細](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
