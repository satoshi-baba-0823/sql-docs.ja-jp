---
title: '手順 2: サーバー プログラム (RDS チュートリアル) を呼び出す |Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS tutorial [ADO], invoking server program
ms.assetid: 5e74c2da-65ee-4de4-8b41-6eac45c3632e
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0a2e7b62276234dcf11067395ff2512a8e93af96
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47800510"
---
# <a name="step-2-invoke-the-server-program-rds-tutorial"></a>手順 2: サーバー プログラムを呼び出す (RDS チュートリアル)
クライアント上のメソッドを呼び出すと*プロキシ*サーバー上の実際のプログラムは、メソッドを実行します。 この手順では、サーバーでクエリを実行します。  
  
> [!IMPORTANT]
>  Windows 8 および Windows Server 2012 以降、RDS サーバー コンポーネントに含まれていない、Windows オペレーティング システム (Windows 8 を参照してくださいと[Windows Server 2012 の互換性クックブック](https://www.microsoft.com/en-us/download/details.aspx?id=27416)の詳細)。 RDS クライアント コンポーネントは、Windows の将来のバージョンで削除されます。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションに移行する必要があります[WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565)します。  
  
 **パート A**を使用していない場合[RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)でこのチュートリアルでは、この手順を実行する最も簡単な方法は使用すること、 [rds.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)オブジェクト。 **Rds.DataControl**プロキシを作成するこの手順でクエリを発行の前の手順を結合します。  
  
 設定、 **rds.DataControl**オブジェクト[Server](../../../ado/reference/rds-api/server-property-rds.md)場所サーバー プログラムをインスタンス化する必要があります使用するには、 [Connect](../../../ado/reference/rds-api/connect-property-rds.md) ; データ ソースへのアクセスへの接続文字列を指定するプロパティと。[SQL](../../../ado/reference/rds-api/sql-property.md)プロパティをクエリ コマンド テキストを指定します。 続いて、[更新](../../../ado/reference/rds-api/refresh-method-rds.md)サーバー プログラムのデータ ソースへの接続、クエリで指定された行を取得して返すメソッドを**レコード セット**クライアントにオブジェクト。  
  
 このチュートリアルでは使用しません、 **rds.DataControl**がどのようにした場合の外観は。  
  
```  
Sub RDSTutorial2A()  
   Dim DC as New RDS.DataControl  
   DC.Server = "http://yourServer"  
   DC.Connect = "DSN=Pubs"  
   DC.SQL = "SELECT * FROM Authors"  
   DC.Refresh  
...  
```  
  
 チュートリアルを呼び出す RDS、ADO オブジェクトとがどのようにした場合の外観になります。  
  
```  
Dim rs as New ADODB.Recordset  
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _  
        "Remote Server=http://yourServer;Remote Provider=SQLOLEDB;"  
```  
  
 **パート B**のこの手順を実行する一般的な方法を呼び出す、 **RDSServer.DataFactory**オブジェクト[クエリ](../../../ado/reference/rds-api/query-method-rds.md)メソッド。 このメソッドにはデータ ソースへの接続に使用される、接続文字列であり、コマンド テキスト、データ ソースから返される行を指定するために使用します。  
  
 このチュートリアルでは、 **DataFactory**オブジェクト**クエリ**メソッド。  
  
```  
Sub RDSTutorial2B()  
   Dim DS as New RDS.DataSpace  
   Dim DF  
   Dim RS as ADODB.Recordset  
   Set DF = DS.CreateObject("RDSServer.DataFactory", "http://yourServer")  
   Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors")  
...  
```  
  
## <a name="see-also"></a>参照  
 [手順 3: サーバーは、レコード セット (RDS チュートリアル) を取得します。](../../../ado/guide/remote-data-service/step-3-server-obtains-a-recordset-rds-tutorial.md)   
 [RDS のチュートリアル (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
