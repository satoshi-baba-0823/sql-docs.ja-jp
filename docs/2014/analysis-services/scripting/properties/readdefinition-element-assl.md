---
title: ReadDefinition 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- ReadDefinition Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- ReadDefinition
helpviewer_keywords:
- ReadDefinition element
ms.assetid: 1f250129-13b2-41b9-b083-b5aacddf0060
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 176f1fa1f1a9f4fca3e773d65a5fda01c2f6752d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48218112"
---
# <a name="readdefinition-element-assl"></a>ReadDefinition 要素 (ASSL)
  メンバーがデータベースの定義やデータベース内のオブジェクトの定義を読み取ることができるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Permission> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <ReadDefinition>...</ReadDefinition>  
   ...  
</Permission>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|String (列挙型)|  
|既定値|*なし*|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[CubePermission](../objects/cubepermission-element-assl.md)、 [DatabasePermission](../objects/databasepermission-element-assl.md)、 [DimensionPermission](../objects/dimensionpermission-element-assl.md)、 [MiningModelPermission](../objects/miningmodelpermission-element-assl.md)、 [MiningStructurePermission](../objects/miningstructurepermission-element-assl.md)、[アクセス許可](../data-type/permission-data-type-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 この要素の値は、次の表の一覧に示す文字列のいずれかに限定されています。  
  
|値|説明|  
|-----------|-----------------|  
|*なし*|オブジェクト定義へのアクセスは許可されません。|  
|*基本*|オブジェクト定義への基本アクセスが許可されます。 **注:** このアクセス許可がローカル キューブを作成する、リンク メジャー グループ、およびディメンションのリンクが必要です。|  
|*許可されています。*|オブジェクト定義への完全アクセスが許可されます。 **注:** このアクセス許可を実行するために必要な[Discover](../../xmla/xml-elements-methods-discover.md) XML for Analysis (XMLA) の呼び出し、DISCOVER_XML_METADATA パラメーターを使用します。|  
  
 分析管理オブジェクト (AMO) オブジェクト モデルで `ReadDefinition` の親に対応する要素は、<xref:Microsoft.AnalysisServices.CubePermission>、<xref:Microsoft.AnalysisServices.DatabasePermission>、<xref:Microsoft.AnalysisServices.DimensionPermission>、<xref:Microsoft.AnalysisServices.MiningModelPermission>、<xref:Microsoft.AnalysisServices.MiningStructurePermission>、および <xref:Microsoft.AnalysisServices.Permission> です。  
  
## <a name="see-also"></a>参照  
 [Role 要素&#40;ASSL&#41;](../objects/role-element-assl.md)   
 [プロパティ&#40;ASSL&#41;](properties-assl.md)  
  
  
