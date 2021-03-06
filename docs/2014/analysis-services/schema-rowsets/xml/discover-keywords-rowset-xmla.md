---
title: DISCOVER_KEYWORDS 行セット (XMLA) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- DISCOVER_KEYWORDS
topic_type:
- apiref
helpviewer_keywords:
- DISCOVER_KEYWORDS rowset
ms.assetid: 99945e53-3a1b-4d7b-9aff-712977db8b2d
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f7395447d832e7cc9f0a0eec745ca419ad19c6c3
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48050922"
---
# <a name="discoverkeywords-rowset-xmla"></a>DISCOVER_KEYWORDS 行セット (XMLA)
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] XML for Analysis (XMLA) プロバイダーによって予約されているキーワードに関する情報を返します。  
  
 呼び出す場合、 [Discover](../../xmla/xml-elements-methods-discover.md)メソッドを`DISCOVER_KEYWORDS`列挙値、 [RequestType](../../xmla/xml-elements-properties/type-element-xmla.md)要素、`Discover`メソッドを返します。、`DISCOVER_KEYWORDS`行セット。  
  
## <a name="rowset-columns"></a>行セットの列  
 `DISCOVER_KEYWORDS`行セットには、次の列が含まれています。  
  
|列名|型を表すインジケーター|長さ|説明|  
|-----------------|--------------------|------------|-----------------|  
|`Keyword`|`DBTYPE_WSTR`||プロバイダーによって予約されているすべてのキーワードの一覧。<br /><br /> 例: `AND`|  
  
 このスキーマ行セットは並べ替えられません。  
  
## <a name="restriction-columns"></a>制限の列  
 `DISCOVER_KEYWORDS`行セットは、次の表に示されている列で制限できます。  
  
|列名|型を表すインジケーター|制限の状態|  
|-----------------|--------------------|-----------------------|  
|`Keyword`|`DBTYPE_WSTR`|任意。|  
  
## <a name="see-also"></a>参照  
 [XML for Analysis スキーマ行セット](xml-for-analysis-schema-rowsets.md)   
 [DISCOVER_LITERALS 行セット](discover-literals-rowset.md)  
  
  
