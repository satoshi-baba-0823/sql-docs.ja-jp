---
title: STExteriorRing (geometry データ型) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STExteriorRing_TSQL
- STExteriorRing (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STExteriorRing (geometry Data Type)
ms.assetid: b402b36f-05bf-4c6d-8cd6-76c0fff19db2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f90bcc20761f3fb3ac4aa7c4ec5e32bd715da176
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47763990"
---
# <a name="stexteriorring-geometry-data-type"></a>STExteriorRing (geometry データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

多角形の **geometry** インスタンスの外部リングを返します。
  
## <a name="syntax"></a>構文  
  
```  
  
.STExteriorRing ( )  
```  
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の戻り値の型: **geometry**  
  
 CLR 戻り値の型: **SqlGeometry**  
  
 Open Geospatial Consortium (OGC) の型: **LineString**  
  
## <a name="remarks"></a>Remarks  
 **geometry** インスタンスが多角形ではない場合、このメソッドは **NULL** を返します。  
  
## <a name="examples"></a>使用例  
 `Polygon` インスタンスを作成し、`STExteriorRing()` を使用して、多角形の外部リングを **LineString** として返す例を次に示します。  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0),(2 2, 2 1, 1 1, 1 2, 2 2))', 0);  
SELECT @g.STExteriorRing().ToString();  
```  
  
## <a name="see-also"></a>参照  
 [Geometry インスタンスの OGC メソッド](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  

