---
title: sum 関数 (XQuery) |Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- sum function [XQuery]
- fn:sum function
ms.assetid: 12288f37-b54c-4237-b75e-eedc5fe8f96d
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 802c870f2ea22d24d8dfa80144a44f8805a14c96
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47619960"
---
# <a name="aggregate-functions---sum"></a>集計関数 - sum
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  一連の数値の合計を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
fn:sum($arg as xdt:anyAtomicType*) as xdt:anyAtomicType  
```  
  
## <a name="arguments"></a>引数  
 *$arg*  
 合計が計算される、一連のアトミック値。  
  
## <a name="remarks"></a>コメント  
 すべての種類に渡されるアトミック値の**sum()** 同じ基本型のサブタイプにする必要があります。 使用できる基本データ型は、3 つの組み込みの数値基本データ型または xdt:untypedAtomic です。 xdt:untypedAtomic 型の値は、xs:double にキャストされます。 これらの型の混在がある場合、またはその他の種類の他の値が渡された場合は、静的エラーが発生します。  
  
 結果**sum()** 場合でも、入力が空のシーケンスで必要に応じて、xs:double、xdt:untypedAtomic の場合などに渡された型の基本型を受け取ります。 入力が静的に空の場合、結果は静的な型および動的な型 xs:integer の 0 になります。  
  
 **Sum()** 関数は、数値の合計を返します。 Xdt:untypedAtomic 値は、xs:double にキャストできない場合で、入力シーケンスの値が無視されます。 *$arg*します。 入力が動的に計算された空のシーケンスの場合、使用されている基本データ型の値 0 が返されます。  
  
 オーバーフローまたは範囲外の例外が発生したとき、関数は実行時エラーを返します。  
  
## <a name="examples"></a>使用例  
 このトピックではさまざまなに格納されている XML インスタンスに対して XQuery の例について**xml**内の列を入力、[!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]データベース。  
  
### <a name="a-using-the-sum-xquery-function-to-find-the-total-combined-number-of-labor-hours-for-all-work-center-locations-in-the-manufacturing-process"></a>A. sum() XQuery 関数を使用した、製造プロセス内のすべてのワーク センターの場所での合計労働時間の計算  
 次のクエリでは、製造手順が格納されているすべての製品モデルの製造プロセスにおける、すべてのワーク センターの場所での合計労働時間を計算します。  
  
```  
SELECT Instructions.query('         
   declare namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";         
  <ProductModel PMID= "{ sql:column("Production.ProductModel.ProductModelID") }"         
  ProductModelName = "{ sql:column("Production.ProductModel.Name") }" >         
   <TotalLaborHrs>         
     { sum(//AWMI:Location/@LaborHours) }         
   </TotalLaborHrs>         
 </ProductModel>         
    ') as Result         
FROM Production.ProductModel         
WHERE Instructions is not NULL         
```  
  
 次に結果の一部を示します。  
  
```  
<ProductModel PMID="7" ProductModelName="HL Touring Frame">  
   <TotalLaborHrs>12.75</TotalLaborHrs>  
</ProductModel>  
<ProductModel PMID="10" ProductModelName="LL Touring Frame">  
  <TotalLaborHrs>13</TotalLaborHrs>  
</ProductModel>  
...  
```  
  
 結果を XML として返す代わりに、次のクエリに示すように、リレーショナル結果を生成するクエリを記述できます。  
  
```  
SELECT ProductModelID,         
        Name,         
        Instructions.value('declare namespace   
      AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";         
    sum(//AWMI:Location/@LaborHours)', 'float') as TotalLaborHours         
FROM Production.ProductModel         
WHERE Instructions is not NULL          
```  
  
 これは、結果の一部です。  
  
```  
ProductModelID Name                 TotalLaborHours         
-------------- -------------------------------------------------  
7              HL Touring Frame           12.75                   
10             LL Touring Frame           13                      
43             Touring Rear Wheel         3                       
...  
```  
  
### <a name="implementation-limitations"></a>実装の制限事項  
 制限事項を次に示します。  
  
-   1 つの引数のバージョンのみ**sum()** はサポートされています。  
  
-   入力が動的に計算された空のシーケンスである場合、xs:integer 型ではなく、使用されている基本データ型の値 0 が返されます。  
  
-   **Sum()** 関数では、すべての整数値を xs:decimal にマップします。  
  
-   **Sum()** xs:duration 型の値に対して関数がサポートされていません。  
  
-   基本データ型の境界を超えて複数の型が混在するシーケンスはサポートされません。  
  
-   sum((xs:double(“INF”), xs:double(“-INF”))) ではドメイン エラーが発生します。  
  
## <a name="see-also"></a>参照  
 [xml データ型に対する XQuery 関数](../xquery/xquery-functions-against-the-xml-data-type.md)  
  
  
