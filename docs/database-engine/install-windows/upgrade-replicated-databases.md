---
title: レプリケートされたデータベースのアップグレード | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- merge replication database upgrades [SQL Server replication]
- replication [SQL Server], upgrading
- transactional replication, upgrading databases
- snapshot replication [SQL Server], upgrading databases
- upgrading replicated databases
ms.assetid: 9926a4f7-bcd8-4b9b-9dcf-5426a5857116
author: MashaMSFT
ms.author: mathoma
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
manager: craigg
ms.openlocfilehash: c92626c8ef9e24436c323819ca50c211aead9ffb
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47699740"
---
# <a name="upgrade-replicated-databases"></a>レプリケートされたデータベースのアップグレード

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  
  [!INCLUDE[ssNoversion](../../includes/ssnoversion-md.md)] では、レプリケートされたデータベースを以前のバージョンの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]からアップグレードすることができます。ノードのアップグレード中は、その他のノードでの操作を停止する必要はありません。 トポロジでサポートされるバージョンに関して、以下の規則が守られていることを確認してください。  
  
-   ディストリビューターは、パブリッシャーのバージョン以上であればどのバージョンでも使用できます (多くの場合、ディストリビューターはパブリッシャーと同じインスタンスです)。  
  
-   パブリッシャーは、ディストリビューターのバージョン以下であればどのバージョンでも使用できます。  
  
-   サブスクライバーのバージョンは、次のように、パブリケーションの種類によって異なります。  
  
    -   トランザクション パブリケーションのサブスクライバーは、2 つのパブリッシャー バージョンのうちどちらでも使用できます。 たとえば、 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] のパブリッシャーには [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] と [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] のサブスクライバーを設定することができます。 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] のパブリッシャーには [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] と  [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] のサブスクライバーを設定することができます。  
  
    -   マージ パブリケーションのサブスクライバーは、パブリッシャーのバージョン以下であればどのバージョンでも使用できます。  
  
> [!NOTE]  
>  この記事は、セットアップ ヘルプ ドキュメントおよび [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] オンライン ブックで参照できます。 セットアップ ヘルプ ドキュメントで太字で表示されている記事のリンクは、オンライン ブックでのみ参照可能な記事を示しています。 **パブリッシャー、サブスクライバー、およびディストリビューターのアップグレード戦略は、こちらの[記事](https://blogs.msdn.microsoft.com/sql_server_team/upgrading-a-replication-topology-to-sql-server-2016/)** に記載されているオプションを使用して設計できます。 
  
## <a name="run-the-log-reader-agent-for-transactional-replication-before-upgrade"></a>アップグレードの前にトランザクション レプリケーション用にログ リーダー エージェントを実行する方法  
 [!INCLUDE[ssNoversion](../../includes/ssnoversion-md.md)] をアップグレードする前に、パブリッシュされたテーブルからコミットされたすべてのトランザクションが、ログ リーダー エージェントによって処理されているかどうかを確認する必要があります。 すべてのトランザクションが処理されたことを確認するには、トランザクション パブリケーションを含んだ各データベースに対して次の手順を実行します。  
  
1.  データベースのログ リーダー エージェントが実行されていることを確認します。 既定では、エージェントは継続的に実行されています。  
  
2.  パブリッシュされたテーブル上のユーザー アクティビティを停止します。  
  
3.  トランザクションをディストリビューション データベースにコピーする時間をログ リーダー エージェントに与えてから、エージェントを停止します。  
  
4.  [sp_replcmds](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md) を実行し、すべてのトランザクションが処理されたことを確認します。 この手順の結果セットを空にする必要があります。  
  
5.  [sp_replflush](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md) を実行し、sp_replcmds から接続を閉じます。  
  
6.  最新バージョンの [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)] へのサーバー アップグレードを実行します。  
  
7.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントとログ リーダー エージェントがアップグレードの後に自動的に起動しない場合は、これらを再起動します。  
  
## <a name="run-agents-for-merge-replication-after-upgrade"></a>アップグレード後のマージ レプリケーション用エージェントの実行  
 アップグレード後は、マージ パブリケーションごとにスナップショット エージェントを実行し、サブスクリプションごとにマージ エージェントを実行して、レプリケーション メタデータを更新します。 サブスクリプションを再初期化する必要がないので、新しいスナップショットを適用する必要はありません。 サブスクリプション メタデータは、アップグレード後に最初にマージ エージェントを実行したときに更新されます。 そのため、サブスクリプション データベースは、パブリッシャーのアップグレード中にオンライン状態でアクティブなままにすることができます。  
  
 マージ レプリケーションでは、パブリケーション データベースおよびサブスクリプション データベース内の多数のシステム テーブルに、パブリケーション メタデータおよびサブスクリプション メタデータが格納されます。 スナップショット エージェントを実行すると、パブリケーション メタデータが更新され、マージ エージェントを実行すると、サブスクリプション メタデータが更新されます。 生成が必要なのはパブリケーション スナップショットのみです。 パラメーター化されたフィルターがマージ パブリケーションで使用される場合は、各パーティションにもスナップショットが必要です。 これらのパーティション スナップショットを更新する必要はありません  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]、レプリケーション モニター、またはコマンド ラインで各エージェントを実行します。 スナップショット エージェントの実行について詳しくは、次の記事をご覧ください。  
  
-   [初期スナップショットの作成および適用](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [レプリケーション エージェントを起動および停止する &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)  
  
-   [初期スナップショットの作成および適用](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [レプリケーション エージェント実行可能ファイルの概念](../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)  
  
 マージ エージェントの実行について詳しくは、次の記事をご覧ください。  
  
-   [プル サブスクリプションの同期](../../relational-databases/replication/synchronize-a-pull-subscription.md)  
  
-   [プッシュ サブスクリプションの同期](../../relational-databases/replication/synchronize-a-push-subscription.md)  
  
 マージ レプリケーションを使用するトポロジで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] をアップグレードした後に、新しい機能を使用する場合は、すべてのパブリケーションのパブリケーション互換性レベルを変更します。  
  
## <a name="upgrading-to-standard-workgroup-or-express-editions"></a>Standard Edition、Workgroup Edition、または Express Edition へのアップグレード  
 [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)] のいずれかのエディションから別のエディションへアップグレードする前に、現在使用している機能がアップグレード先のエディションでサポートされているかどうかを確認します。 詳細については、[SQL Server の各エディションとサポートされる機能](../../sql-server/editions-and-components-of-sql-server-2017.md)に関するページのレプリケーションのセクションをご覧ください。  
  
## <a name="web-synchronization-for-merge-replication"></a>マージ レプリケーションの Web 同期  
 マージ レプリケーションの Web 同期オプションでは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] レプリケーション リスナー (replisapi.dll) を、同期に使用するインターネット インフォメーション サービス (IIS) サーバーの仮想ディレクトリにコピーする必要があります。 Web 同期を構成すると、Web 同期の構成ウィザードにより、ファイルが仮想ディレクトリにコピーされます。 IIS サーバーにインストールされた [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] コンポーネントをアップグレードする場合、replisapi.dll を COM ディレクトリから IIS サーバーの仮想ディレクトリへ手動でコピーする必要があります。 Web 同期の構成の詳細については、「 [Web 同期の構成](../../relational-databases/replication/configure-web-synchronization.md)」を参照してください。  
  
## <a name="restoring-a-replicated-database-from-an-earlier-version"></a>以前のバージョンからレプリケートされたデータベースの復元  
 以前のバージョンからレプリケートされたデータベースのバックアップを復元するときにレプリケーション設定が保持されるようにするには、バックアップが作成されたサーバーおよびデータベースと同じ名前のサーバーおよびデータベースに復元します。  
  
## <a name="see-also"></a>参照  
 [管理 &#40;レプリケーション&#41;](../../relational-databases/replication/administration/administration-replication.md)   
 [レプリケーションの下位互換性](../../relational-databases/replication/replication-backward-compatibility.md)   
 [新機能 &#40;レプリケーション&#41;](../../relational-databases/replication/what-s-new-replication.md)   
 [サポートされているバージョンとエディションのアップグレード](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)   
 [SQL Server のアップグレード](../../database-engine/install-windows/upgrade-sql-server.md)  
  
  
