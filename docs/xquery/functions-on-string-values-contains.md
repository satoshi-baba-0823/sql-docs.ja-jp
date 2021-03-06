---
title: contains 関数 (XQuery) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- contains function (XQuery)
- fn:contains function
ms.assetid: 2c88c015-04fc-429b-84b2-835596a28b65
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 595d5fb7d98d85120fca3b96eedc5a83694dc1a7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47753920"
---
# <a name="functions-on-string-values---contains"></a>文字列値に使用する関数 - contains
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  示す xs:boolean 型の値を返すかどうかの値*ドル arg1*によって指定された文字列値を含む*ドル arg2*します。  
  
## <a name="syntax"></a>構文  
  
```  
  
fn:contains ($arg1 as xs:string?, $arg2 as xs:string?) as xs:boolean?  
```  
  
## <a name="arguments"></a>引数  
 *$arg1*  
 評価対象の文字列の値。  
  
 *$arg2*  
 検索するサブストリング。  
  
## <a name="remarks"></a>コメント  
 場合の値*ドル arg2* 、長さ 0 の文字列関数で返される**True**します。 場合の値*ドル arg1*長さ 0 の文字列の値が*ドル arg2*が長さ 0 の文字列を返します**False**します。  
  
 場合の値*ドル arg1*または*ドル arg2*空のシーケンスでは、引数が長さ 0 の文字列として扱われます。  
  
 contains() 関数では、文字列の比較に XQuery の既定の Unicode コード ポイントの照合順序が使用されます。  
  
 指定された部分文字列値*ドル arg2* 4000 文字未満である必要があります。 指定された値が 4,000 文字よりも大きい場合は、動的エラーが発生し、contains() 関数は空のシーケンスのブール値ではなくを返します**True**または**False**します。 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] では XQuery 式に対して動的なエラーは発生しません。  
  
 小文字の比較を取得するために、[大文字](../xquery/functions-on-string-values-upper-case.md)または lower-case 関数を使用できます。  
  
## <a name="supplementary-characters-surrogate-pairs"></a>補助文字 (サロゲート ペア)  
 XQuery 関数におけるサロゲート ペアの動作は、データベースの互換性レベルに左右されます。場合によっては、関数の既定の名前空間 URI に左右されることもあります。 詳細については、のトピックでは、「XQuery 関数はサロゲート対応」のセクションを参照してください。 [SQL Server 2016 におけるデータベース エンジン機能の重大な変更](../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md)します。 参照してください[ALTER DATABASE 互換性レベル&#40;TRANSACT-SQL&#41; ](../t-sql/statements/alter-database-transact-sql-compatibility-level.md)と[Collation and Unicode Support](../relational-databases/collations/collation-and-unicode-support.md)します。  
  
## <a name="examples"></a>使用例  
 このトピックでは、AdventureWorks データベース内のさまざまな xml 型列に格納されている XML インスタンスに対して XQuery の例を示します。  
  
### <a name="a-using-the-contains-xquery-function-to-search-for-a-specific-character-string"></a>A. contains() XQuery 関数を使用した特定の文字列の検索  
 次のクエリでは、概要説明に Aerodynamic という単語が含まれている製品を検索します。 クエリは、該当製品の ProductID と <`Summary`> 要素を返します。  
  
```  
--The product model description document uses  
--namespaces. The WHERE clause uses the exit()  
--method of the xml data type. Inside the exit method,  
--the XQuery contains()function is used to  
--determine whether the <Summary> text contains the word  
--Aerodynamic.   
  
USE AdventureWorks  
GO  
WITH XMLNAMESPACES ('http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS pd)  
SELECT ProductModelID, CatalogDescription.query('  
      <Prod>  
         { /pd:ProductDescription/@ProductModelID }  
         { /pd:ProductDescription/pd:Summary }  
      </Prod>  
 ') as Result  
FROM Production.ProductModel  
where CatalogDescription.exist('  
   /pd:ProductDescription/pd:Summary//text()  
    [contains(., "Aerodynamic")]') = 1  
```  
  
 [結果]  
  
 `ProductModelID Result`  
  
 `-------------- ---------`  
  
 `28     <Prod ProductModelID="28">`  
  
 `<pd:Summary xmlns:pd=`  
  
 `"http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">`  
  
 `<p1:p xmlns:p1="http://www.w3.org/1999/xhtml">`  
  
 `A TRUE multi-sport bike that offers streamlined riding and`  
  
 `a revolutionary design. Aerodynamic design lets you ride with`  
  
 `the pros, and the gearing will conquer hilly roads.</p1:p>`  
  
 `</pd:Summary>`  
  
 `</Prod>`  
  
## <a name="see-also"></a>参照  
 [xml データ型に対する XQuery 関数](../xquery/xquery-functions-against-the-xml-data-type.md)  
  
  
