---
title: PushedDataSource データ型 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- PushedDataSource Data Type
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- PushedDataSource
helpviewer_keywords:
- PushedDataSource data type
ms.assetid: b319ee87-7c0a-41ec-a8af-cc7089aeb6ad
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ec01d8795e9ba5212dd8bfbd30186bbf648a8726
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48169844"
---
# <a name="pusheddatasource-data-type-assl"></a>PushedDataSource  データ型 (ASSL)
  データ ソースを表すプリミティブ データ型を定義します (など、 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]パッケージ) にデータを"プッシュ"するために使用される、[キューブ](../objects/cube-element-assl.md)要素。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<PushedDataSource>  
   <Root>...</Root>  
   <EndOfData>...</EndOfData>  
</PushedDataSource>  
```  
  
## <a name="data-type-characteristics"></a>データ型の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|基本データ型|なし|  
|派生データ型|なし|  
  
## <a name="data-type-relationships"></a>データ型のリレーションシップ  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|なし|  
|子要素|[EndOfData](../objects/data-element-assl.md)、[ルート](../properties/root-element-assl.md)|  
|派生要素|なし|  
  
## <a name="remarks"></a>コメント  
 `PushedDataSource` は、不一致データ ソースとして処理コマンド内でのみ使用されます。 持続データ ソースはこの型ではありません。  
  
## <a name="see-also"></a>参照  
 [Analysis Services スクリプト言語の XML データ型&#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
