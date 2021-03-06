---
title: カスタム レポート アイテムのアーキテクチャ | Microsoft Docs
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: custom-report-items
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: markingmyname
ms.author: maghan
ms.openlocfilehash: cfe60270d68886f498b25d5f9b161df4f7dc2622
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47670573"
---
# <a name="custom-report-item-architecture"></a>カスタム レポート アイテムのアーキテクチャ
  カスタム レポート アイテムは、レポート定義言語 (RDL) の拡張機能です。開発者は、カスタム レポート アイテムを使用して、RDL ではネイティブでサポートされない機能を追加するか、既存のコントロールの機能を拡張することができます。 カスタム レポート アイテムには、2 つのメイン コンポーネントである、実行時コンポーネントとデザイン時コンポーネントがあります。 これらのコンポーネントは、[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] アセンブリとして実装され、CLS 準拠の言語で作成できます。  
  
## <a name="the-run-time-component"></a>実行時コンポーネント  
 カスタム レポート アイテムの実行時コンポーネントは、実行時にレポート プロセッサにより呼び出されます。 実行時コンポーネントは実行時にレポート プロセッサから渡されたデータを受け取り、そのデータを処理し、表示されたカスタム レポート アイテムを含む画像を返します。  
  
 ![カスタム レポート アイテムの実行時コンポーネント](../../reporting-services/custom-report-items/media/customreportitemrun-timecomponentarchitecture.gif "カスタム レポート アイテムの実行時コンポーネント")  
  
## <a name="the-design-time-component"></a>デザイン時コンポーネント  
 デザイン時コンポーネントを使用して、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] のレポート デザイナーでカスタム レポート アイテムを定義および操作することができます。 デザイン時コンポーネントは、デザイン環境でのカスタム レポート アイテムの表示およびプロパティを制御するいくつかのサブコントロールで構成されています。  
  
 ![カスタム レポート アイテムのデザイン時コンポーネント](../../reporting-services/custom-report-items/media/customreportitemdesign-timecomponentarchitecture.gif "カスタム レポート アイテムのデザイン時コンポーネント")  
  
## <a name="see-also"></a>参照  
 [カスタム レポート アイテムの実行時コンポーネントの作成](../../reporting-services/custom-report-items/creating-a-custom-report-item-run-time-component.md)   
 [カスタム レポート アイテムのデザイン時コンポーネントの作成](../../reporting-services/custom-report-items/creating-a-custom-report-item-design-time-component.md)   
 [カスタム レポート アイテムを配置する方法](../../reporting-services/custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
