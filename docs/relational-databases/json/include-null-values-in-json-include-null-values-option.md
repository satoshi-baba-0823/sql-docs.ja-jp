---
title: JSON に Null 値を含める - INCLUDE_NULL_VALUES オプション | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2016
ms.prod: sql
ms.reviewer: douglasl
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- INCLUDE_NULL_VALUES (FOR JSON)
ms.assetid: 06873768-3778-4ed8-a1db-61758726bda0
author: jovanpop-msft
ms.author: jovanpop
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 10b54bfd40fa841381b6e246881ba0c64904c45f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47723300"
---
# <a name="include-null-values-in-json---includenullvalues-option"></a>JSON に Null 値を含める - INCLUDE_NULL_VALUES オプション
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  **FOR JSON** 句の JSON の出力に null 値を含めるには、 **INCLUDE_NULL_VALUES** オプションを指定します。  
  
 **INCLUDE_NULL_VALUES** オプションを指定しない場合、クエリ結果で値が null のプロパティは JSON の出力に含まれません。  
  
## <a name="examples"></a>使用例  
 **INCLUDE_NULL_VALUES** オプションを指定した場合と指定しなかった場合の **FOR JSON** 句の出力例を以下に示します。  
  
|**INCLUDE_NULL_VALUES** オプションを指定しなかった場合|**INCLUDE_NULL_VALUES** オプションを指定した場合|  
|--------------------------------------------------|-----------------------------------------------|  
|`{    "name": "John",    "surname": "Doe" }`|`{    "name": "John",    "surname": "Doe",    "age": null,    "phone": null }`|  
  
 次に、 **FOR JSON** 句で **INCLUDE_NULL_VALUES** オプションを指定した別の例を示します。  
  
 **クエリ**  
  
```sql  
SELECT name, surname  
FROM emp  
FOR JSON AUTO, INCLUDE_NULL_VALUES    
```  
  
 **結果**  
  
```json  
[{
    "name": "John",
    "surname": null
}, {
    "name": "Jane",
    "surname": "Doe"
}] 
```  

## <a name="learn-more-about-json-in-sql-server-and-azure-sql-database"></a>SQL Server と Azure SQL Database の JSON の詳細情報  
  
### <a name="microsoft-blog-posts"></a>マイクロソフトのブログ記事  
  
具体的なソリューション、ユース ケース、推奨事項については、SQL Server および Azure SQL Database に組み込まれている JSON のサポートに関する[ブログ投稿](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/)を参照してください。  

### <a name="microsoft-videos"></a>Microsoft ビデオ

SQL Server と Azure SQL Database に組み込まれている JSON のサポートの視覚的な紹介は、次のビデオをご覧ください。

-   [SQL Server 2016 と JSON のサポート](https://channel9.msdn.com/Shows/Data-Exposed/SQL-Server-2016-and-JSON-Support)

-   [SQL Server 2016 と Azure SQL Database での JSON の使用](https://channel9.msdn.com/Shows/Data-Exposed/Using-JSON-in-SQL-Server-2016-and-Azure-SQL-Database)

-   [NoSQL とリレーショナル環境間の架け橋としての JSON](https://channel9.msdn.com/events/DataDriven/SQLServer2016/JSON-as-a-bridge-betwen-NoSQL-and-relational-worlds)

## <a name="see-also"></a>参照  
 [FOR 句 &#40;Transact-SQL&#41;](../../t-sql/queries/select-for-clause-transact-sql.md)  
  
  
