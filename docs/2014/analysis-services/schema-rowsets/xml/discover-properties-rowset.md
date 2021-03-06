---
title: DISCOVER_PROPERTIES 行セット |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- DISCOVER_PROPERTIES
topic_type:
- apiref
helpviewer_keywords:
- DISCOVER_PROPERTIES rowset
ms.assetid: 3e2b50e2-3855-4091-8b02-4968e8e57d4c
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: facf15dea30e4628b52584141c67528fa73d2adb
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48095542"
---
# <a name="discoverproperties-rowset"></a>DISCOVER_PROPERTIES 行セット
  指定されたデータ ソースの [!INCLUDE[msCoName](../../../includes/msconame-md.md)] XML for Analysis (XMLA) プロバイダーによってサポートされている標準プロパティとプロバイダー固有のプロパティに関する情報および値の一覧を返します。 サポートされていないプロパティは、返される結果セットに表示されません。  
  
 呼び出す場合、 [Discover](../../xmla/xml-elements-methods-discover.md)メソッドを`DISCOVER_PROPERTIES`列挙値、 [RequestType](../../xmla/xml-elements-properties/type-element-xmla.md)要素、`Discover`メソッドを返します、`DISCOVER_PROPERTIES`行セット.。  
  
## <a name="rowset-columns"></a>行セットの列  
 `DISCOVER_PROPERTIES`行セットには、次の列が含まれています。  
  
|列名|型|長さ|説明|  
|-----------------|----------|------------|-----------------|  
|`PropertyName`|`DBTYPE_WSTR`||プロパティの名前。|  
|`PropertyDescription`|`DBTYPE_WSTR`||プロパティのローカライズ可能な説明テキスト。 `NULL` を返す場合もあります。|  
|`PropertyType`|`DBTYPE_WSTR`||プロパティの XML データ型。<br /><br /> `NULL` を返す場合もあります。|  
|`PropertyAccessType`|`DBTYPE_WSTR`||プロパティのアクセス。 値を指定できます`Read`、 `Write`、または`ReadWrite`します。|  
|`IsRequired`|`DBTYPE_BOOL`||プロパティが必須かどうかを示すブール値。<br /><br /> 必須の場合は True、必須でない場合は False です。<br /><br /> `NULL` を返す場合もあります。|  
|`Value`|`DBTYPE_WSTR`||プロパティの現在の値。<br /><br /> `NULL` を返す場合もあります。|  
  
 このスキーマ行セットは並べ替えられません。  
  
## <a name="restriction-columns"></a>制限の列  
 `DISCOVER_PROPERTIES` 行セットは、次の表に示されている列で制限できます。  
  
|列名|型を表すインジケーター|制限の状態|  
|-----------------|--------------------|-----------------------|  
|`PropertyName`|`DBTYPE_WSTR`||  
  
## <a name="see-also"></a>参照  
 [XML for Analysis Schema 行セット](xml-for-analysis-schema-rowsets.md)  
  
  
