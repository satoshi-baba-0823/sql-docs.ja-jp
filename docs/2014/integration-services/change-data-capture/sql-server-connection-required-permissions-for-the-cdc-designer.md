---
title: CDC デザイナーで使用する SQL Server 接続に必要な権限 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 946228116a33e57f118c1205bd2b4c24cb87441b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48064532"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a>CDC デザイナーで使用する SQL Server 接続に必要な権限
  CDC デザイナー コンソールのタスクを実行するには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] への接続情報が必要です。 このトピックでは、 **との接続を設定するために** [SQL Server への接続] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ダイアログ ボックスで指定できる情報について説明します。  
  
 **‭[SQL Server への接続]** ダイアログ ボックスは必要なときに開きます。たとえば、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 接続情報がない場合や、情報は存在しても接続に必要な権限がない場合などです。  
  
 次の表では、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] への接続が必要となる各種のタスクと、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ログイン/ユーザーに必要な権限について説明します。  
  
|タスク|最低限の権限|  
|----------|-------------------------|  
|関連する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスを使用した CDC サービスおよびインスタンスの一覧表示|`db_datareader` ロール|  
|CDC インスタンスの開始/停止|`db_datareader` ロールと `db_datawriter` ロール|  
|CDC インスタンスの状態の表示|`db_owner` ロール|  
|新しい Oracle CDC インスタンス データベースの作成|`dbcreator` 固定サーバー ロール|  
|新しい Oracle CDC インスタンスの作成|`db_datareader` ロール<br /><br /> `db_owner` ロール|  
|配置スクリプトの取得|`db_datareader` ロールと `db_datawriter` ロール<br /><br /> `db_owner` ロール|  
|構成の変更およびキャプチャ インスタンスの追加/削除|`db_datareader` ロールと `db_datawriter` ロール<br /><br /> `db_owner` ロール|  
  
## <a name="see-also"></a>参照  
 [CDC デザイナー コンソールへのアクセスします。](access-the-cdc-designer-console.md)   
 [インスタンスの作成のための SQL Server 接続](sql-server-connection-for-instance-creation.md)  
  
  
