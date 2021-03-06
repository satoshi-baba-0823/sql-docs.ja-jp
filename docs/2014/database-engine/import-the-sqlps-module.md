---
title: SQLPS モジュールのインポート | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: e687fd8c7fcd7c21f8aac9b546492a8f9bd4a644
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48077242"
---
# <a name="import-the-sqlps-module"></a>SQLPS モジュールのインポート
  PowerShell から [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] を管理する方法としては、`sqlps` モジュールを Windows PowerShell 2.0 環境にインポートする方法を推奨します。 このモジュールによって、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] のスナップインと管理アセンブリが読み込まれ、登録されます。  
  
1.  **はじめに:**  [セキュリティ](#Security)  
  
2.  **モジュールを読み込むには:**  [sqlps モジュールの読み込み](#LoadSqlps)  
  
## <a name="before-you-begin"></a>はじめに  
 `sqlps` モジュールを Windows PowerShell にインポートした後は、次のことができます。  
  
-   Windows PowerShell コマンドを対話的に実行する。  
  
-   Windows PowerShell スクリプト ファイルを実行する。  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] コマンドレットを実行する。  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] プロバイダー パスを使用して [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] オブジェクトの階層内を移動する。  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] の管理オブジェクト モデル (Microsoft.SqlServer.Management.Smo など) を使用して、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] のオブジェクトを管理する。  
  
> [!NOTE]  
>  2 つの SQL Server コマンドレット (`Encode-Sqlname` および `Decode-Sqlname`) の名前で使用されている動詞は、Windows PowerShell 2.0 で承認されている動詞と一致しません。 、操作に影響を与えませんが、Windows PowerShell によって警告が発生時に、`sqlps`モジュールがセッションにインポートします。  
  
###  <a name="Security"></a> セキュリティ  
 既定では、Windows PowerShell 実行時のスクリプト実行ポリシーは **[Restricted]** に設定されます。これにより、Windows PowerShell スクリプトの実行が防止されます。 `sqlps` モジュールを読み込む際は、`Set-ExecutionPolicy` コマンドレットを使用すると、署名されたスクリプトまたは任意のスクリプトの実行を有効化できます。 信頼できるソースからのスクリプト以外は実行しないでください。また、適切な NTFS 権限を使用して、すべての入力ファイルと出力ファイルのセキュリティを保護してください。 Windows PowerShell スクリプトの有効化の詳細については、「 [Windows PowerShell スクリプトの実行](http://www.microsoft.com/technet/scriptcenter/topics/winpsh/manual/run.mspx)」を参照してください。  
  
##  <a name="LoadSqlps"></a> sqlps モジュールの読み込み  
 **Windows PowerShell に sqlps モジュールを読み込むには**  
  
1.  使用して、`Set-ExecutionPolicy`コマンドレットを適切なスクリプト実行ポリシーを設定します。  
  
2.  使用して、 `Import-Module` sqlps モジュールをインポートするコマンドレットです。 指定、`DisableNameChecking`についての警告を抑制する場合は、パラメーター`Encode-Sqlname`と`Decode-Sqlname`します。  
  
### <a name="example-powershell"></a>例 (PowerShell)  
 この例は `sqlps` モジュールを読み込み、名前のチェックを無効にします。  
  
```  
## Import the SQL Server Module.  
  
Import-Module “sqlps” -DisableNameChecking  
  
```  
  

  
## <a name="see-also"></a>参照  
 [SQL Server PowerShell](../powershell/sql-server-powershell.md)   
 [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md)   
 [データベース エンジン コマンドレットの使用](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
  
  
