---
title: Columns 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Columns Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- COLUMNS
helpviewer_keywords:
- Columns element
ms.assetid: 14011eed-6f10-4120-b256-d599d59bde80
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 16e8d446b3ffeb4895bde76a739d7ec63a01337d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48131512"
---
# <a name="columns-element-assl"></a>Columns 要素 (ASSL)
  親要素に関連付けられた列のコレクションを格納します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Action xsi:type="DrillThroughAction"> <!-- or one of the elements listed below in the Element Relationships table -->  
   <Columns>  
      <Column xsi:type="MeasureBinding">...</Column> <!-- parent: DrillThroughAction -->  
      <!-- or -->  
      <Column xsi:type="CubeAttributeBinding">...</Column> <!-- parent: DrillThroughAction -->  
      <!-- or -->  
      <Column xsi:type="EventColumn">...</Column> <!-- parent: Event -->  
      <!-- or -->  
      <Column xsi:type="MiningModelColumn">...</Column> <!-- parent: MiningModel or MiningModelColumn -->  
      <!-- or -->  
      <Column xsi:type="MiningStructureColumn">...</Column> <!-- parent: MiningStructure or TableMiningStructureColumn -->  
   </Columns>  
</DrillThroughAction>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
  
|先祖または親|Cardinality|  
|------------------------|-----------------|  
|[イベント](../objects/event-element-assl.md)|1-1 : 必須要素で、1 回だけ出現します|  
|他のすべて|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[アクション](../objects/action-element-assl.md)型の[DrillThroughAction](../data-type/action-data-type-assl.md)、[イベント](../objects/event-element-assl.md)、 [MiningModel](../objects/miningmodel-element-assl.md)、 [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)、 [MiningStructure](../objects/miningstructure-element-assl.md)、 [TableMiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)|  
  
|先祖または親|子要素|  
|------------------------|--------------------|  
|[DrillThroughAction](../data-type/binding-data-type-assl.md)または[MeasureBinding](../data-type/measurebinding-data-type-assl.md)|  
|[イベント](../data-type/eventcolumn-data-type-assl.md)|  
|[MiningModel](../objects/miningmodel-element-assl.md)、 [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|[MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|  
|[MiningStructure](../objects/miningstructure-element-assl.md)、 [TableMiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)|[MiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)|  
  
## <a name="remarks"></a>コメント  
 `DrillThroughAction` 、要素、`Columns`コレクションは、アクションは実行時に返されるデータを含む列を識別します。  
  
 `TableMiningStructureColumn` 、要素、`Columns`の再帰レベルを 1 つだけのコレクションを使用します。 つまり、`TableMiningStructureColumn`このコレクションに含まれる要素は、いずれかを含めることはできません`TableMiningStructureColumn`内の要素の`Columns`コレクション。  
  
 分析管理オブジェクト (AMO) オブジェクト モデルで対応する一部の要素は、<xref:Microsoft.AnalysisServices.TraceColumnCollection>、<xref:Microsoft.AnalysisServices.MiningModelColumnCollection>、および <xref:Microsoft.AnalysisServices.MiningStructureColumnCollection> です。  
  
## <a name="see-also"></a>参照  
 [コレクション&#40;ASSL&#41;](collections-assl.md)  
  
  
