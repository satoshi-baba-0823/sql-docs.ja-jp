---
title: TableNotification 要素 (ASSL) |Microsoft ドキュメント
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: f5d50f1182ce2c35f2c197b57434f4b30a6ea2d8
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34030213"
---
# <a name="tablenotification-element-assl"></a>TableNotification 要素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  情報が含まれています、 [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md)テーブルまたはビューが変更されているデータ ソース内の要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<TableNotifications>  
   <TableNotification>  
      <DbTableName>...</DbTableName>  
      <DbSchemaName>...</DbSchemaName>  
...</TableNotification>  
</TableNotifications>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
|Cardinality|1-n : 必須要素で、複数回の出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[TableNotifications](../../../analysis-services/scripting/collections/tablenotifications-element-assl.md)|  
|子要素|[DbSchemaName](../../../analysis-services/scripting/properties/dbschemaname-element-assl.md)、 [DbTableName](../../../analysis-services/scripting/properties/dbtablename-element-assl.md)|  
  
## <a name="remarks"></a>解説  
 分析管理オブジェクト (AMO) オブジェクト モデルで対応する要素は<xref:Microsoft.AnalysisServices.TableNotification>します。  
  
## <a name="see-also"></a>参照  
 [ProactiveCachingTablesBinding データ型&#40;ASSL&#41;](../../../analysis-services/scripting/data-type/proactivecachingtablesbinding-data-type-assl.md)   
 [ProactiveCachingObjectNotificationBinding データ型&#40;ASSL&#41;](../../../analysis-services/scripting/data-type/proactivecachingobjectnotificationbinding-data-type-assl.md)   
 [ProactiveCachingBinding データ型&#40;ASSL&#41;](../../../analysis-services/scripting/data-type/proactivecachingbinding-data-type-assl.md)   
 [オブジェクト & #40 です。ASSL & #41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
