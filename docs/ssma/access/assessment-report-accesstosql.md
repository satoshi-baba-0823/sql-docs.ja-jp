---
title: 評価レポート (AccessToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Assessment Report dialog box
- Conversion Report dialog box
ms.assetid: ba6f53aa-0049-4c49-8bb8-607a8bfaa737
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: d6a73f88a0c1bc0ab2235241f7801c8fbc0f8328
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47660340"
---
# <a name="assessment-report-accesstosql"></a>評価レポート (AccessToSQL)
評価レポート ウィンドウには、データベース オブジェクトの変換の結果が表示されます。[!INCLUDE[tsql](../../includes/tsql-md.md)]構文、およびヘルプの複雑さと、移行プロジェクトのコストを見積もることができます。  
  
ソースのメタデータ エクスプ ローラーで変換するオブジェクトの選択、評価レポートを作成するを右クリックして**データベース**、し、**レポートの作成**です。 スキーマに変換した後このレポートを自動的に表示することもできます。 ただし、レポート名は、変換レポートになります。 詳細については、次を参照してください。[プロジェクトの設定 (GUI) (SSMA 一般的)](http://msdn.microsoft.com/cf06baf1-8714-48a3-95dc-781f6ca53693)します。  
  
## <a name="options"></a>および  
**エクスプ ローラー ペイン**  
評価レポート内のオブジェクトの階層が含まれています。 個々 のオブジェクトおよびサブコンポーネントを表示するフォルダーを展開します。 カテゴリまたはオブジェクトをクリックすると、詳細ウィンドウでそのカテゴリまたはオブジェクトの変換の統計情報が表示されます。  
  
**詳細ウィンドウ**  
選択したオブジェクトの統計情報またはエラーおよび警告のメッセージの変換を示しています。 たとえば、[テーブル] フォルダーを選択すると、詳細ウィンドウには外部キー、インデックス、主キー、および変換されたテーブルの数が表示されます。  
  
**[メッセージ] ウィンドウ**  
エラー、警告、および評価レポートの作成時に生成された情報メッセージを示しています。 メッセージは、番号でグループ化されます。  
  
メッセージの詳細を表示するには、いずれかをクリックして**エラー**、**警告**、または**メッセージ**、し、メッセージを展開します。 SSMA は、このエラーのあるオブジェクトの一覧に表示されます。 オブジェクトのすべての変換の詳細を表示するオブジェクトをクリックします。  
  
## <a name="see-also"></a>参照  
[ユーザー インターフェイスの Reference(Access)](http://msdn.microsoft.com/af24c303-4a41-449b-9c86-d6558a97e839)  
  
