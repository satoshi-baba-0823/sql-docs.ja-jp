---
title: locks 構成オプションの既定値の保持 | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: f214f05b-5f0b-4786-b2ad-b8b4b6e58d72
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: f06990ba700ebebe4058dbdfb5ad973f2de390b7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47791680"
---
# <a name="keep-the-locks-configuration-option-default-value"></a>locks 構成オプションの既定値の保持
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  このルールでは、locks 構成オプションの値を確認します。 このオプションは、使用可能なロックの最大数を決定します。 これにより、 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] がロックに使用するメモリの量が制限されます。 既定値である 0 の場合、 [!INCLUDE[ssDE](../../includes/ssde-md.md)] はシステム要件の変更に基づいてロック構造を動的に割り当てたり、割り当てを解除することができます。  
  
 locks が 0 でない場合、指定された値を超えるとバッチ ジョブが停止し、"ロック不足" のエラー メッセージが生成されます。  
  
## <a name="best-practices-recommendations"></a>ベスト プラクティスと推奨事項  
 sp_configure システム ストアド プロシージャを使用して次のステートメントを実行することで、locks の値を既定の設定に変更してください。  
  
```  
EXEC sp_configure 'locks', 0;  
```  
  
## <a name="for-more-information"></a>詳細情報  
 [locks サーバー構成オプションの構成](../../database-engine/configure-windows/configure-the-locks-server-configuration-option.md)  
  
 [sys.dm_tran_locks &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql.md)  
  
 [sys.dm_os_wait_stats &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql.md)  
  
 [サポート技術情報の資料 271509](http://go.microsoft.com/fwlink/?linkid=117788)  
  
## <a name="see-also"></a>参照  
 [ポリシー ベースの管理を使用したベスト プラクティスの監視と実行](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
