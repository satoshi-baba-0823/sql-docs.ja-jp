---
title: AttributeID 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- AttributeID Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- AttributeID
helpviewer_keywords:
- AttributeID element
ms.assetid: 13d2e92b-e4bf-4f2d-b34c-a6f483da3a9e
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ef870903cf32945abc442901757c3d524a9f2d73
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48168822"
---
# <a name="attributeid-element-assl"></a>AttributeID 要素 (ASSL)
  親要素に関連付けられている属性の ID を格納します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<AggregationAttribute> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <AttributeID>...</AttributeID>  
   ...  
</AggregationAttribute>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|String|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[AggregationAttribute](../data-type/aggregationattribute-data-type-assl.md)、 [AggregationDesignAttribute](../data-type/aggregationdesignattribute-data-type-assl.md)、 [AggregationInstanceAttribute](../data-type/aggregationinstanceattribute-data-type-assl.md)、 [AttributeBinding](../data-type/binding-data-type-assl.md)、 [AttributePermission](../objects/attributepermission-element-assl.md)、 [AttributeRelationship](../objects/attributerelationship-element-assl.md)、 [CubeAttribute](../data-type/cubeattribute-data-type-assl.md)、 [CubeAttributeBinding](../data-type/cubeattributebinding-data-type-assl.md)、 [DimensionAttributeBinding](../data-type/dimensionattributebinding-data-type-out-of-line-assl.md)、 [MeasureGroupAttribute](../data-type/measuregroupattribute-data-type-assl.md)、 [MeasureGroupAttributeBinding](../data-type/measuregroupattributebinding-data-type-out-of-line-assl.md)、 [PerspectiveAttribute](../data-type/perspectiveattribute-data-type-assl.md)、 [UserDefinedGroupBinding](../data-type/userdefinedgroupbinding-data-type-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 親に対応する要素`AttributeID`分析管理オブジェクト (AMO) オブジェクト モデルは、 <xref:Microsoft.AnalysisServices.AggregationAttribute>、 <xref:Microsoft.AnalysisServices.AggregationDesignAttribute>、 <xref:Microsoft.AnalysisServices.AggregationInstanceAttribute>、 <xref:Microsoft.AnalysisServices.AttributeBinding>、 <xref:Microsoft.AnalysisServices.AttributePermission>、 <xref:Microsoft.AnalysisServices.AttributeRelationship>、 <xref:Microsoft.AnalysisServices.CubeAttribute>、 <xref:Microsoft.AnalysisServices.CubeAttributeBinding>、 <xref:Microsoft.AnalysisServices.PerspectiveAttribute>、および<xref:Microsoft.AnalysisServices.UserDefinedGroupBinding>します。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;ASSL&#41;](properties-assl.md)  
  
  
