---
title: XQuery プロローグ |Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- XQuery, prolog
- prolog
- namespaces [XQuery]
- default namespace declarations
ms.assetid: 03924684-c5fd-44dc-8d73-c6ab90f5e069
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: d496a846c49c002e77f0f8bc3bde13fad24755a9
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47854760"
---
# <a name="modules-and-prologs---xquery-prolog"></a>モジュールとプロローグ - XQuery プロローグ
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  XQuery クエリは、プロローグ (序文) と本文で構成されます。 XQuery プロローグは、クエリ処理に必要な環境を作成する一連の宣言および定義です。 SQL Server では、XQuery プロローグに名前空間の宣言を含めることができます。 XQuery 本文は、目的のクエリ結果を指定する一連の式で構成されます。  
  
 Instructions 列に対して、次の XQuery を指定するなど、 **xml**製造手順 XML として格納する型。 このクエリでは、ワーク センターの場所 `10` に関する製造手順が取得されます。 `query()`のメソッド、 **xml** XQuery を指定するデータ型を使用します。  
  
```  
SELECT Instructions.query('declare namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";           
    /AWMI:root/AWMI:Location[@LocationID=10]  
') AS Result   
FROM  Production.ProductModel  
WHERE ProductModelID=7  
```  
  
 上のクエリに関して、次の点に注意してください。  
  
-   XQuery プロローグには、名前空間プレフィックス (AWMI) 宣言が含まれています`(namespace AWMI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";`します。  
  
-   `declare namespace` キーワードは、クエリ本文で後から使用される名前空間プレフィックスを定義します。  
  
-   `/AWMI:root/AWMI:Location[@LocationID="10"]` がクエリの本文です。  
  
## <a name="namespace-declarations"></a>名前空間の宣言  
 次のクエリで示すように、名前空間の宣言でプレフィックスを定義し、名前空間 URI に関連付けます。 クエリで`CatalogDescription`は、 **xml**型の列。  
  
 この列に対する XQuery の指定では、クエリのプロローグで `declare namespace` 宣言を指定して、製品説明のプレフィックス `PD` を名前空間 URI に関連付けています。 クエリ本文では、名前空間 URI の代わりにこのプレフィックスを使用します。 結果の XML のノードは、名前空間 URI に関連付けられた名前空間内に含まれます。  
  
```  
SELECT CatalogDescription.query('  
declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
         /PD:ProductDescription/PD:Summary   
    ') as Result  
FROM Production.ProductModel  
where ProductModelID=19  
```  
  
 クエリの読みやすさを向上させるのを使用して、プレフィックスとクエリのプロローグで名前空間のバインドを宣言する代わりに WITH XMLNAMESPACES を使用して名前空間を宣言できます`declare namespace`します。  
  
```  
WITH XMLNAMESPACES ('http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS PD)  
  
SELECT CatalogDescription.query('  
         /PD:ProductDescription/PD:Summary   
    ') as Result  
FROM Production.ProductModel  
where ProductModelID=19  
```  
  
 詳細についてを参照してください、 [with XMLNAMESPACES を使用したクエリへの名前空間の追加](../relational-databases/xml/add-namespaces-to-queries-with-with-xmlnamespaces.md)します。  
  
### <a name="default-namespace-declaration"></a>既定の名前空間の宣言  
 使用して、名前空間プレフィックスを宣言する代わりに、`declare namespace`使用することができます、宣言、`declare default element namespace`要素名の既定の名前空間のバインドを宣言します。 この場合、プレフィックスは指定しません。  
  
 次の例では、クエリ本文のパス式で名前空間プレフィックスを指定していません。 既定では、すべての要素名はプロローグで指定された既定の名前空間に所属します。  
  
```  
SELECT CatalogDescription.query('  
     declare default element namespace  "http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
        /ProductDescription/Summary   
    ') as Result  
FROM  Production.ProductModel  
WHERE ProductModelID=19   
```  
  
 既定の名前空間は、WITH XMLNAMESPACES を使用して宣言できます。  
  
```  
WITH XMLNAMESPACES (DEFAULT 'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription')  
SELECT CatalogDescription.query('  
        /ProductDescription/Summary   
    ') as Result  
FROM  Production.ProductModel  
WHERE ProductModelID=19   
```  
  
## <a name="see-also"></a>参照  
 [WITH XMLNAMESPACES を使用したクエリへの名前空間の追加](../relational-databases/xml/add-namespaces-to-queries-with-with-xmlnamespaces.md)  
  
  
