---
title: 多次元データを扱う |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- multidimensional data [ADO]
ms.assetid: 84387746-aa3e-44fd-ad6c-a8214a6966dc
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f7721018d887fdb4c24293c4076f384167f38a55
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47695080"
---
# <a name="working-with-multidimensional-data"></a>多次元データの操作
A*セルセット*多次元データに対するクエリの結果です。 軸、以下の 4 つの軸は、通常、通常 2 つまたは 3 つのコレクションで構成されます。 *軸*を探すか、キューブ内の特定の値をフィルター処理に使用される 1 つまたは複数のディメンションのメンバーのコレクションです。  
  
 A*位置*軸に沿ったポイントです。 1 つのディメンションで構成される軸では、それらの位置は、ディメンション メンバーのサブセットです。 軸は、1 つ以上のディメンションのかどうかは、各位置が、複合エンティティは、 *n* where 部分*n*その軸に沿った指向ディメンションの数です。 位置の各部分は、1 つの構成要素であるディメンションのメンバーです。  
  
 たとえば、売上データを格納しているキューブから、Geography、Product のディメンションは、セルセットの x 軸に沿って方向は、場合この軸に沿った位置含めることができます"USA"と「コンピューター」メンバー この例では、x 軸に沿った位置を決定するが各ディメンションのメンバーが軸に沿った指向が必要です。  
  
 A*セル*は軸の座標が交差する位置に配置されているオブジェクトです。 各セルには、データ自体、書式設定された文字列 (セルのデータの表示可能な項目のフォーム)、およびセルの序数値を含む、関連付けられている情報の複数の部分。 (各セルはセルセットの一意の序数値です。 セル セットの最初のセルの序数値は 0、8 つの列を含むセル セットの 2 行目で一番左のセル序数値は 8 になります。)  
  
 たとえば、キューブには、次の 6 つのディメンション (で指定された例から、このキューブ スキーマが若干異なりますに注意してください。[多次元スキーマの概要とデータ](../../../ado/guide/multidimensional/overview-of-multidimensional-schemas-and-data.md))。  
  
-   営業担当者  
  
-   Geography (自然階層): 大陸、国、州、およびなど  
  
-   四半期、四半期、月、日  
  
-   Years  
  
-   メジャー、Sales、PercentChange、BudgetedSales  
  
-   Products  
  
 次のセル セットでは、1991 すべての製品の売上を表します。  
  
> [!NOTE]
>  セルの値の例では、最初の桁が x 軸の位置と y 軸の位置に、2 番目の数字を表す軸位置の序数の順序付けされたペアとして表示できます。  
  
 このセル セットの特性は次のとおりです。  
  
-   軸ディメンション: 四半期数、販売員、Geography  
  
-   ディメンションをフィルター処理: メジャー、年の製品  
  
-   2 つの軸: (x、または軸 0) の列と行 (y または軸 1)  
  
-   x 軸: 入れ子になった 2 つの販売員と Geography ディメンションは、  
  
-   y 軸: 四半期のディメンション  
  
 X 軸が 2 つの入れ子になったディメンション: 販売員と Geography です。 Geography 型から 4 つのメンバーが選択されている: シアトル、ボストン、米国南部、および日本です。 営業担当者から 2 つのメンバーが選択されている: バレンタイン"と"Nash します。 この軸 (2 * 8 = 4) の 8 つの位置の合計が生成されます。  
  
 各座標が 2 つのメンバーの位置として表されます: Geography ディメンションから別の販売員のディメンションと 1 つ。  
  
```  
(Valentine, Seattle), (Valentine, Boston), (Valentine, USA_North),  
(Valentine, Japan), (Nash, Seattle), (Nash, Boston), (Nash, USA_North),  
(Nash, Japan)  
```  
  
 Y 軸には、次の 8 つの位置を含む 1 つだけのディメンションがあります。  
  
```  
Jan, Feb, Mar, Qtr2, Qtr3, Oct, Nov, Dec  
```  
  
 セル セット、セル、軸、および位置はすべてで表される ADO MD で対応するオブジェクト:[セルセット](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)、[セル](../../../ado/reference/ado-md-api/cell-object-ado-md.md)、[軸](../../../ado/reference/ado-md-api/axis-object-ado-md.md)、および[位置](../../../ado/reference/ado-md-api/position-object-ado-md.md).  
  
## <a name="see-also"></a>関連項目  
 [ADO MD オブジェクト モデル](../../../ado/reference/ado-md-api/ado-md-object-model.md)   
 [ADO (多次元) (ADO MD)](../../../ado/guide/multidimensional/ado-multidimensional-ado-md.md)   
 [多次元スキーマとデータの概要](../../../ado/guide/multidimensional/overview-of-multidimensional-schemas-and-data.md)   
 [ADO MD を使用したプログラミング](../../../ado/guide/multidimensional/programming-with-ado-md.md)   
 [ADO MD と ADO の併用](../../../ado/guide/multidimensional/using-ado-with-ado-md.md)
