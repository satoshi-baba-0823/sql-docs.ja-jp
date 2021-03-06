---
title: common criteria compliance enabled サーバー構成オプション | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 1f1ad58e4b3e923d23d9770f12b094211adfc5a4
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48178732"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a>common criteria compliance enabled サーバー構成オプション
  [情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] オプションを使用すると、情報セキュリティ国際評価基準で必要とされる次の要素を有効にできます。  
  
|[抽出条件]|説明|  
|--------------|-----------------|  
|残存情報保護 (RIP)|RIP の要件とは、新しいリソースにメモリを再度割り当てる前に、メモリ割り当てを既知のビット パターンで上書きすることです。 RIP 標準を満たすとセキュリティの向上が図れますが、メモリ割り当てを上書きすることによってパフォーマンスが低下する場合があります。 [情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] を有効にすると、この上書きが行われます。|  
|ログインの統計を表示する機能|[情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] を有効にすると、ログイン監査が有効になります。 ユーザーが [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]へのログインに成功するたびに、最後にログインに成功した時間、最後にログインに失敗した時間、最後にログインした時間から現在のログイン時間までのログイン試行回数について、情報を確認できます。 このログインに関する統計情報は、 [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) 動的管理ビューにクエリを実行すると表示できます。|  
|列の GRANT がテーブルの DENY をオーバーライドしないこと|[情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] を有効にすると、テーブル レベルの DENY が列レベルの GRANT より優先されます。 このオプションが有効でない場合は、列レベルの GRANT がテーブル レベルの DENY より優先されます。|  
  
 [Common Criteria Compliance Enabled] オプションは拡張オプションです。 情報セキュリティ国際評価基準は、Enterprise Edition と Datacenter Edition についてのみ評価され、認定されています。 情報セキュリティ国際評価基準の最新の状況については、 [Microsoft SQL Server の情報セキュリティ国際評価基準](http://go.microsoft.com/fwlink/?LinkId=616319) の Web サイトを参照してください。  
  
> [!IMPORTANT]  
>  情報セキュリティ国際評価基準の評価保証レベル 4+ (EAL4+) に準拠するには、[情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] オプションを有効にすることのほかに、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の構成を完了するためのスクリプトをダウンロードして実行する必要があります。 このスクリプトは、 [Microsoft SQL Server 情報セキュリティ国際評価基準](http://go.microsoft.com/fwlink/?LinkId=616319) Web サイトからダウンロードできます。  
  
 sp_configure システム ストアド プロシージャを使用してこの設定を変更する場合、[情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] を変更できるのは、show advanced options が 1 に設定されているときだけです。 この設定は、サーバーを再起動した後に有効になります。 有効値は、0 および 1 です。  
  
-   0 は [情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] が有効でないことを表します。 既定値です。  
  
-   1 は [情報セキュリティ国際評価基準 (Common Criteria) への準拠を有効にする] が有効であることを表します。  
  
## <a name="examples"></a>使用例  
 次の例では、情報セキュリティ国際評価基準への準拠を有効にしています。  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a>参照  
 [サーバー構成オプション &#40;SQL Server&#41;](server-configuration-options-sql-server.md)  
  
  
