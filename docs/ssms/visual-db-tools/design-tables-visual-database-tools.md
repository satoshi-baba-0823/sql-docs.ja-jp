---
title: テーブルの作成と更新 (SSMS) | Microsoft Docs
ms.custom: ''
ms.date: 08/25/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], Table Designer
- Table Designer, designing tables
- opening tables
- opening Table Designer
- tables [SQL Server], opening
- Table Designer, opening
ms.assetid: c49e0155-5dcb-481f-9538-e1bde77105e2
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ff738c43095548ea6667deadf0eb80c4c6818ec3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47805485"
---
# <a name="create-and-update-database-tables"></a>データベース テーブルの作成と更新
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
テーブル デザイナーはビジュアル ツールであり、[データベース テーブル](../../relational-databases/tables/tables.md)の設計および視覚化を行うことができます。 SQL Server Management Studio (SSMS) テーブル デザイナーを使用して、テーブル、列、キー、インデックス、リレーションシップ、および制約を作成、編集、または削除します。  

  
## <a name="create-a-table"></a>テーブルの作成  
  
1. データベースで **[テーブル]** ノードを右クリックし、**[新規作成]** > **[テーブル]** を選択します。  
  
    ![新しいテーブル](../media/design-tables/new-table.png)
  
1. テーブルに[列](column-properties-visual-database-tools.md)を追加します。
  
    ![テーブルを設計する](../media/design-tables/new-table2.png)

1. デザイナーを閉じて、変更を保存します。
  
## <a name="update-a-table"></a>テーブルを更新する  
  
1. データベースの **[テーブル]** ノードの下にあるテーブルを右クリックし、**[デザイン]** を選択します。  
  
   ![テーブルを更新する](../media/design-tables/update-table.png)

1. 目的のテーブル設定を更新します。

   ![](../media/design-tables/update-table2.png)

1. デザイナーを閉じて、変更を保存します。

## <a name="see-also"></a>参照

[テーブル](../../relational-databases/tables/tables.md)  
[テーブルのプロパティ (Visual Database Tools)](../../ssms/visual-db-tools/table-properties-visual-database-tools.md)  
[列のプロパティ](column-properties-visual-database-tools.md)  
[テーブルへの列の追加](../../relational-databases/tables/add-columns-to-a-table-database-engine.md)  
[主キーと外部キー](../../relational-databases/tables/primary-and-foreign-key-constraints.md)  
[[インデックス]](../../relational-databases/indexes/indexes.md)  
[データ型 (Transact-SQL)](../../t-sql/data-types/data-types-transact-sql.md)  
[SQL Server Management Studio (SSMS) のダウンロード](../download-sql-server-management-studio-ssms.md)  
