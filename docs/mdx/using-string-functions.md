---
title: "文字列関数の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- string functions
ms.assetid: 962e820a-a1f9-49b5-90f0-a05261e6682b
caps.latest.revision: 24
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 12fc2dca6c7a0eb1c7d126ef0cfdc87df869c878
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="using-string-functions"></a>文字列関数の使用
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  文字列関数は、多次元式 (MDX) 内のほとんどすべてのオブジェクトに対して使用できます。 ストアド プロシージャでは、主にオブジェクトを文字列表記に変換するために文字列関数を使用します。 また、文字列式をオブジェクトに対して評価して値を返すために文字列関数を使用することもできます。  
  
 最も広く使用されている文字列関数は**名前**と**Uniquename**です。 これらの関数はそれぞれ、オブジェクトの名前と一意の名前を返します。 ほとんどの場合、これらは、計算をデバッグする際に、関数によって返されるメンバーを検出するために使用されます。  
  
## <a name="examples"></a>使用例  
 次のクエリでは、これらの関数の使用方法を示しています。  
  
 `WITH`  
  
 `//Returns the name of the current Product on rows`  
  
 `MEMBER [Measures].[ProductName] AS [Product].[Product].CurrentMember.Name`  
  
 `//Returns the uniquename of the current Product on rows`  
  
 `MEMBER [Measures].[ProductUniqueName] AS [Product].[Product].CurrentMember.Uniquename`  
  
 `//Returns the name of the Product dimension`  
  
 `MEMBER [Measures].[ProductDimensionName] AS [Product].Name`  
  
 `SELECT  {[Measures].[ProductName],[Measures].[ProductUniqueName],[Measures].[ProductDimensionName]}`  
  
 `ON COLUMNS,`  
  
 `[Product].[Product].MEMBERS  ON ROWS`  
  
 `FROM [Adventure Works]`  
  
 **生成**を一連のすべてのメンバーに文字列関数を実行し、結果を連結関数を使用できます。 また、セットの内容を視覚化できるようになるため、計算をデバッグする際に役立つ場合もあります。 次の例では、この用途で関数を使用する方法を示します。  
  
 `WITH`  
  
 `//Returns the names of the current Product and its ancestors up to the All Member`  
  
 `MEMBER [Measures].[AncestorNames] AS`  
  
 `GENERATE(`  
  
 `ASCENDANTS([Product].[Product Categories].CurrentMember)`  
  
 `, [Product].[Product Categories].CurrentMember.Name, ", ")`  
  
 `SELECT`  
  
 `{[Measures].[AncestorNames]}`  
  
 `ON COLUMNS,`  
  
 `[Product].[Product Categories].MEMBERS  ON ROWS`  
  
 `FROM [Adventure Works]`  
  
 広く使われているもう 1 つのグループの文字列関数は、オブジェクトやそのオブジェクトに解決される式の一意の名前を含む文字列を、そのオブジェクト自体にキャストできるようにする関数です。 次の例のクエリを示していますが、どのように**StrToMember**と**StrToSet**関数は。  
  
 `SELECT`  
  
 `{StrToMember("[Measures].[Inter" + "net Sales Amount]")}`  
  
 `ON COLUMNS,`  
  
 `StrToSet("{`  
  
 `[Product].[Product Categories].[Category].&[3],`  
  
 `[Product].[Product Categories].[Product].&[477],`  
  
 `[Product].[Product Categories].[Product].&[788],`  
  
 `[Product].[Product Categories].[Product].&[708],`  
  
 `[Product].[Product Categories].[Product].&[711]`  
  
 `}")`  
  
 `ON ROWS`  
  
 `FROM [Adventure Works]`  
  
> [!NOTE]  
>  **StrToMember**と**StrToSet**関数を使用して、注意してください。 これらの関数を計算の定義内で使用すると、クエリのパフォーマンスが低下する場合があります。  
  
## <a name="see-also"></a>参照  
 [生成 (& a) #40 です。MDX と #41 です。](../mdx/generate-mdx.md)   
 [名前と #40 です。MDX と #41 です。](../mdx/name-mdx.md)   
 [UniqueName & #40 です。MDX と #41 です。](../mdx/uniquename-mdx.md)   
 [関数と #40 です。MDX 構文 &#41;](../mdx/functions-mdx-syntax.md)   
 [ストアド プロシージャ &#40; を使用します。MDX と #41 です。](../mdx/using-stored-procedures-mdx.md)   
 [StrToMember & #40 です。MDX と #41 です。](../mdx/strtomember-mdx.md)   
 [StrToSet & #40 です。MDX と #41 です。](../mdx/strtoset-mdx.md)  
  
  
