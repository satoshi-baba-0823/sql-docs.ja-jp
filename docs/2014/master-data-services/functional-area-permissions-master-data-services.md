---
title: 機能領域アクセス許可 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
helpviewer_keywords:
- functional area permissions [Master Data Services], about functional area permissions
- functional area permissions [Master Data Services]
- permissions [Master Data Services], functional areas
ms.assetid: a80b87b3-b904-4cda-8582-0761c2617c57
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 4332afe3936740fa801810676f301b8fefbe35c4
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48202442"
---
# <a name="functional-area-permissions-master-data-services"></a>機能領域権限 (Master Data Services)
  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ユーザー インターフェイス (UI) の各機能領域に、権限を割り当てることができます。 次の 5 つの機能領域があります。  
  
-   **エクスプローラー**  
  
-   **バージョン管理**  
  
-   **統合管理**  
  
-   **システム管理**  
  
-   **ユーザー/グループの権限**  
  
 機能領域に権限を割り当てると、UI のその領域がユーザーまたはグループに表示されます。  
  
 **[エクスプローラー]** 機能領域内でユーザーがアクセスできるデータは、モデル オブジェクトおよび階層メンバーに割り当てられた追加権限によって決定されます。 その他のすべての機能領域内でモデルを表示および操作するには、ユーザーはモデル管理者である必要があります。 詳細については、「[Administrators &#40;Master Data Services&#41; (管理者 &#40;マスター データ サービス&#41;)](administrators-master-data-services.md)」を参照してください。  
  
 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]にアクセスするには、ユーザーまたはグループが、少なくとも 1 つの機能領域および **[モデル]** タブに表示される少なくとも 1 つのモデルに対する権限を持っている必要があります。  
  
## <a name="see-also"></a>参照  
 [機能領域アクセス許可を割り当てる&#40;マスター データ サービス&#41;](../../2014/master-data-services/assign-functional-area-permissions-master-data-services.md)   
 [モデル オブジェクト権限&#40;マスター データ サービス&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md)   
 [階層メンバーの権限&#40;マスター データ サービス&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)   
 [権限の決定方法&#40;マスター データ サービス&#41;](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
