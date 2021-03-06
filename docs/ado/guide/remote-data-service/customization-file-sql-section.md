---
title: カスタマイズ ファイルの SQL セクション |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL section in RDS [ADO]
- customization file in RDS [ADO]
ms.assetid: e65c2871-9986-44ff-b8b7-7f5eda91b3fa
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 36f6eec4b8203848dc6f4b8c99597f22c9cedeab
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47625880"
---
# <a name="customization-file-sql-section"></a>カスタマイズ ファイルの SQL セクション
**Sql**セクションは、クライアントのコマンド文字列を置換する新しい SQL 文字列を含めることができます。 セクション内に SQL 文字列がない場合は、セクションは無視されます。  
  
> [!IMPORTANT]
>  Windows 8 および Windows Server 2012 以降、RDS サーバー コンポーネントに含まれていない、Windows オペレーティング システム (Windows 8 を参照してくださいと[Windows Server 2012 の互換性クックブック](https://www.microsoft.com/en-us/download/details.aspx?id=27416)の詳細)。 RDS クライアント コンポーネントは、Windows の将来のバージョンで削除されます。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションに移行する必要があります[WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565)します。  
  
 新しい SQL 文字列がある*パラメーター化された*します。 内のパラメーターは、 **sql** SQL 文字列のセクション (で指定された、' ですか?' 文字) に対応する引数を置き換え、*識別子*クライアントのコマンド文字列で (によって指定された、コンマ区切りリストをかっこで)。 識別子と引数リストは、関数呼び出しのように動作します。  
  
 たとえば、クライアントのコマンド文字列は`"CustomerByID(4)"`、SQL セクション ヘッダーが`[SQL CustomerByID]`、新しい SQL セクション文字列は`"SELECT * FROM Customers WHERE CustomerID = ?".`、ハンドラーが生成されます`"SELECT * FROM Customers WHERE CustomerID = 4"`し、その文字列を使用して、データ ソースのクエリにします。  
  
 新しい SQL ステートメントが null の文字列の場合 ("") のセクションは無視されます。  
  
 新しい SQL ステートメントの文字列が有効でない場合は、ステートメントの実行は失敗します。 クライアントのパラメーターは無視されます。 指定することで、クライアントのすべての SQL コマンドを「オフにする」に意図的にこれを行うことができます。  
  
```  
[SQL default]   
SQL = " "  
```  
  
## <a name="syntax"></a>構文  
 形式は、交換用の SQL 文字列を入力します。  
  
 **SQL=**   
 ***sqlString***  
  
|要素|説明|  
|----------|-----------------|  
|**SQL**|これを示すリテラル文字列は、SQL セクション エントリです。|  
|***sqlString***|クライアントの文字列を置換する SQL 文字列です。|  
  
## <a name="see-also"></a>参照  
 [カスタマイズ ファイル Connect セクション](../../../ado/guide/remote-data-service/customization-file-connect-section.md)   
 [カスタマイズ ファイル Logs セクション](../../../ado/guide/remote-data-service/customization-file-logs-section.md)   
 [カスタマイズ ファイル UserList セクション](../../../ado/guide/remote-data-service/customization-file-userlist-section.md)   
 [DataFactory のカスタマイズ](../../../ado/guide/remote-data-service/datafactory-customization.md)   
 [必要なクライアント設定](../../../ado/guide/remote-data-service/required-client-settings.md)   
 [カスタマイズ ファイルの概要](../../../ado/guide/remote-data-service/understanding-the-customization-file.md)   
 [独自のカスタム ハンドラーの記述](../../../ado/guide/remote-data-service/writing-your-own-customized-handler.md)


