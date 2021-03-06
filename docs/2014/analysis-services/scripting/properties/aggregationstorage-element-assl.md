---
title: AggregationStorage 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- AggregationStorage Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- AggregationStorage
helpviewer_keywords:
- AggregationStorage element
ms.assetid: dd082388-534d-4847-9232-8f80fc9fe96e
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e3ec001116b63816d0b1e2831a266ec3029a38a9
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48187072"
---
# <a name="aggregationstorage-element-assl"></a>AggregationStorage 要素 (ASSL)
  集計の保存方法を識別します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<ProactiveCaching>  
   ...  
   <AggregationStorage>...</AggregationStorage>  
   ...  
</ProactiveCaching>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|String (列挙型)|  
|既定値|*正規表現*|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[ProactiveCaching](../objects/proactivecaching-element-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 この要素の値は、次のいずれかの文字列に制限されます。  
  
|値|説明|  
|-----------|-----------------|  
|*正規表現*|集計データは既定の方法で保存されます。|  
|*MolapOnly*|集計データは、多次元 OLAP (MOLAP) ストレージのみを使用して保存されます。|  
  
 *MolapOnly*オプションにのみ使用できますが、[パーティション](../objects/partition-element-assl.md)要素。  
  
 許容された値に対応する列挙体`AggregationStorage`分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.ProactiveCachingAggregationStorage>します。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;ASSL&#41;](properties-assl.md)  
  
  
