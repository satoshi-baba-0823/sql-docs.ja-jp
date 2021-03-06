---
title: Azure Data Studio の機能を拡張 |Microsoft Docs
description: Azure データ studio の拡張機能を追加します。
ms.custom: tools|sos
ms.date: 09/24/2018
ms.reviewer: alayu; sstein
ms.prod: sql
ms.prod_service: sql-tools
ms.topic: conceptual
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d71b46bb992a5a47e0225e9263f5467e9d7f7150
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "48039124"
---
# <a name="extend-the-functionality-of-includename-sosincludesname-sos-shortmd"></a>[!INCLUDE[name-sos](../includes/name-sos-short.md)] の機能を拡張します

[!INCLUDE[name-sos](../includes/name-sos-short.md)] の拡張機能はベース [!INCLUDE[name-sos](../includes/name-sos-short.md)] のインストールにより多くの機能を簡単に追加する方法を提供します。 

拡張機能は、サード パーティ コミュニティ (する!) と (マイクロソフト)、Azure Data Studio チームによって提供されます。 拡張機能の作成方法の詳細については、次を参照してください。[拡張機能作成](extension-authoring.md)です。


## <a name="add-azure-data-studio-extensions"></a>Azure Data Studio の拡張機能を追加します。

1. 拡張機能マネージャーを開き、使用可能な拡張機能にアクセスするには、拡張機能 アイコンを選択するか、**ビュー**メニューの**拡張**を選択します。
2. 使用可能な拡張機能を選択して詳細を表示します。

   ![拡張機能マネージャー](media/extensions/extension-manager.png)

3. 必要な拡張機能を選択し、**インストール**します。
4. **再読み込み**を選択して拡張機能を有効にします(初めて拡張機能をインストールするときのみ必要です)。
5. サーバーまたはデータベースを右クリックし、**管理**を選択して管理ダッシュ ボードに移動します。
6. インストールされた拡張機能は、管理ダッシュ ボードのタブとして表示されます。

   ![拡張機能マネージャー](media/extensions/dashboard-extensions.png)




