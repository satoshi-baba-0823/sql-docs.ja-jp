---
title: DefaultScript 要素 (ASSL) |Microsoft ドキュメント
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: e21b89833edf744a6e47474e9c438be74530479c
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34034193"
---
# <a name="defaultscript-element-assl"></a>DefaultScript 要素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  既定値を識別[MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md)内の要素、 [MdxScripts](../../../analysis-services/scripting/collections/mdxscripts-element-assl.md)コレクション。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<MdxScript>  
   ...  
   <DefaultScript>...</DefaultScript>  
   ...  
</MdxScript>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|ブール値|  
|既定値|**True**|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>解説  
 値を設定**DefaultScript**に**True**スクリプトを 1 つの値の設定の**DefaultScript**に**False**の他のすべての**MdxScript**内の要素、 **MdxScripts**コレクション。  
  
 親に対応する要素**DefaultScript**分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.MdxScript>します。  
  
## <a name="see-also"></a>参照  
 [プロパティ & #40 です。ASSL & #41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
