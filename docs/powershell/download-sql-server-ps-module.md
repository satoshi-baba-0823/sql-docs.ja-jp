---
title: SQL Server PowerShell モジュールのダウンロード | Microsoft Docs
ms.custom: ''
ms.date: 01/05/2018
ms.prod: sql
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
keywords:
- sql server powershell のインストール, sql server powershell のダウンロード
ms.assetid: ''
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d41d03c3bba51b919a71f195de75a7ec29f51b7e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47621560"
---
# <a name="install-sql-server-powershell-module"></a>SQL Server PowerShell モジュールのインストール
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

この記事は、**SqlServer** PowerShell モジュールをインストールする手順を説明しています。

> [!NOTE]
> SQL Server PowerShell モジュールには **SqlServer** と **SQLPS** の 2 つがあります。 **SQLPS** モジュールは (後方互換性のため) SQL Server のインストールに含まれていますが、今後更新されることはありません。 最新の PowerShell モジュールは **SqlServer** モジュールです。 **SqlServer** モジュールには **SQLPS** のコマンドレットの更新バージョンだけでなく、最新の SQL 機能をサポートする新しいコマンドレットも含まれています。 SQL Server Management Studio (SSMS) には前のバージョンの **SqlServer** が含まれて*いました*が、SSMS の 16.x バージョンのみです。 PowerShell を SSMS 17.0 以降で使用するには、**SqlServer** モジュールを PowerShell ギャラリーからインストールする必要があります。

PowerShell ギャラリーから **SqlServer** モジュールをインストールするには、[PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting) セッションを開始し、次のコマンドを使用します。 インストールに問題が発生した場合は、[Install-module のドキュメント](https://docs.microsoft.com/powershell/gallery/psget/module/psget_install-module)と [Install-Module の参照](https://docs.microsoft.com/powershell/module/powershellget/Install-Module)をご覧ください。

**SqlServer** モジュールをインストールするには:

```Install-Module -Name SqlServer```

以前のバージョンの **SqlServer** モジュールがコンピューター上にある場合、`Update-Module` (この記事で後述) を使用できる、または `-AllowClobber` パラメーターを指定できる場合があります。  

```Install-Module -Name SqlServer -AllowClobber```

管理者として PowerShell セッションを実行できない場合は、次のようにして現在のユーザーにインストールできます。

```Install-Module -Name SqlServer -Scope CurrentUser```

**SqlServer** モジュールの更新バージョンがある場合、`Update-Module` を使用してバージョンを更新できます。

```Update-Module -Name SqlServer```

インストールされているモジュールのバージョンを表示する場合:

```Get-Module SqlServer -ListAvailable```

モジュールの特定のバージョンを使用するには、次のような特定のバージョン番号でインポートできます。

```Import-Module SqlServer -Version 21.0.17178```


PowerShell ギャラリーの **SqlServer** モジュールのバージョンは、バージョン管理をサポートし、PowerShell バージョン 5.0 以降が必要です。 

* [PowerShell ギャラリーの SqlServer モジュール](https://www.powershellgallery.com/packages/Sqlserver) 
* [SqlServer のコマンドレット](https://docs.microsoft.com/powershell/module/sqlserver)
* [SQLPS のコマンドレット](https://docs.microsoft.com/powershell/module/sqlps)
