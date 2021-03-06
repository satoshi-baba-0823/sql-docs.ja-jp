---
title: SSMA for DB2 コンポーネント (DB2ToSQL) の削除 |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 4ee0d698-6246-48eb-b963-d62be81cab6a
caps.latest.revision: 6
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 6f93ca145c96e2cc9b6d86e0ebc8c2c9899afad9
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "40393626"
---
# <a name="removing-ssma-for-db2-components-db2tosql"></a>SSMA for DB2 コンポーネント (DB2ToSQL) の削除
終了したらを DB2 からデータベースを移行する[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、SSMA コンポーネントをアンインストールしたい場合があります。 クライアント コンポーネントは、いつでもアンインストールできます。 ただしから拡張機能パックをアンインストールする必要がありますいない[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、移行されたデータベースが不要になった内の関数を使用しない限り、 **ssma_DB2**のスキーマ、 **sysdb**データベース。  
  
## <a name="uninstalling-the-ssma-for-db2-client"></a>SSMA を DB2 クライアントのアンインストール  
SSMA をアンインストールするにを使用して**プログラム追加と削除**します。  
  
**SSMA をアンインストールするには**  
  
1.  コントロール パネルで、開く**プログラム追加と削除**します。  
  
2.  選択 **[!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Migration Assistant for DB2**、 をクリックし、**削除**します。  
  
3.  SSMA をアンインストールすることを確認するには、次のようにクリックします。**はい**します。  
  
## <a name="uninstalling-the-extension-pack"></a>拡張機能パックをアンインストールします。  
データベースを移行は、内のオブジェクトを使用しない場合は、確認、 **sysdb.ssma_DB2**スキーマ、スキーマから削除することによって、拡張機能パックを削除する – Windows アンインストールはありませんが  
  
## <a name="see-also"></a>参照  
[SSMA for DB2 クライアントのインストール&#40;DB2ToSQL&#41;](../../ssma/db2/installing-ssma-for-db2-client-db2tosql.md)  
[SQL Server での SSMA コンポーネントのインストール&#40;DB2ToSQL&#41;](../../ssma/db2/installing-ssma-components-on-sql-server-db2tosql.md)  
  
