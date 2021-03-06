---
title: RDS オブジェクト モデルの概要 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS objects [ADO], object model summary
- RDS object model [ADO]
ms.assetid: 909f9af7-31db-4eec-ad52-650ce74dac2f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0421f5eead03d6e3641054b9c26dc1d4dac838e6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47822132"
---
# <a name="rds-object-model-summary"></a>RDS オブジェクト モデルの概要
> [!IMPORTANT]
>  Windows 8 および Windows Server 2012 以降、RDS サーバー コンポーネントに含まれていない、Windows オペレーティング システム (Windows 8 を参照してくださいと[Windows Server 2012 の互換性クックブック](https://www.microsoft.com/en-us/download/details.aspx?id=27416)の詳細)。 RDS クライアント コンポーネントは、Windows の将来のバージョンで削除されます。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションに移行する必要があります[WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565)します。  
  
|オブジェクト|説明|  
|------------|-----------------|  
|[RDS.DataSpace](../../../ado/reference/rds-api/dataspace-object-rds.md)|このオブジェクトには、サーバーのプロキシを取得するメソッドが含まれています。 プロキシは、既定またはカスタムのサーバー プログラム (ビジネス オブジェクト) にあります。 サーバーのプログラムは、インターネット、イントラネット、ローカル エリア ネットワークで呼び出すことがでもローカル ダイナミック リンク ライブラリです。<br /><br /> **DataSpace**オブジェクトがスクリプトを実行します。|  
|[RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)|このオブジェクトは、既定のサーバー プログラムを表します。 既定の RDS のデータの取得と更新動作を実行します。<br /><br /> **DataFactory**オブジェクトは、スクリプトを実行することはありません。|  
|[RDS.DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)|このオブジェクトは自動的に呼び出すことができます、 **rds.DataSpace**と**RDSServer.DataFactory**オブジェクト。<br /><br /> このオブジェクトを使用して、既定の RDS のデータの取得や更新プログラムの動作を呼び出します。<br /><br /> このオブジェクトは、ビジュアル コントロールへのアクセス、返されたにするための手段も用意されています。 **Recordset**オブジェクト。<br /><br /> **DataControl**オブジェクトがスクリプトを実行します。|  
  
## <a name="see-also"></a>参照  
 [RDS の基礎](../../../ado/guide/remote-data-service/rds-fundamentals.md)   
 [RDS のシナリオ](../../../ado/guide/remote-data-service/rds-scenario.md)   
 [RDS チュートリアル](../../../ado/guide/remote-data-service/rds-tutorial.md)   
 [RDS の使用方法とセキュリティ](../../../ado/guide/remote-data-service/rds-usage-and-security.md)


