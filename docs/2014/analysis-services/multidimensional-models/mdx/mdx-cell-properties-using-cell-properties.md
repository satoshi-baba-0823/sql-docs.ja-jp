---
title: セル プロパティ (MDX) の使用 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- intrinsic cell properties [MDX]
- cells [MDX]
- cell properties [MDX]
- CELL PROPERTIES keyword
ms.assetid: a593c74d-8c5e-485e-bd92-08f9d22451d4
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8aa9168e6272522bc773cb61166cb888d988c009
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48082812"
---
# <a name="using-cell-properties-mdx"></a>セル プロパティの使用 (MDX)
  多次元式 (MDX) でのセル プロパティには、キューブなどの多次元データ  ソース内のセルの内容や書式に関する情報が含まれます。  
  
 MDX では、固有のセル プロパティを取得するために MDX SELECT ステートメント内で CELL PROPERTIES キーワードを使用できます。 固有セル プロパティは、主にセル データを視覚的に表示するために利用されます。  
  
## <a name="cell-properties-keyword-syntax"></a>CELL PROPERTIES キーワードの構文  
 に対して次の構文を使用して、 `CELL PROPERTIES` MDX のキーワード`SELECT`ステートメント。  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
[<cell_props>]  
```  
  
 次の構文は、`<cell_props>` 値の形式、およびこの値の中で `CELL PROPERTIES` キーワードと 1 つまたは複数の固有セル プロパティを使用する方法を示しています。  
  
```  
<cell_props> ::= CELL PROPERTIES <property> [, <property>...]  
```  
  
## <a name="supported-intrinsic-cell-properties"></a>サポートされる固有セル プロパティ  
 次の表は、 `<property>` 値の中で使用可能な固有セル プロパティを示しています。  
  
|プロパティ|説明|  
|--------------|-----------------|  
|`ACTION_TYPE`|セルに対するアクションの種類を示すビットマスク。 このプロパティの値は、次のいずれか 1 つです。<br /><br /> **MDACTION_TYPE_URL**<br /><br /> **MDACTION_TYPE_HTML**<br /><br /> **MDACTION_TYPE_STATEMENT**<br /><br /> **MDACTION_TYPE_DATASET**<br /><br /> **MDACTION_TYPE_ROWSET**<br /><br /> **MDACTION_TYPE_COMMANDLINE**<br /><br /> **MDACTION_TYPE_PROPRIETARY**<br /><br /> **MDACTION_TYPE_REPORT**<br /><br /> **MDACTION_TYPE_DRILLTHROUGH**<br /><br /> <br /><br /> 注: WHERE 句内にセットを含むクエリの場合、ドリルスルー アクションは含まれません。|  
|**BACK_COLOR**|`VALUE` または `FORMATTED_VALUE` プロパティを表示するときの背景色。 詳しくは、「[FORE_COLOR および BACK_COLOR の内容 &#40;MDX&#41;](mdx-cell-properties-fore-color-and-back-color-contents.md)」をご覧ください。|  
|`CELL_ORDINAL`|データセット内のセルの序数。|  
|**FONT_FLAGS**|フォントの詳細な文字飾りを示すビットマスク。 たとえば、値 5 が太字の組み合わせを表します (`MDFF_BOLD`) と下線 (`MDFF_UNDERLINE`) フォントの文字飾り。 この値は、次の 1 つ以上の定数に対するビットごとの OR 演算の結果です。<br /><br /> `MDFF_BOLD` = 1<br /><br /> `MDFF_ITALIC` = 2<br /><br /> `MDFF_UNDERLINE` = 4<br /><br /> `MDFF_STRIKEOUT` = 8|  
|**FONT_NAME**|表示するために使用するフォント、`VALUE`または`FORMATTED_VALUE`プロパティ。|  
|**FONT_SIZE**|`VALUE` または `FORMATTED_VALUE` プロパティの表示に使用するフォント サイズ。|  
|**FORE_COLOR**|`VALUE` または `FORMATTED_VALUE` プロパティを表示するときの前景色。 詳しくは、「[FORE_COLOR および BACK_COLOR の内容 &#40;MDX&#41;](mdx-cell-properties-fore-color-and-back-color-contents.md)」をご覧ください。|  
|`FORMAT`|同じ`FORMAT_STRING`します。|  
|`FORMAT_STRING`|作成するために使用する書式指定文字列、`FORMATTED_VALUE`プロパティの値。 詳しくは、「[FORMAT_STRING の内容 &#40;MDX&#41;](mdx-cell-properties-format-string-contents.md)」をご覧ください。|  
|`FORMATTED_VALUE`|表示の書式設定を表す文字列、`VALUE`プロパティ。|  
|`LANGUAGE`|`FORMAT_STRING` を適用するロケール。 `LANGUAGE` 通貨換算の通常使用されます。|  
|`UPDATEABLE`|セルが更新可能かどうかを示す値。 このプロパティの値は、次のいずれか 1 つです。<br /><br /> `MD_MASK_ENABLED` (0x00000000) セルは更新できます。<br /><br /> `MD_MASK_NOT_ENABLED` (0x10000000) セルを更新することはできません。<br /><br /> `CELL_UPDATE_ENABLED` (0x00000001) セルはセル セットで更新できます。<br /><br /> `CELL_UPDATE_ENABLED_WITH_UPDATE` (0x00000002) セルは update ステートメントで更新できます。 書き込み可能でないリーフ セルが更新される場合、UPDATE は失敗する可能性があります。<br /><br /> `CELL_UPDATE_NOT_ENABLED_FORMULA` セルにすることはできません (0x10000001) セルの座標の間で計算されるメンバーがあるため、更新where で一連のセルが取得された句。 数式がセルの値に影響を与える、あるいは計算されるセルが集計パス上にあるとしても、セルの更新は行われます。 この場合、結果が計算に影響されるため、セルの最終的な値は更新後の値にならない可能性があります。<br /><br /> `CELL_UPDATE_NOT_ENABLED_NONSUM_MEASURE` (0x10000002) 合計でないメジャー (カウント、最小、最大値、個別のカウント、準加法) は更新できませんので、セルを更新できません。<br /><br /> `CELL_UPDATE_NOT_ENABLED_NACELL_VIRTUALCUBE` (0x10000003) セルは、メジャーの交差部分には、メジャーのメジャー グループには無関係なディメンション メンバー、セルが存在しないため、更新できません。<br /><br /> `CELL_UPDATE_NOT_ENABLED_SECURE` (0x10000005) セルのセキュリティで保護されているために、セルを更新できません。<br /><br /> `CELL_UPDATE_NOT_ENABLED_CALCLEVEL` (0x10000006) 将来使用するために予約されています。<br /><br /> `CELL_UPDATE_NOT_ENABLED_CANNOTUPDATE` (0x10000007) 内部的な理由のため、セルは更新できません。<br /><br /> `CELL_UPDATE_NOT_ENABLED_INVALIDDIMENSIONTYPE` (0x10000009) マイニング モデルでは、間接的、またはデータ マイニング ディメンションでは、更新はサポートされていないために、セルを更新できません。|  
|`VALUE`|書式設定されていないセルの値。|  
  
 のみ、 `CELL_ORDINAL`、 `FORMATTED_VALUE`、および`VALUE`セル プロパティは必須です。 固有またはプロバイダー固有を問わず、すべてのセル プロパティは、そのデータ型およびプロバイダーのサポートを含めて、`PROPERTIES` スキーマ行セットで定義します。 詳細については、`PROPERTIES`スキーマ行セットを参照してください[MDSCHEMA_PROPERTIES 行セット](../../schema-rowsets/ole-db-olap/mdschema-properties-rowset.md)します。  
  
 既定では場合、`CELL PROPERTIES`キーワードが使用されない場合、返されるセル プロパティは`VALUE`、 `FORMATTED_VALUE`、および`CELL_ORDINAL`(この順序で)。 場合、`CELL PROPERTIES`キーワードを使用して、キーワードで明示的に記述されたセル プロパティだけが返されます。  
  
 次の例では、使用、 `CELL PROPERTIES` MDX クエリ内のキーワード。  
  
```  
SELECT  
   {[Measures].[Reseller Gross Profit]} ON COLUMNS,  
   {[Reseller].[Reseller Type].[Reseller Name].Members} ON ROWS  
FROM [Adventure Works]  
CELL PROPERTIES VALUE, FORMATTED_VALUE, FORMAT_STRING, FORE_COLOR, BACK_COLOR  
```  
  
 セル プロパティは、フラット化された行セットを返す MDX クエリの場合は返されません場合のみとここでは、各セルが表される、`FORMATTED_VALUE`セル プロパティが返されました。  
  
## <a name="setting-cell-properties"></a>セル プロパティの設定  
 セル プロパティは、 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] のさまざまな場所で設定できます。 たとえば、Format String プロパティは、 [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]のキューブ エディターの [キューブ構造] タブで、標準メジャーに対して設定できます。同じプロパティをキューブ エディターの [計算] タブで、キューブで定義されている計算されるメジャーに対して設定できます。クエリの WITH 句で定義されている計算されるメジャーも、その書式設定文字列をそこで定義されます。次のクエリでは、計算されるメジャーに対してセル プロパティを設定する方法を示しています。  
  
```  
WITH MEMBER MEASURES.CELLPROPERTYDEMO AS [Measures].[Internet Sales Amount]  
, FORE_COLOR=RGB(0,0,255)  
, BACK_COLOR=IIF([Measures].[Internet Sales Amount]>7000000, RGB(255,0,0), RGB(0,255,0))  
, FONT_SIZE=10  
, FORMAT_STRING='#,#.000'  
SELECT MEASURES.CELLPROPERTYDEMO ON 0,  
[Date].[Calendar Year].[Calendar Year].MEMBERS ON 1  
FROM [Adventure Works]  
CELL PROPERTIES VALUE, FORMATTED_VALUE, FORE_COLOR, BACK_COLOR, FONT_SIZE  
```  
  
## <a name="see-also"></a>参照  
 [MDX クエリの基礎&#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md)  
  
  
