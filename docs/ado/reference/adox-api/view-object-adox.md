---
title: オブジェクト (ADOX) の表示 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- View
helpviewer_keywords:
- View object [ADOX]
ms.assetid: 653421ce-7b94-43d0-9bc6-4900f8f2af45
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 61b3f81a23c3bb35921e0374eea44e58a31dcd4a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47696861"
---
# <a name="view-object-adox"></a>View オブジェクト (ADOX)
フィルター選択された一連のレコードまたは仮想テーブルを表します。 ADO と組み合わせて使用すると[コマンド](../../../ado/reference/ado-api/command-object-ado.md)オブジェクト、**ビュー**オブジェクトは、追加、削除、またはビューの変更のために使用できます。  
  
## <a name="remarks"></a>コメント  
 ビューは、他のデータベース テーブルまたはビューから作成された、仮想テーブルです。 **ビュー**オブジェクトでは、知っているか、プロバイダーの"CREATE VIEW"の構文を使用することがなく、ビューを作成できます。  
  
 プロパティを持つ、**ビュー**オブジェクトのことができます。  
  
-   ビューを識別、[名前](../../../ado/reference/adox-api/name-property-adox.md)プロパティ。  
  
-   ADO の指定**コマンド**追加、削除、またはビューを変更するために使用できるオブジェクト、[コマンド](../../../ado/reference/adox-api/command-property-adox.md)プロパティ。  
  
-   日付情報を返す、 [DateCreated](../../../ado/reference/adox-api/datecreated-property-adox.md)と[DateModified](../../../ado/reference/adox-api/datemodified-property-adox.md)プロパティ。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [View オブジェクトのプロパティ、メソッド、およびイベント](../../../ado/reference/adox-api/view-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>参照  
 [ビューとフィールド コレクションの例 (VB)](../../../ado/reference/adox-api/views-and-fields-collections-example-vb.md)   
 [Views Append メソッドの例 (VB)](../../../ado/reference/adox-api/views-append-method-example-vb.md)   
 [Views コレクションおよび CommandText プロパティの例 (VB)](../../../ado/reference/adox-api/views-collection-commandtext-property-example-vb.md)   
 [Views Delete メソッドの例 (VB)](../../../ado/reference/adox-api/views-delete-method-example-vb.md)   
 [Views コレクション (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)
