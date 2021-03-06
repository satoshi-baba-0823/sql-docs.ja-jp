---
title: Caption 要素 (XMLA) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Caption Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#Caption
- http://schemas.microsoft.com/analysisservices/2003/engine#Caption
- microsoft.xml.analysis.caption
helpviewer_keywords:
- Caption element
ms.assetid: 3d10ee68-98ab-4da0-a409-800dea2f1c32
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4899f19b8a3986e2063d2979ce84c0a0d52d0d02
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48201482"
---
# <a name="caption-element-xmla"></a>Caption 要素 (XMLA)
  親のキャプションに関する情報を格納[HierarchyInfo](hierarchyinfo-element-xmla.md)または[メンバー](member-element-xmla.md)要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<HierarchyInfo> <!-- or Member -->  
   ...  
   <Caption>...</Caption>  
   ...  
</HierarchyInfo>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|String|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現します|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[HierarchyInfo](hierarchyinfo-element-xmla.md)、[メンバー](member-element-xmla.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 `HierarchyInfo` 要素の場合、`Caption` 要素は、階層のメンバー キャプションを表すプロパティの名前を含みます。 値は、OLE DB for OLAP 仕様で軸行セットに関して定義される、MEMBER_CAPTION プロパティと同等です。  
  
 `Member` 要素の場合、`Caption` 要素は、XML for Analysis (XMLA) セッションに対して指定された言語で、親要素 `Member` のキャプションを含みます。 キャプションが使用できない場合、この要素にはメンバーの一意の名前が含まれます。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;XMLA&#41;](xml-elements-properties.md)  
  
  
