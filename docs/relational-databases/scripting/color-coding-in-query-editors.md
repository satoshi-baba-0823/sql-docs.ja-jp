---
title: クエリ エディターでのコードの色分け | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: scripting
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 25392403e587451d44a000ab78b904626f4f0dd7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47852545"
---
# <a name="color-coding-in-query-editors"></a>クエリ エディターでのコードの色分け
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
  コード エディターで入力されたテキストにはカテゴリが割り当てられ、それぞれのカテゴリが色分けされます。 色分けによってコード内のテキストをすばやく見つけることができます。 たとえば、濃い緑を使用してコメントが目立つようにします。 次の表では、最も一般的な色を示します。 **[ツール]** の **[オプション]** メニューを使用して、色とカテゴリの完全な一覧を表示して、独自の配色を構成できます。 既定の色を変更する方法の詳細については、「 [フォントの色、サイズ、およびスタイルを変更する方法](../../relational-databases/scripting/change-font-color-size-and-style.md)」を参照してください。  
  
## <a name="default-code-colors"></a>コードの既定の色分け  
  
|色|カテゴリ|  
|-----------|--------------|  
|[赤]|SQL 文字列|  
|緑|解説|  
|黒 (背景は銀色)|SQLCMD コマンド|  
|赤紫|システム関数|  
|[緑]|システム テーブル、ビュー、またはテーブル値関数。 sys および INFORMATION_SCHEMA のすべてのシステム スキーマ。|  
|[青]|Keyword|  
|青緑|行番号またはテンプレート パラメーター|  
|茶色|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ストアド プロシージャ (stored procedure)|  
|灰色|演算子|  
  
## <a name="status-bar"></a>ステータス バー  
 オブジェクト エクスプローラーで、登録済みサーバーまたは [!INCLUDE[ssDE](../../includes/ssde-md.md)] サーバーが [!INCLUDE[ssDE](../../includes/ssde-md.md)] クエリ エディターのステータス バーに別の色で表示されるように構成することができます。 そうすることで、多くのウィンドウを同時に開いているときに、各エディター ウィンドウがどのサーバーに接続しているかを識別しやすくなります。 ステータス バーの色の設定の詳細については、「[ステータス バー &#40;データベース エンジン クエリ エディター&#41;](../../relational-databases/scripting/status-bar-database-engine-query-editor.md)」を参照してください。  
  
 エディターの種類によっては、ステータス バーが表示されない場合や、複数の色がサポートされていない場合があります。  
  
  
