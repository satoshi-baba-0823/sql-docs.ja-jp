---
title: 新しいエイリアス (別名 タブ) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
manager: craigg
ms.openlocfilehash: 69324ab25ba5efd293e445aa7ae4f0ff768b1c8b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47698280"
---
# <a name="new-alias-alias-tab"></a>[別名 - 新規] ダイアログ ボックス ([別名] タブ)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  別名は、接続のために使用できる代替名です。 別名は、接続文字列の必須要素をカプセル化したものであり、ユーザーが選択した名前でそれらの要素を公開できます。 **[別名 - 新規]** ダイアログ ボックスの **[別名]** ページでは、別名の接続文字列の各要素を指定できます。 既存の別名の接続文字列を変更する場合は、「[[&#60;Alias&#62; のプロパティ] ダイアログ ボックス ([別名] タブ)](../../tools/configuration-manager/alias-properties-alias-tab.md)」を参照してください。  
  
 **[プロパティ]** グリッドのすべての値を設定する必要はありません。 有効な組み合わせは、選択したプロトコルによって異なります。 有効な組み合わせの例については、最後に示してあるトピックを参照してください。  
  
 **[別名]**  
 この接続を参照するために使用する名前 (別名) です。  
  
 **[パイプ名]** / **[ポート番号]**  
 接続文字列の追加要素です。 このボックスの名前は、選択したプロトコルによって異なります。  
  
 **[プロトコル]**  
 接続に使用するプロトコルです。  
  
 **[サーバー]**  
 接続先の [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスの名前です。  
  
## <a name="when-to-use-an-alias"></a>別名を使用する状況  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] は既定で、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のローカル インスタンスに接続するときには **共有メモリ** プロトコルを使用し、別のコンピューター上の [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに接続するときには **TCP/IP** または **名前付きパイプ**を使用します。 TCP/IP または名前付きパイプを使用するときにカスタム接続文字列を指定する場合や、接続のためにサーバー名以外の名前を使用する場合には、別名を作成してください。  
  
### <a name="examples"></a>使用例  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] が既定の TCP/IP ポート 1433 で受信を待機しない場合に、別のポート番号を設定した接続文字列を指定します。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] が既定の名前付きパイプで受信を待機しない場合に、別のパイプ名を設定した接続文字列を指定します。  
  
-   `ACCT`という名前のサーバー上のデータベースに接続するアプリケーションがありますが、そのデータベースは、 `ACCT` という名前のサーバー上の `CENTRAL`という名前のインスタンスとして統合されています。 そのアプリケーションは、簡単に変更できません。 この場合は、 `ACCT`という別名を作成し、接続文字列で `CENTRAL\ACCT`を参照します。  
  
## <a name="creating-a-valid-connection-string"></a>有効な接続文字列の作成  
 別名のプロパティの有効な組み合わせに関する説明と例については、以下のトピックを参照してください。  
  
-   [共有メモリ プロトコルを使用した有効な接続文字列の作成](../../tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [TCP/IP を使用した有効な接続文字列の作成](../../tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [名前付きパイプを使用した有効な接続文字列の作成](http://msdn.microsoft.com/library/90930ff2-143b-4651-8ae3-297103600e4f)  
  
  
