---
title: 有効なブール値 (XQuery) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- effective Boolean value [XQuery]
- Boolean values
- XQuery, effective Boolean values
- EBV
ms.assetid: 506682b1-b6c9-45e2-aa54-7abd5844c3f1
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 27c4c66d2216d582137b12e7c595dd1dc75fe166
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47719380"
---
# <a name="effective-boolean-value-xquery"></a>有効なブール値 (XQuery)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  次に有効なブール値を示します。  
  
-   オペランドが空のシーケンスまたはブール型の false である場合、false になります。  
  
-   それ以外の場合、値は true になります。  
  
 有効なブール値は、1 つのブール値、ノード シーケンス、または空のシーケンスを返す式で計算できます。 次の型の式が処理されるとき、ブール値が暗黙的に計算されます。  
  
-   論理式  
  
-   [機能しません。](../xquery/functions-on-boolean-values-not-function.md)  
  
-   FLWOR 式の WHERE 句  
  
-   [条件式](../xquery/conditional-expressions-xquery.md)  
  
-   [QuantifiedeExpressions](../xquery/quantified-expressions-xquery.md)  
  
 次に、有効なブール値の例を示します。 ときに、**場合**式が処理される場合、条件の有効なブール値が決定されます。 `/a[1]`が空のシーケンスを返す有効なブール値は false。 1 つのテキスト ノード (false) を含む XML として結果が返されます。  
  
```  
value is false  
DECLARE @x XML  
SET @x = '<b/>'  
SELECT @x.query('if (/a[1]) then "true" else "false"')  
go  
```  
  
 次の例では、式が空ではないシーケンスを返すので、有効なブール値は true になります。  
  
```  
DECLARE @x XML  
SET @x = '<a/>'  
SELECT @x.query('if (/a[1]) then "true" else "false"')  
go  
```  
  
 ときに型指定されたクエリを実行する**xml**列または変数、ブール型のノードを持つことができます。 **Data()** ここではブール値を返します。 クエリ式がブール値 true を返す場合、次の例で示すように、有効なブール値は true になります。 この例では、次のことも示しています。  
  
-   XML スキーマ コレクションが作成されます。 要素\<b > コレクションでのブール型です。  
  
-   型指定された**xml**変数が作成され、クエリを実行します。  
  
-   式`data(/b[1])`ブール値 true を返します。 したがって、この場合の有効なブール値は true になります。  
  
-   式`data(/b[2])`ブール値 false を返します。 したがって、この場合の有効なブール値は false になります。  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
      <element name="s" type="string"/>  
      <element name="b" type="boolean"/>  
</schema>'  
go  
DECLARE @x XML(SC)  
SET @x = '<b>true</b><b>false</b>'  
SELECT @x.query('if (data(/b[1])) then "true" else "false"')  
SELECT @x.query('if (data(/b[2])) then "true" else "false"')  
go  
```  
  
## <a name="see-also"></a>参照  
 [XQuery の基礎](../xquery/xquery-basics.md)   
 [FLWOR ステートメントおよびイテレーション&#40;XQuery&#41;](../xquery/flwor-statement-and-iteration-xquery.md)  
  
  
