---
title: ブロック要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Blocks Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Blocks
helpviewer_keywords:
- Blocks element
ms.assetid: d6fd4e6b-b5bd-43cd-9c28-48af57cf977c
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 6b1030bf5efbfb86319d83a19913f58d834f85fc
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48082722"
---
# <a name="blocks-element-assl"></a>Blocks 要素 (ASSL)
  バイナリ コンテンツを表すバイナリ データのブロックのコレクションを格納する[ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md)要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Data xsi:type="DataBlock">  
   ...  
   <Blocks>  
      <Block>...</Block>  
   </Blocks>  
   ...  
</File>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現します|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[データ](../objects/data-element-assl.md)型の[DataBlock](../data-type/datablock-data-type-assl.md)|  
|子要素|[ブロック](../objects/block-element-assl.md)|  
  
## <a name="remarks"></a>コメント  
 親に対応する要素`Blocks`分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.ClrAssemblyFile>します。  
  
## <a name="see-also"></a>参照  
 [Assembly 要素&#40;ASSL&#41;](../objects/assembly-element-assl.md)   
 [ClrAssembly データ型&#40;ASSL&#41;](../data-type/assembly-data-type-assl.md)   
 [要素をファイル&#40;ASSL&#41;](files-element-assl.md)   
 [要素が&#40;ASSL&#41;](../objects/file-element-assl.md)   
 [ClrAssemblyFile データ型&#40;ASSL&#41;](../data-type/clrassemblyfile-data-type-assl.md)   
 [データ要素&#40;ASSL&#41;](../objects/data-element-assl.md)   
 [DataBlock データ型&#40;ASSL&#41;](../data-type/datablock-data-type-assl.md)   
 [Blocks 要素](blocks-element-assl.md)   
 [要素のブロック&#40;ASSL&#41;](../objects/block-element-assl.md)   
 [コレクション&#40;ASSL&#41;](collections-assl.md)  
  
  
