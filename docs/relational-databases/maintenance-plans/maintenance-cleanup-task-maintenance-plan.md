---
title: '[メンテナンス クリーンアップ タスク] (メンテナンス プラン) | Microsoft Docs'
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- sql13.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 4d9398bfda4df50706d1767ce6e5114acbe34a63
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47815980"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a>[メンテナンス クリーンアップ タスク] \(メンテナンス プラン)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  **[メンテナンス クリーンアップ タスク]** を使用すると、メンテナンス プランで作成されたテキスト レポートやデータベースのバックアップ ファイルなど、メンテナンス プランに関連する古いファイルを削除できます。  
  
> [!NOTE]  
>  メンテナンス クリーンアップ タスクでは、指定したディレクトリのサブフォルダーにあるファイルは自動的に削除されません。 この機能によって、メンテナンス クリーンアップ タスクを使ってファイルを削除するなど、悪意のある攻撃を受ける危険性を最小限に抑えることができます。 直下のサブフォルダーにあるファイルを削除する場合は、 **[直下のサブフォルダーを含める]** を選択する必要があります。  
  
## <a name="options"></a>[変数]  
 **接続**  
 現在の接続を表示します。  
  
 **新規**  
 このタスクを実行するときに使用する新しいサーバー接続を作成します。 **[新しい接続]** ダイアログ ボックスについては、後で説明します。  
  
 **[バックアップ ファイル]**  
 バックアップ ファイルを削除します。  
  
 **[メンテナンス プラン テキスト レポート]**  
 以前に実行されたメンテナンス プランのテキスト レポートを削除します。  
  
 **[特定のファイルを削除する]**  
 **[ファイル名]** ボックスに指定した特定のファイルを削除します。  
  
 **[ファイル名]**  
 削除するファイルのパスと名前です。  
  
 **[フォルダーを検索し、拡張子に基づいてファイルを削除する]**  
 指定したフォルダー内にある、指定した拡張子を持つすべてのファイルを削除します。 このオプションは、複数のファイル (たとえば、"Tuesday" フォルダー内にある、拡張子が .bak のすべてのバックアップ ファイル) を一度に削除する場合に使用します。  
  
 **フォルダー**  
 削除するファイルが格納されているフォルダーのパスと名前を指定します。  
  
 **[ファイル拡張子]**  
 削除するファイルのファイル拡張子を指定します。  
  
 **[直下のサブフォルダーを含める]**  
 **[ファイル拡張子]** に指定された拡張子を持つファイルを、 **[フォルダー]** の直下のサブフォルダーから削除します。  
  
 **[タスク実行時にファイルの経過期間に基づいてファイルを削除する]**  
 **[次の期間経過したファイルを削除]** ボックスに数値と時間単位を指定して、削除するファイルの最小経過期間を指定します。  
  
 **[次の期間経過したファイルを削除]**  
 数値と時間単位 ([日]、[週]、[月]、または [年]) を指定して、削除するファイルの最小経過期間を指定します。 指定した期間より古いファイルが削除されます。  
  
 **[T-SQL の表示]**  
 選択したオプションに基づき、このタスクでサーバーに対して実行される [!INCLUDE[tsql](../../includes/tsql-md.md)] ステートメントを表示します。  
  
> [!NOTE]  
>  影響を受けるオブジェクトが大量にある場合は、表示にかなりの時間を要する場合があります。  
  
## <a name="new-connection-dialog-box"></a>[新しい接続] ダイアログ ボックス  
 **[接続名]**  
 新しい接続の名前を入力します。  
  
 **[サーバー名の選択または入力]**  
 このタスクを実行するときに接続するサーバーを選択します。  
  
 **…**  
 利用可能なサーバーを一覧表示します。  
  
 **[サーバーにログオンするための情報の入力]**  
 サーバーの認証情報を指定します。  
  
 **[Windows NT の統合セキュリティを使用する]**  
 Microsoft Windows 認証を使用して [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] のインスタンスに接続します。  
  
 **[特定のユーザー名とパスワードを使用する]**  
 SQL Server 認証を使用して [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] のインスタンスに接続します。 このオプションは利用できません。  
  
 **User name**  
 認証に使用する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ログインを指定します。 このオプションは利用できません。  
  
 **Password**  
 認証に使用するパスワードを指定します。 このオプションは利用できません。  
  
## <a name="see-also"></a>参照  
 [のオブジェクト エクスプローラーの](../../relational-databases/maintenance-plans/maintenance-plans.md)  
  
  
