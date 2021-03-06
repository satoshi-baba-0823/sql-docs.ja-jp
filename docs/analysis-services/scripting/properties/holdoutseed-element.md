---
title: HoldoutSeed 要素 |Microsoft ドキュメント
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: f0fbf102dcfc731f02195964c6657244e9bf0b70
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34036430"
---
# <a name="holdoutseed-element"></a>HoldoutSeed 要素
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  テスト セットを含む反復可能な提示されたパーティションのシードを指定します、 [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)要素。 このシードを指定すると、再処理中にモデルのコンテンツが変更されることはありません。 指定されていないか 0 に設定する場合[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]マイニング構造の名前のハッシュ アルゴリズムを使用して、シードを作成します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<MiningStructure>  
   ...  
   <ddl100_100:HoldoutSeed>...</ddl100_100:HoldoutSeed>  
   ...  
</MiningStructure>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|Long|  
|既定値|0|  
|Cardinality|0-1 : 省略可能な要素で、出現する場合は 1 回だけの出現が可能です。|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>解説  
 最初にマイニング構造を作成した時点では、ID と名前は同じです。 ただし、マイニング構造の名前は変更できます。 したがって、パーティションを反復可能にする場合は、名前に基づいて作成されたシードは使用せずに、シードを明示的に設定してください。  
  
 さらを使用してマイニング構造のコピーを作成する場合、**エクスポート**ステートメントでは、[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]新しいマイニング構造の名前が保持されますが、新しい ID を自動的に生成されます したがって、名前が同じで ID が異なる 2 つのマイニング構造が存在することもありえます。 名前が同じ 2 つのマイニング構造では、同じシードが使用されます。 ただし、データのパーティション分割はソース データにも依存するので、各構造のパーティションの実際の内容は異なる場合があります。  
  
 新しいプロパティ**HoldoutMaxCases**、 **HoldoutMaxPercent**、 **HoldoutSeed**、または**HoldoutActualSize** でしか使用できません。[!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]以降のバージョン。 構文の説明に示すように、これらのプロパティを新しい名前空間を付ける必要がありますので、または[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]はエラーを返します。  
  
 **注**で[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]、[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]でした、マイニング構造に提示されたパーティションの使用をサポートしていません。 したがって、[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]スクリプト言語 (ASSL) ステートメントを提示されたパラメーターを含む**HoldoutMaxCases**、 **HoldoutMaxPercent**、 **HoldoutSeed**、または**HoldoutActualSize**では使用できません[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]です。 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] の ASSL ステートメントでこれらの提示されたパラメーターのいずれかを使用すると、[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] でエラーが返されます。  
  
 親に対応する要素**HoldoutSeed**分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.MiningStructure>します。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;ASSL&#41;](../../../analysis-services/scripting/properties/properties-assl.md)   
 [HoldoutActualSize 要素](../../../analysis-services/scripting/properties/holdoutactualsize-element.md)   
 [HoldoutMaxPercent 要素](../../../analysis-services/scripting/properties/holdoutmaxpercent-element.md)   
 [HoldoutMaxCases 要素](../../../analysis-services/scripting/properties/holdoutmaxcases-element.md)  
  
  
