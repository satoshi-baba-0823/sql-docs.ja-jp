---
title: 入力システム (XQuery) |Microsoft Docs
ms.custom: ''
ms.date: 08/10/2016
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- sequence [XQuery]
- type system [XQuery]
- typed values [XQuery]
- XQuery, sequence
- string values [XQuery]
- XQuery, XPath data type namespace
- xdt prefix [XML in SQL Server]
- XQuery, type system
- built-in XML schema types [SQL Server]
- xs prefix [XML in SQL Server]
ms.assetid: 22d6f861-d058-47ee-b550-cbe9092dcb12
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 18294a9ecfea469d0f7a2c85dd4ce22ddf419fef
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47675480"
---
# <a name="type-system-xquery"></a>型システム (XQuery)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  XQuery は、スキーマ型に対しては厳密に型指定された言語で、型指定されていないデータに対しては厳密には型指定されていない言語です。 XQuery の定義済みの型には、次のものがあります。  
  
-   内の XML スキーマの組み込み型、 **http://www.w3.org/2001/XMLSchema**名前空間。  
  
-   定義された型、 **http://www.w3.org/2004/07/xpath-datatypes**名前空間。  
  
 このトピックでは、次の内容についても説明します。  
  
-   型指定された値とノードの文字列値。  
  
-   [データ関数&#40;XQuery&#41; ](../xquery/data-accessor-functions-data-xquery.md)と[string 関数&#40;XQuery&#41;](../xquery/data-accessor-functions-string-xquery.md)します。  
  
-   式から返されるシーケンス型の照合。  
  
## <a name="built-in-types-of-xml-schema"></a>XML スキーマの組み込み型  
 XML スキーマの組み込み型には、xs という定義済みの名前空間プレフィックスが付いています。 これらの種類のものが**xs:integer**と**xs:string**します。 これらの組み込み型はすべてサポートされます。 XML スキーマ コレクションを作成するときに、これらの型を使用できます。  
  
 型指定された XML のクエリを実行するとき、ノードの静的および動的な型は、クエリの対象の列または変数に関連付けられた XML スキーマ コレクションによって決まります。 静的および動的な型の詳細については、次を参照してください。[式コンテキストとクエリの評価&#40;XQuery&#41;](../xquery/expression-context-and-query-evaluation-xquery.md)します。 次のクエリを指定するなど、型指定されたに対して**xml**列 (`Instructions`)。 式を使用して`instance of`ことを確認する型指定された値の`LotSize`返される属性は`xs:decimal`型。  
  
```  
SELECT Instructions.query('  
   DECLARE namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
   data(/AWMI:root[1]/AWMI:Location[@LocationID=10][1]/@LotSize)[1] instance of xs:decimal  
') AS Result  
FROM Production.ProductModel  
WHERE ProductModelID=7  
```  
  
 この型指定情報は、列に関連付けられた XML スキーマ コレクションによって提供されます。  
  
## <a name="types-defined-in-xpath-data-types-namespace"></a>XPath データ型の名前空間で定義されている型  
 定義された型、 **http://www.w3.org/2004/07/xpath-datatypes**名前空間の定義済みのプレフィックスがある**xdt**します。 これらの型には、次のことが当てはまります。  
  
-   XML スキーマ コレクションを作成しているときは、これらの型を使用できません。 これらの型が、XQuery 型システムで使用され、使わ[XQuery と静的な型指定](../xquery/xquery-and-static-typing.md)します。 たとえば、アトミック型にキャストできます**xdt:untypedAtomic**の**xdt**名前空間。  
  
-   型指定されていない XML のクエリを実行する場合、要素ノードの静的および動的な型は**xdt: 型指定されていない**、および属性値の型は**xdt:untypedAtomic**します。 結果、 **query()** メソッドに型指定されていない XML が生成されます。 これは、XML ノードとして返されることを意味**xdt: 型指定されていない**と**xdt:untypedAtomic**、それぞれします。  
  
-   **Xdt:dayTimeDuration**と**xdt:yearMonthDuration**型がサポートされていません。  
  
 次の例では、型指定されていない XML 変数に対してクエリを指定しています。 式では、 `data(/a[1]`)、1 つのアトミック値のシーケンスを返します。 `data()`関数要素の型指定された値を返します`<a>`します。 クエリ対象の XML は型指定されていないので、返される値は `xdt:untypedAtomic` 型です。 そのため、 `instance of` true を返します。  
  
```  
DECLARE @x xml  
SET @x='<a>20</a>'  
SELECT @x.query( 'data(/a[1]) instance of xdt:untypedAtomic' )  
```  
  
 次の例の式 (`/a[1]`) は、型指定された値を取得するのではなく、要素 `<a>` という 1 つの要素のシーケンスを返します。 `instance of`式では、要素のテストを使用して、式によって返される値が要素ノードであることを確認`xdt:untyped type`します。  
  
```  
DECLARE @x xml  
SET @x='<a>20</a>'  
-- Is this an element node whose name is "a" and type is xdt:untyped.  
SELECT @x.query( '/a[1] instance of element(a, xdt:untyped?)')  
-- Is this an element node of type xdt:untyped.  
SELECT @x.query( '/a[1] instance of element(*, xdt:untyped?)')  
-- Is this an element node?  
SELECT @x.query( '/a[1] instance of element()')  
```  
  
> [!NOTE]  
>  型指定された XML インスタンスにクエリを実行して、クエリ式に parent 軸が含まれるときは、結果のノードの静的な型情報は使用できなくなります。 ただし、動的な型はノードに関連付けられたままです。  
  
## <a name="typed-value-vs-string-value"></a>型指定された値と文字列値  
 どのノードにも型指定された値と文字列値があります。 型指定された XML データの場合、型指定された値の型は、クエリ対象の列または変数に関連付けられた XML スキーマ コレクションによって提供されます。 XML データの型指定されていない、型指定された値の型は**xdt:untypedAtomic**します。  
  
 使用することができます、 **data()** または**string()** ノードの値を取得します。  
  
-   [データ関数&#40;XQuery&#41; ](../xquery/data-accessor-functions-data-xquery.md)ノードの型指定された値を返します。  
  
-   [String 関数&#40;XQuery&#41; ](../xquery/data-accessor-functions-string-xquery.md)ノードの文字列値を返します。  
  
 次の XML スキーマ コレクションで、<`root`> 整数型の要素が定義されています。  
  
```  
CREATE XML SCHEMA COLLECTION SC AS N'  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
      <element name="root" type="integer"/>  
</schema>'  
GO  
```  
  
 次の例の式では、最初に `/root[1]` の型指定された値を取得してから、その値に `3` を加算しています。  
  
```  
DECLARE @x xml(SC)  
SET @x='<root>5</root>'  
SELECT @x.query('data(/root[1]) + 3')  
```  
  
 次の例では、式の `string(/root[1])` から文字列型の値が返されるので、式が失敗します。 返された値は、オペランドとして数値型の値しか受け取らない算術演算子に渡されます。  
  
```  
-- Fails because the argument is string type (must be numeric primitive type).  
DECLARE @x xml(SC)  
SET @x='<root>5</root>'  
SELECT @x.query('string(/root[1]) + 3')  
```  
  
 次の例では、`LaborHours` 属性の合計を計算しています。 `data()`関数の型指定された値を取得する`LaborHours`からすべての属性、<`Location`> 製品モデルの要素。 関連付けられている XML スキーマに従って、`Instruction`列、`LaborHours`の**xs:decimal**型。  
  
```  
SELECT Instructions.query('   
DECLARE namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";   
             sum(data(//AWMI:Location/@LaborHours))   
') AS Result   
FROM Production.ProductModel   
WHERE ProductModelID=7  
```  
  
 このクエリにより、結果として 12.75 が返されます。  
  
> [!NOTE]  
>  明示的な使用、 **data()** 関数がこの例では、例示のみを目的。 指定されていない場合**sum()** 暗黙的に適用されます、 **data()** ノードの型指定された値を抽出する関数。  
  
## <a name="see-also"></a>参照  
 [SQL Server プロファイラーのテンプレートと権限](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md)   
 [XQuery の基礎](../xquery/xquery-basics.md)  
  
  
