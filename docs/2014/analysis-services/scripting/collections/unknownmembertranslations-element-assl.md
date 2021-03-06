---
title: UnknownMemberTranslations 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- UnknownMemberTranslations Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- UnknownMemberTranslations
helpviewer_keywords:
- UnknownMemberTranslations element
ms.assetid: 72920843-2d43-4ff4-b38e-19c9a7451cb2
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 24f9aa5470bc1283abc0fd2b50838dca880ed6d4
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48113555"
---
# <a name="unknownmembertranslations-element-assl"></a>UnknownMemberTranslations 要素 (ASSL)
  キャプションに対する翻訳のコレクションを格納、 [UnknownMember](../objects/member-element-assl.md)ディメンションの要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Dimension>  
   ...  
   <UnknownMemberTranslations>  
      <UnknownMemberTranslation xsi:type="Translation ">...</UnknownMemberTranslation>  
      </UnknownMemberTranslations>  
   ...  
</Dimension>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[Dimension](../objects/dimension-element-assl.md)|  
|子要素|[UnknownMemberTranslation](../objects/translation-element-assl.md)型の[翻訳](../data-type/translation-data-type-assl.md)|  
  
## <a name="remarks"></a>コメント  
 親に対応する要素`UnknownMemberTranslations`分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.Dimension>します。  
  
## <a name="see-also"></a>参照  
 [Translation データ型&#40;ASSL&#41;](../data-type/translation-data-type-assl.md)   
 [コレクション&#40;ASSL&#41;](collections-assl.md)  
  
  
