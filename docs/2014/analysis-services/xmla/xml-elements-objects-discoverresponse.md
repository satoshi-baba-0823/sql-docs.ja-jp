---
title: DiscoverResponse 要素 (XMLA) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- DiscoverResponse Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#DiscoverResponse
- microsoft.xml.analysis.discoverresponse
- urn:schemas-microsoft-com:xml-analysis#DiscoverResponse
helpviewer_keywords:
- DiscoverResponse element
ms.assetid: 20e10a82-dbd1-4ead-b92d-f84b4b2f10c6
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 763724fb08a849000cb960435847a84447ba5674
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48105392"
---
# <a name="discoverresponse-element-xmla"></a>DiscoverResponse 要素 (XMLA)
  インスタンスによって返される情報を含む[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]への応答を[Discover](xml-elements-methods-discover.md)メソッドの呼び出し。  
  
 **Namespace** urn: スキーマ-microsoft-'http://www.w3.org/2001/xmlschema'-分析  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<DiscoverResponse>  
   <return>  
</DiscoverResponse>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|なし|  
|子要素|[return](xml-elements-properties/return-element-xmla.md)|  
  
## <a name="remarks"></a>コメント  
 `DiscoverResponse` 要素は、`Discover` メソッドに対する SOAP 応答の本文の最上位要素です。  
  
## <a name="see-also"></a>参照  
 [ExecuteResponse 要素&#40;XMLA&#41;](xml-elements-objects-executeresponse.md)   
 [オブジェクト&#40;XMLA&#41;](xml-elements-objects.md)  
  
  
