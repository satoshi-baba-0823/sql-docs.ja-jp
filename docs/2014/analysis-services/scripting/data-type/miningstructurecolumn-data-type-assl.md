---
title: MiningStructureColumn データ型 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- MiningStructureColumn Data Type
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- MiningStructureColumn
helpviewer_keywords:
- MiningStructureColumn data type
ms.assetid: b6d6e7a5-9c48-40c4-b147-8fcd5e429ae3
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 0bcf11bef82aa9cb2abb2e8a08b7d567e5eb0159
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48153072"
---
# <a name="miningstructurecolumn-data-type-assl"></a>MiningStructureColumn データ型 (ASSL)
  内の列に関する情報を表す抽象プリミティブ データ型を定義、 [MiningStructure](../objects/miningstructure-element-assl.md)要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<MiningStructureColumn>  
   <Name>...</Name>  
   <ID>...</ID>  
   <Description>...</Description>  
   <Type>...</Type>  
   <Annotations>...</Annotations>  
</MiningStructureColumn>  
```  
  
## <a name="data-type-characteristics"></a>データ型の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|基本データ型|なし|  
|派生データ型|[ScalarMiningStructureColumn](miningstructurecolumn-data-type-assl.md)、 [TableMiningStructureColumn](tableminingstructurecolumn-data-type-assl.md)|  
  
## <a name="data-type-relationships"></a>データ型のリレーションシップ  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|なし|  
|子要素|[注釈](../collections/annotations-element-assl.md)、[説明](../properties/description-element-assl.md)、 [ID](../properties/id-element-assl.md)、[名前](../properties/name-element-assl.md)、[型](../properties/type-element-miningstructurecolumn-assl.md)|  
|派生要素|[列](../objects/column-element-assl.md)([列](../collections/columns-element-assl.md)のコレクション[MiningStructure](../objects/miningstructure-element-assl.md))|  
  
## <a name="remarks"></a>コメント  
 分析管理オブジェクト (AMO) オブジェクト モデルで対応する要素は<xref:Microsoft.AnalysisServices.MiningStructureColumn>します。  
  
## <a name="see-also"></a>参照  
 [Analysis Services スクリプト言語の XML データ型&#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
