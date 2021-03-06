---
title: シングル ユーザー モードでの SQL Server の起動 | Microsoft Docs
ms.custom: ''
ms.date: 09/20/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server, single-user mode
- single-user mode [SQL Server]
ms.assetid: 72eb4fc1-7af4-4ec6-9e02-11a69e02748e
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: c6b4f895b265b47c82e39f6f6d4641ebb4962881
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47821250"
---
# <a name="start-sql-server-in-single-user-mode"></a>シングル ユーザー モードでの SQL Server の起動
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  特定の状況では、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup option -m **を使用して、** のインスタンスをシングル ユーザー モードで起動する必要が生じる場合があります。 たとえば、サーバーの構成オプションを変更したり、破損した master データベースや他のシステム データベースを復旧したりすることがあります。 いずれの場合も、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスをシングル ユーザー モードで起動する必要があります。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] をシングル ユーザー モードで起動すると、コンピューターのローカル Administrators グループのメンバーはすべて、固定サーバー ロール sysadmin のメンバーとして [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスに接続できるようになります。 詳細については、「 [システム管理者がロックアウトされた場合の SQL Server への接続](../../database-engine/configure-windows/connect-to-sql-server-when-system-administrators-are-locked-out.md)」を参照してください。  
  
 シングル ユーザー モードで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスを起動する場合は、次の点に注意してください。  
  
-   1 人のユーザーのみがサーバーに接続できます。  
  
-   CHECKPOINT プロセスは実行されません。 既定では、このプロセスは、起動時に自動的に実行されます。  
  
> [!NOTE]  
>  シングル ユーザー モードの場合、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスに接続する前に [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスを停止してください。そうしないと、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスによってその接続が使用されるため、SQL Server のインスタンスがブロックされます。  
  
シングル ユーザー モードで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスを起動すると、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] で [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]に接続できます。 [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] のオブジェクト エクスプローラーでは、一部の操作で複数の接続が必要になるため失敗することがあります。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] をシングル ユーザー モードで管理するには、 [!INCLUDE[tsql](../../includes/tsql-md.md)] のクエリ エディターのみを介して接続することにより [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]ステートメントを実行するか、 [sqlcmd ユーティリティ](../../tools/sqlcmd-utility.md)を使用します。  
  
**SQLCMD** または [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] で **-m** オプションを使用すると、接続を特定のクライアント アプリケーションに限定できます。 

> [!NOTE]
> Linux では、**SQLCMD** は、このように大文字で入力する必要があります。

たとえば、**-m"SQLCMD"** を使用すると、接続が、**SQLCMD** クライアント プログラムとして識別される必要がある単一の接続に限定されます。 このオプションは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] をシングル ユーザー モードで起動するときに、その唯一の接続を不明なクライアント アプリケーションによって使用されていた場合に使用します。 [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]のクエリ エディターを使用して接続するには、 **-m"Microsoft SQL Server Management Studio - Query"** を使用します。  
  
> [!IMPORTANT]  
>  このオプションをセキュリティ機能として使用しないでください。 クライアント アプリケーションの名前はクライアント アプリケーションによって接続文字列の一部として指定されるため、本当の名前が指定されるとは限りません。  
  
## <a name="note-for-clustered-installations"></a>クラスター化インストールに関する注意  
 クラスター環境に [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] をインストールした場合、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] をシングル ユーザー モードで起動すると、利用可能な接続がクラスター リソースの dll によって占有され、サーバーに対する他の接続がブロックされます。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] がこの状態に陥ると、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントのリソースをオンラインに戻そうとしたときに、SQL のリソースが別のノードにフェールオーバーされる可能性があります (リソースがそのグループに影響するように構成されていた場合)。  
  
 この問題を回避するには、次の手順に従います。  
  
1.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の詳細プロパティから起動時のパラメーター –m を削除します。  
  
2.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] リソースをオフラインにします。  
  
3.  このグループの現在の所有者ノードのコマンド プロンプトで、次のコマンドを発行します:  
    net start MSSQLSERVER /m  
  
4.  クラスター アドミニストレーターまたはフェールオーバー クラスター管理コンソールから、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] リソースがまだオフライン状態にあるかどうかを確認します。  
  
5.  ここで、次のコマンドを使用して [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] に接続し、必要な操作を行います: SQLCMD -E -S\<servername>  
  
6.  操作が完了したら、コマンド プロンプトを閉じ、クラスター アドミニストレーターから SQL および他のリソースをオンラインに戻します。  
  
## <a name="see-also"></a>参照  
 [SQL Server エージェント サービスの開始、停止、または一時停止](http://msdn.microsoft.com/library/c95a9759-dd30-4ab6-9ab0-087bb3bfb97c)   
 [データベース管理者用の診断接続](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)   
 [sqlcmd ユーティリティ](../../tools/sqlcmd-utility.md)   
 [CHECKPOINT &#40;Transact-SQL&#41;](../../t-sql/language-elements/checkpoint-transact-sql.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [データベース エンジン サービスのスタートアップ オプション](../../database-engine/configure-windows/database-engine-service-startup-options.md)  
  
  
