---
title: STSrid (geometry データ型) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STSrid (geometry Data Type)
- STSrid_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STSrid (geometry Data Type)
ms.assetid: 5e0de983-a0fe-48b7-9e08-30588d7271e2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 74cbd1d34ba7503881c8c9ab424be67edc02588c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47652540"
---
# <a name="stsrid-geometry-data-type"></a>STSrid (geometry データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  **STSrid** はインスタンスの SRID (spatial reference identifier) を表す整数です。  
  
このプロパティは変更できます。
  
## <a name="syntax"></a>構文  
  
```  
  
STSrid  
```  
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 型: **int**  
  
 CLR 型: **SqlInt32**  
  
## <a name="examples"></a>使用例  
 最初に、SRID 値が 13 の **geometry** インスタンスを作成し、`STSrid` を使用して SRID を確認する例を示します。  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0))', 13);  
SELECT @g.STSrid;  
```  
  
 次に、`STSrid` を使用してそのインスタンスの SRID 値を 23 に変更し、変更された SRID 値を確認する例を示します。  
  
```  
SET @g.STSrid = 23;  
SELECT @g.STSrid;  
```  
  
## <a name="see-also"></a>参照  
 [STX &#40;geometry データ型&#41;](../../t-sql/spatial-geometry/stx-geometry-data-type.md)   
 [STY &#40;geometry データ型&#41;](../../t-sql/spatial-geometry/sty-geometry-data-type.md)   
 [Geometry インスタンスの OGC メソッド](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  

