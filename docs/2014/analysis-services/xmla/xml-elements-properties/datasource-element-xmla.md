---
title: DataSource 要素 (XMLA) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- DataSource Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#DataSource
- http://schemas.microsoft.com/analysisservices/2003/engine#DataSource
- microsoft.xml.analysis.datasource
helpviewer_keywords:
- DataSource element
ms.assetid: adc0713a-3927-40f3-8b87-012130908f34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 3acbba2e1ee5df1535799e133c064b90b6921386
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48130530"
---
# <a name="datasource-element-xmla"></a>DataSource 要素 (XMLA)
  親の行外のデータ ソースのバインドを含む[バッチ](../xml-elements-commands/batch-element-xmla.md)または[プロセス](../xml-elements-commands/process-element-xmla.md)要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Batch> <!-- or Process>  
...  
   <DataSource>  
      <DatabaseID>...</DatabaseID>  
      <DataSourceID>...</DataSourceID>  
   </DataSource>  
...  
</Batch>  
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
|親要素|[バッチ](../xml-elements-commands/batch-element-xmla.md)、[プロセス](../xml-elements-commands/process-element-xmla.md)|  
|子要素|[DatabaseID](id-element-xmla.md)、 [DataSourceID](datasourceid-element-xmla.md)|  
  
## <a name="remarks"></a>コメント  
 `DataSource` 要素は、データ ソースに対する不一致バインドを表します。これは、コマンドによって処理される [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] オブジェクトのデータ ソース バインドを一時的にオーバーライドするために、`Batch` または `Process` コマンドによって使用されます。  
  
 アウトオブ ライン バインドの詳細については、次を参照してください。[データ ソースとバインド&#40;SSAS 多次元&#41;](../../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md)します。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;XMLA&#41;](xml-elements-properties.md)  
  
  
