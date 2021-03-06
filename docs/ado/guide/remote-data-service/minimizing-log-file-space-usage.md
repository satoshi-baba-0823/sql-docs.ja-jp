---
title: ログ ファイル領域使用量を最小限に抑える |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- log file space in RDS [ADO]
ms.assetid: 669662a0-e20f-483e-ab28-53f66c524c98
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 39daf1dd4b3f97628bed17377e7d11f7ecc9c725
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47714470"
---
# <a name="minimizing-log-file-space-usage"></a>ログ ファイルの使用領域の最小化
ログ ファイルがすぐにいっぱい (サーバーが停止するため)、SQL Server データベースでのアクティビティ量が多い場合。 ログ ファイルを設定する**チェックポイントに Truncate**データベースのログ ファイルの有効期間を大幅に拡張します。  
  
> [!IMPORTANT]
>  Windows 8 および Windows Server 2012 以降、RDS サーバー コンポーネントに含まれていない、Windows オペレーティング システム (Windows 8 を参照してくださいと[Windows Server 2012 の互換性クックブック](https://www.microsoft.com/en-us/download/details.aspx?id=27416)の詳細)。 RDS クライアント コンポーネントは、Windows の将来のバージョンで削除されます。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションに移行する必要があります[WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565)します。  
  
### <a name="to-enable-truncate-on-checkpoint-in-microsoft-sql-server-65"></a>Microsoft SQL Server 6.5 のチェックポイントの切り捨てを有効にするには  
  
1.  Microsoft SQL Server Enterprise Manager を起動、サーバーのツリーをオープンし、データベース デバイス ツリーを開きます。  
  
2.  この機能を有効にするデータベースの名前をダブルクリックします。  
  
3.  **データベース**] タブで [ **Truncate**します。  
  
4.  **オプション**] タブで [**チェックポイントのログを切り捨てる**、順にクリックします**OK**します。  
  
### <a name="to-enable-truncate-on-checkpoint-in-microsoft-sql-server-70"></a>Microsoft SQL Server 7.0 でのチェックポイントの切り捨てを有効にするには  
  
1.  Microsoft SQL Server Enterprise Manager を起動、サーバーのツリーをオープンし、データベース ツリーを開きます。  
  
2.  この機能を有効になります、選択は、データベースの名前を右クリックして**プロパティ**します。  
  
3.  **オプション**] タブで [**チェックポイントのログを切り捨てる**、順にクリックします**OK**します。  
  
 詳細については、**チェックポイントに Truncate**機能、Microsoft SQL Server のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [RDS の基礎](../../../ado/guide/remote-data-service/rds-fundamentals.md)


