---
title: テーブルの計算列の指定 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 3f8cb3a1a2ae171c386b9f8a0b9c18e06b3cc723
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47627860"
---
# <a name="specify-computed-columns-in-a-table"></a>テーブルの計算列の指定
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  計算列は、PERSISTED とマークされていない限り、テーブルに物理的に保存されない仮想列です。 計算列の式は、他の列のデータを使用して値を計算し、それを自身の列に格納します。 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] では、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] または [!INCLUDE[tsql](../../includes/tsql-md.md)]を使用して計算列に式を指定できます。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Limitations)  
  
     [Security](#Security)  
  
-   **計算列を指定する方法:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 作業を開始する準備  
  
###  <a name="Limitations"></a> 制限事項と制約事項  
  
-   計算列は、DEFAULT 制約定義または FOREIGN KEY 制約定義として使用したり、NOT NULL 制約定義と共に使用したりすることはできません。 ただし、計算列の値が決定的な式によって定義され、その結果のデータ型がインデックス列で可能な場合、計算列は、インデックスのキー列として、または任意の PRIMARY KEY 制約または UNIQUE 制約の一部として使用できます。 たとえば、テーブルに整数型の列 a と b がある場合、計算列 a + b にはインデックスを作成できますが、計算列 a+DATEPART(dd, GETDATE()) にインデックスを作成することはできません。これは、この計算列の値が次以降の呼び出しで変更される可能性があるためです。  
  
-   計算列を INSERT ステートメントまたは UPDATE ステートメントの対象にすることはできません。  
  
###  <a name="Security"></a> セキュリティ  
  
####  <a name="Permissions"></a> Permissions  
 テーブルに対する ALTER 権限が必要です。  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
###  <a name="NewColumn"></a> 新しい計算列を追加するには  
  
1.  **オブジェクト エクスプローラー**で、新しい計算列を追加するテーブルを展開します。 **[列]** を右クリックして **[新しい列]** をクリックします。  
  
2.  列名を入力し、既定のデータ型 (**nchar**(10)) をそのまま使用します。 [!INCLUDE[ssDE](../../includes/ssde-md.md)] により、計算列のデータ型は、数式で指定された式のデータ型のうち優先順位が高い方になります。 たとえば、式で **money** 型の列と **int**型の列を参照する場合、 **money** 型の方が優先順位が高いため、計算列はそのデータ型になります。 詳細については、「[データ型の優先順位 &#40;Transact-SQL&#41;](../../t-sql/data-types/data-type-precedence-transact-sql.md)」を参照してください。  
  
3.  **[列のプロパティ]** タブの **[計算列の指定]** プロパティを展開します。  
  
4.  **[(数式)]** 子プロパティで、列の式を右側のグリッド セルに入力します。 たとえば、 `SalesTotal` 列に `SubTotal+TaxAmt+Freight`という数式を入力した場合、テーブル内の各行のこれらの列の値が加算されます。  
  
    > [!IMPORTANT]  
    >  数式でデータ型が異なる 2 つの式を結合すると、データ型の優先順位の規則によって、優先順位の低いデータ型を優先順位の高いデータ型に変換することが指定されます。 暗黙的な変換がサポートされていない場合は、「`Error validating the formula for column column_name.`」というエラーが返されます。 データ型の競合を解決するには、CAST 関数または CONVERT 関数を使用します。 たとえば、 **nvarchar** 型の列を **int**型の列と結合する場合は、この数式 **のように、整数型を** nvarchar `('Prod'+CONVERT(nvarchar(23),ProductID))`に変換する必要があります。 詳細については、「[CAST および CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)」を参照してください。  
  
5.  **[Is Persisted]** 子プロパティのドロップダウンの **[はい]** または **[いいえ]** をクリックし、データを永続化するかどうかを指定します。  
  
6.  **ファイル** メニューの **table name**_の保存_をクリックします。  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a>既存の列に計算列の定義を追加するには  
  
1.  **オブジェクト エクスプローラー**で、変更する列が含まれているテーブルを右クリックし、 **[列]** フォルダーを展開します。  
  
2.  計算列の数式を指定する列を右クリックし、 **[削除]** をクリックします。 **[OK]** をクリックします。  
  
3.  前の手順に従って、新しい列を追加し、計算列の数式を指定して、新しい計算列を追加します。  
  
##  <a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a>テーブルの作成時に計算列を追加するには  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]に接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。 この例では、 `QtyAvailable` 列の値と `UnitPrice` 列の値を乗算する計算列を含むテーブルを作成します。  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a>既存のテーブルに新しい計算列を追加するには  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]に接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。 次の例では、前の例で作成したテーブルに新しい列を追加します。  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a>既存の列を計算列に変更するには  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]に接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  既存の列を計算列に変更するには、計算列を削除してから再作成する必要があります。 次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。 次の例では、前の例で追加した列を変更します。  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     詳細については、「[ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)」を参照してください。  
  
###  <a name="TsqlExample"></a>  
