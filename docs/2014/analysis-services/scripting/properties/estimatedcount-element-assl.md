---
title: EstimatedCount 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- EstimatedCount Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- EstimatedCount
helpviewer_keywords:
- EstimatedCount element
ms.assetid: ce84b54a-8ab2-42f4-a7dd-e10a3d41cb4d
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: bc65def1576c28a9a21249501f83986c2652652d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48155716"
---
# <a name="estimatedcount-element-assl"></a>EstimatedCount 要素 (ASSL)
  ユーザーによって定義された属性のメンバーの推定数を格納します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<AggregationDesignAttribute> <!-- or DimensionAttribute -->  
      ...  
   <EstimatedCount>...</EstimatedCount>  
   ...  
</AggregationDesignAttribute>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|Long|  
|既定値|なし|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[AggregationDesignAttribute](../data-type/aggregationdesignattribute-data-type-assl.md)、 [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 この値は、ユーザーによって割り当てられるし、によって使用されます、 [AggregationDesign 要素&#40;ASSL&#41;](../objects/aggregationdesign-element-assl.md)します。  
  
 親に対応する要素`EstimatedCount`分析管理オブジェクト (AMO) オブジェクト モデルは、<xref:Microsoft.AnalysisServices.AggregationDesignAttribute>と<xref:Microsoft.AnalysisServices.DimensionAttribute>します。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;ASSL&#41;](properties-assl.md)  
  
  
