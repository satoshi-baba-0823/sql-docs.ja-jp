---
title: '[SQL Server Integration Services のプロパティ] ダイアログ ボックス ([サービス] タブ) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- configmgr-client
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 5d716dcebef94f3da17a01cc4a6aac95c1272b79
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48066202"
---
# <a name="sql-server-integration-services-properties-service-tab"></a>[SQL Server Integration Services のプロパティ] ダイアログ ボックス ([サービス] タブ)
  **[[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] のプロパティ]** ダイアログ ボックスの **[サービス]** タブでは、以下のオプションの表示や指定を行います。  
  
## <a name="options"></a>および  
 **[バイナリ パス]**  
 表示、このサービスで使用するプログラム ファイルの場所。  
  
 **[エラー制御]**  
 1 は `SERVICE_ERROR_NORMAL`を示します。 コンピューターの起動時にこのサービスが開始しなかった場合は、スタートアップ プログラムによってログにエラーが記録され、ポップアップ メッセージ ボックスが表示されますが、スタートアップ操作は継続します。 この値は変更できません。  
  
 **終了コード**  
 このサービスの開始時または停止時に検出された問題を定義する [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows エラー コードです。 このクラスで表されるサービスに固有のエラーが検出されると、このプロパティは **ERROR_SERVICE_SPECIFIC_ERROR** (1066) に設定され、そのエラーに関する情報は、 **ServiceSpecificExitCode** プロパティで利用できるようになります。 この値は、実行中と正常終了時には NO_ERROR (0) に設定されます。  
  
 **Host Name**  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] サービスを実行しているコンピューターまたはクラスターの名前が表示されます。  
  
 **名前**  
 サービスの表示名が表示されます。  
  
 **プロセス ID**  
 Windows プロセス ID が表示されます。  
  
 **[SQL サービスの種類]**  
 呼び出し側プロセスに提供されるサービスの種類が表示されます。 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では、いくつかのサービスがインストールされます。  
  
 **[開始モード]**  
 このサービスを以下のいずれかのモードに設定します。  
  
-   「手動」: このサービスは、コンピューターの起動時に自動的に開始しません。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 構成マネージャーまたは他のツールを使用してこのサービスを開始する必要があります。  
  
-   \[自動]: このサービスは、コンピューターの起動時に開始を試みます。  
  
-   \[無効]: このサービスは開始できません。  
  
 **状態**  
 このサービスが実行中か、停止しているか、無効になっているかが表示されます。 **[...]** の場合は、状態の変更が保留になっています。  
  
  
