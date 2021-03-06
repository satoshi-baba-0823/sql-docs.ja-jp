---
title: RequiresRestart 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- RequiresRestart Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- RequiresRestart
helpviewer_keywords:
- RequiresRestart element
ms.assetid: 9e98f956-c41e-4e15-a7bd-e17c10ee6fc6
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 752acb9d560ba62d74a3b5486c79279fb49fd2a8
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48120882"
---
# <a name="requiresrestart-element-assl"></a>RequiresRestart 要素 (ASSL)
  関連付けられている読み取り専用の値が含まれています、 [ServerProperty](../objects/serverproperty-element-assl.md)サーバー プロパティの値を変更するには、変更を反映するため、インスタンスを再起動するが必要かどうかを決定する要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<ServerProperty>  
   ...  
   <RequiresRestart>...</RequiresRestart>  
   ...  
</ServerProperty>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|ブール値|  
|既定値|なし|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[ServerProperty](../objects/serverproperty-element-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 親に対応する要素`RequiresRestart`分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.ServerProperty>します。  
  
## <a name="see-also"></a>参照  
 [ServerProperties 要素&#40;ASSL&#41;](../collections/serverproperties-element-assl.md)   
 [Server 要素&#40;ASSL&#41;](../objects/server-element-assl.md)   
 [プロパティ&#40;ASSL&#41;](properties-assl.md)  
  
  
