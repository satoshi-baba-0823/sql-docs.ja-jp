---
title: ToggleDrillState (MDX) |Microsoft ドキュメント
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: a2ed3251b5bf8bc17e832f87947cfc41231d35c0
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34743431"
---
# <a name="toggledrillstate-mdx"></a>ToggleDrillState (MDX)


  ドリル ダウンおよびドリルアップ モードの間でメンバーのドリル状態を切り替えます。  
  
## <a name="syntax"></a>構文  
  
```  
  
ToggleDrillState(Set_Expression1,Set_Expression2 [, [RECURSIVE] [,INCLUDE_CALC_MEMBERS] ] )  
```  
  
## <a name="arguments"></a>引数  
 *Set_Expression1*  
 セットを返す有効な多次元式 (MDX) です。  
  
 *Set_Expression2*  
 セットを返す有効な多次元式 (MDX) です。  
  
 *再帰*  
 (省略可)。 セットの再帰的な比較を示すキーワードです。 **ToggleDrillState**関数は、の組み合わせ、 **DrillupMember**と**DrilldownMember**関数。 再帰メンバーがの場合にのみ適用されます、 **DrilldownMember**状態です。  
  
 *Include_calc_members*  
 (省略可)。 計算されるメンバーがドリルダウン レベルに存在する場合にそれらを含めるかどうかを示すフラグです。  
  
## <a name="remarks"></a>コメント  
 **ToggleDrillState**関数は、最初のセットに存在する 2 番目のセットの各メンバーのドリル状態を切り替えます。 1 番目のセットには任意の次元の組を含めることができますが、2 番目のセットには単一の次元のメンバーしか含めることができません。 **ToggleDrillState**関数は、の組み合わせ、 **DrillupMember**と**DrilldownMember**関数。 場合、メンバーを*m*、2 番目のセットが最初のセット内に存在し、そのメンバーがドリル ダウンされている (つまり、直下に子孫が)、`DrillupMember(Set_Expression1, {m})`は、最初のセット内の組またはメンバーに適用します。 場合は、その*m*メンバーがドリル アップされている (つまり、子孫が存在しないの*m*の直下*m*)、`DrilldownMember(Set_Expression1, {m}[, RECURSIVE])`は最初のセットに適用します。  
  
 場合、省略可能な**再帰**フラグが使用されて、ドリル アップおよびドリル ダウンが再帰的に適用します。 Recursive フラグの詳細については、次を参照してください。、 [DrillupMember](../mdx/drillupmember-mdx.md)と[DrilldownMember](../mdx/drilldownmember-mdx.md)関数。  
  
 XMLA プロパティの mdpropmdxdrillfunctions にクエリを使用すると、サーバーがドリル関数以外が提供するサポートのレベルを確認するには参照してください[サポートされる XMLA プロパティ&#40;XMLA&#41; ](../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md)詳細についてはします。  
  
 参照してください[Database Journal: MDX Set Functions: The ToggleDrillState() Function](http://go.microsoft.com/fwlink/?LinkId=517759)のシナリオと例をこの関数を含むです。  
  
## <a name="example"></a>例  
 次の例では、1 番目のセットの Australia メンバーをドリル ダウンし、1 番目のセットの United States メンバーをドリル アップしています。  
  
```  
SELECT ToggleDrillState  
   ({[Geography].[Geography].[Country].Members, [Geography].[Geography].[Country].&[United States].Children},  
      {[Geography].[Geography].[Country].[Australia]  
      , [Geography].[Geography].[Country].&[United States]}  
      --, recursive  
      --, include_calc_members  
   ) ON 0  
   FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>参照  
 [MDX 関数リファレンス&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
