---
title: ロールの割り当てを変更または削除する (レポート マネージャー) | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: markingmyname
ms.author: maghan
ms.openlocfilehash: d533acbbc99d02c644d910e1b2ee3555d58bece0
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47699500"
---
# <a name="role-assignments---modify-or-delete"></a>ロールの割り当て - 変更または削除
  ロールの割り当てとは、実行できるタスクがあらかじめ規定されたロール定義に、グループまたはユーザー アカウントをマップすることです。 ユーザーが実行できる操作の種類は、フォルダー、レポート、モデルなど、コンテンツの種類に基づいて決定されます。 ロールの割り当てを作成、変更、または削除するには、レポート マネージャーを使用します。 特定のユーザーまたはグループに対して作成したロールの割り当ては、後で異なるロールを選択することによって変更できます。 レポート サーバーに対する権限を取り消したい場合は、ロールの割り当てをレポート サーバーから削除します。  
  
 目的によっては、別の方法を用いた方がよい場合もあります。 つまり、新しいロール定義の作成やカスタマイズ、Active Directory 内グループ アカウントのメンバーシップ変更などです。  
  
 たとえば、ある一連のユーザーが、自分たちのコンテンツを詳細に管理する必要があるとします。これらのユーザーに対して、コンテンツ マネージャーに関連付けられている権限をすべて付与するわけにはいきません。 このような場合は、"部門コンテンツ マネージャー" という新しいロール定義を作成し、コンテンツ マネージャーの **[アイテムごとにセキュリティを設定]** を除く、すべてのタスクを含めます。  
  
 同様に、システム管理者やネットワーク管理者にとっては、レポート マネージャーでロールの割り当てを管理するよりも、Active Directory のグループ アカウントを管理した方が容易であるという場合も考えられます。そのようなときは、グループ アカウントに対するロールの割り当てを 1 つだけ作成し、ユーザーがレポートにアクセスする必要がなくなった時点でグループのメンバーシップを調整することによって、ロールの割り当て管理に伴うオーバーヘッドを低減できます。  
  
 ロールの割り当てを変更または削除することが最善の方法であると判断した場合は、必ずシステム ロールの割り当てとアイテム ロールの割り当ての両方を確認してください。 レポート マネージャーでロールの割り当てを構成する際に使用するページは、ロールの種類によって異なります。  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a>システム ロールの割り当てを変更または削除するには  
  
1.  [レポート マネージャー &#40;SSRS ネイティブ モード&#41;](http://msdn.microsoft.com/library/80949f9d-58f5-48e3-9342-9e9bf4e57896) を開始します。  
  
2.  **[サイトの設定]** をクリックします。  
  
3.  **[セキュリティ]** をクリックします。 現在、サーバーまたはスケールアウト配置に対して定義されているシステムレベルのロールの割り当てが、アカウント名ごとに一覧表示されます。  
  
4.  変更または削除するロールの割り当てを探します。  
  
5.  特定のユーザーまたはグループに対するロールを追加または削除するには、 **[編集]** をクリックします。  
  
6.  ロールの割り当てを削除するには、ユーザーまたはグループ名の隣にあるチェック ボックスをオンにして、 **[削除]** をクリックします。  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a>アイテム ロールの割り当てを変更または削除するには  
  
1.  **レポート マネージャー** を起動し、ロールの割り当てを編集または削除するアイテムを探します。  
  
2.  アイテムの上にマウス ポインターを移動し、下矢印をクリックします。  
  
3.  ドロップダウン メニューの **[セキュリティ]** をクリックします。  
  
4.  変更または削除するロールの割り当てを探します。  
  
5.  特定のユーザーまたはグループに対するロールを追加または削除するには、 **[編集]** をクリックします。  
  
6.  ロールの割り当てを削除するには、ユーザーまたはグループ名の隣にあるチェック ボックスをオンにして、 **[削除]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ロールの割り当てを作成および管理する](../../reporting-services/security/create-and-manage-role-assignments.md)   
 [ロールの割り当て](../../reporting-services/security/role-assignments.md)   
 [[サイトの設定] ページ &#40;レポート マネージャー&#41;](http://msdn.microsoft.com/library/4d67a01c-eae4-49ba-a6e8-8e983c0248f5)   
 [[新しいシステム ロールの割り当て]: [システム ロールの割り当てを編集] ページ &#40;レポート マネージャー&#41;](http://msdn.microsoft.com/library/62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a)  
  
  
