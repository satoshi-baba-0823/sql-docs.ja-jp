---
title: SQL Server のビッグ データ クラスター コント ローラーとは何ですか。 | Microsoft Docs
description: ''
author: mihaelablendea
ms.author: mihaelab
manager: craigg
ms.date: 10/01/2018
ms.topic: conceptual
ms.prod: sql
ms.openlocfilehash: 6b3a8f01170fecf21fd85dbb2d85d228430fc100
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48796309"
---
# <a name="what-is-the-sql-server-big-data-clusters-controller"></a>SQL Server のビッグ データ クラスター コント ローラーとは何ですか。

コント ローラーは、展開、およびビッグ データ クラスターを管理するためのコア ロジックをホストします。 Kubernetes では、クラスターおよび Spark、HDFS などの他のコンポーネントの一部である SQL Server インスタンスのすべての通信が処理されます。 

コント ローラー サービスは、次のコア機能を提供します。

- クラスターのライフ サイクル管理: 構成を更新、削除 (&)、クラスターのブートス トラップ
- Master の SQL Server インスタンスを管理します。
- コンピューティング、データおよび記憶域プールを管理します。
- クラスターの状態を監視する監視ツールを公開します。
- トラブルシューティング ツールを検出し、予期しない問題の修復の公開します。
- クラスターのセキュリティの管理: セキュリティで保護されたクラスター エンドポイントを確認、ユーザーとロールの管理、クラスター内通信の資格情報構成
- 安全に実装されているため、アップグレードのワークフローの管理 (CTP 2.0 では使用できません)
- (CTP 2.0 では使用できません)、クラスター内のステートフル サービスの高可用性と災害復旧を管理します。

## <a name="deploying-the-controller-service"></a>コント ローラー サービスのデプロイ

コント ローラーが展開され、ビッグ データ クラスターを構築するためのユーザーが同じの Kubernetes 名前空間でホストされています。 このサービスは、mssqlctl コマンド ライン ユーティリティを使用して、クラスターのブートス トラップ中には、Kubernetes には、管理者がインストールされています。

```bash
mssqlctl create cluster <name of your cluster>
```

年間のワークフローは Kubernetes の上にレイアウトで説明されているすべてのコンポーネントを含む完全に機能の SQL Server ビッグ データ クラスター、[概要](big-data-cluster-overview.md)記事。 ブートス トラップのワークフローが最初に、コント ローラー サービスを作成し、コント ローラー サービスでのインストールとマスター、コンピューティング、データおよび記憶域プールのサービスの一部の残りの部分の構成を調整はこれが配置されるとします。

## <a name="managing-the-cluster-through-the-controller-service"></a>コント ローラー サービスを使用してクラスターを管理します。
いずれかを使用してコント ローラー サービスを使用するだけで、クラスターを管理する`mssqlctl`Api や、クラスター内でホストされているクラスターの管理ポータル。 同じ名前空間にポッドのような追加の Kubernetes オブジェクトを展開する場合管理またはコント ローラー サービスの監視対象ができません。

コント ローラーとビッグ データ クラスター用に作成された、Kubernetes のオブジェクト (ステートフルのセット、ポッド、シークレットなど) は、専用の Kubernetes 名前空間に存在します。 コント ローラー サービスをその名前空間内のすべてのリソースを管理する Kubernetes クラスターの管理者によってアクセス権付与されます。  このシナリオでは、RBAC ポリシーが展開を使用して初期クラスターの一部として自動的に構成されている`mssqlctl`します。 

### <a name="mssqlctl"></a>mssqlctl

`mssqlctl` コマンド ライン ユーティリティは、クラスター管理者は、ブートス トラップし、コント ローラー サービスによって公開される REST Api を使用してビッグ データ クラスターを管理できるようにする Python で記述されます。

### <a name="cluster-administration-portal"></a>クラスターの管理ポータル

コント ローラー サービスが稼働するいると、クラスター管理者は、デプロイの進行状況を監視、検出、およびクラスター内のサービスに関する問題のトラブルシューティングにクラスターの管理ポータルを使用できます。 

## <a name="monitoring-and-troubleshooting-the-controller-service"></a>監視と、コント ローラー サービスのトラブルシューティング

もうすぐです。。。

## <a name="controller-service-security"></a>コント ローラー サービスのセキュリティ
コント ローラー サービスへのすべての通信は、HTTPS 経由で REST API 経由で行われます。 自己署名証明書は、するので自動的にブートス トラップ時に生成されます。 

コント ローラーのサービス エンドポイントへの認証は、ユーザー名とパスワードに基づきます。 これらの資格情報は、環境変数の入力を使用して、クラスターのブートス トラップ時にプロビジョニングされて`CONTROLLER_USERNAME`と`CONTROLLER_PASSWORD`します。
```

> [!NOTE]
> You must provide a password that is in compliance with [SQL Server password complexity requirements](https://docs.microsoft.com/en-us/sql/relational-databases/security/password-policy?view=sql-server-2017).

## Next steps

To learn more about the SQL Server big data clusters, see the following overview:

- [What is SQL Server 2019 big data clusters?](big-data-cluster-overview.md)
