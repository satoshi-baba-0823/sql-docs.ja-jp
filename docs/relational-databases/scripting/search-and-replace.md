---
title: 検索と置換 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.technology: scripting
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 95820c07f8ee7d2d74f9720e1554cb0dd934c778
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47840540"
---
# <a name="search-and-replace"></a>検索と置換
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
  テキストの検索と置換にはいくつかの方法があります。 **[編集]** メニューの **[検索と置換]** には、 **[クイック検索]**、 **[クイック置換]**、 **[フォルダーを指定して検索]**、 **[フォルダーを指定して置換]** という 4 つのオプションが用意されています。 各オプションを選択すると、各バージョンの **[検索と置換]** ダイアログ ボックスが表示されます。 ダイアログ ボックスを使用しないで、インクリメンタル検索キーボード ショートカット キーによって検索することも可能です。 これらの方法によって、検索と置換の範囲を設定することや、検索一致項目や置換項目を確認する方法を選択することができます。  
  
 テキストの検索と置換に関する注意点は次のとおりです。  
  
-   **[検索と置換]** ダイアログ ボックスで設定したオプションは、すべての検索操作に影響します。 具体的には、 **[大文字と小文字を区別する]**、 **[単語単位]**、 **[上へ検索]**、 **[非表示のテキストを検索]**、 **[ワイルドカード]**、 **[正規表現]**、 **[検索対象: すべての開かれているドキュメント]**、 **[検索対象: 現在のプロジェクト]** の各オプションです。 すべてのバージョンの **[検索と置換]** ダイアログ ボックスですべてのオプションを使用できるわけではありません。  
  
-   **[元に戻す]** を使用できるのは、置換操作後に開いたままにしておいたドキュメントに限られます。  
  
-   複数のファイルを対象にした **[すべて置換]** 操作に対して **[元に戻す]** を使用すると、すべての対象ファイルに対して一括処理が行われます。 つまり、一部のファイルの変更を元に戻し、他のファイルの変更をそのまま残す、ということはできません。  
  
 一般に、グラフィカル ビューを持つ項目の検索はできません。  
  
## <a name="see-also"></a>参照  
 [アクティブ ドキュメントのインクリメンタル検索](../../relational-databases/scripting/search-an-active-document-incrementally.md)   
 [ドキュメントの対話形式の検索](../../relational-databases/scripting/search-documents-interactively.md)   
 [結果一覧を使用してドキュメントを検索する方法](../../relational-databases/scripting/search-documents-using-results-lists.md)   
 [ワイルドカードを使用したテキスト検索](../../relational-databases/scripting/search-text-with-wildcards.md)   
 [正規表現によるテキストの検索](../../relational-databases/scripting/search-text-with-regular-expressions.md)  
  
  
