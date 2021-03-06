---
title: '@@LANGID (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 09/18/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '@@LANGID'
- '@@LANGID_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- languages [SQL Server], current in use
- '@@LANGID function'
- current language in use
- ID for language in use
- local language IDs [SQL Server]
ms.assetid: 7a0fc089-2a48-4a81-9d78-2aaedb540d37
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: c7da7b6f0bec6df0e20dcd73354af615631b0534
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47739380"
---
# <a name="x40x40langid-transact-sql"></a>&#x40;&#x40;LANGID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  現在使用している言語のローカル言語識別子 (ID) を返します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
@@LANGID  
```  
  
## <a name="return-types"></a>戻り値の型  
 **smallint**  
  
## <a name="remarks"></a>Remarks  
 言語 ID 番号を含めて、言語の設定に関する情報を表示するには、パラメーターを指定しないで **sp_helplanguage** を実行します。  
  
## <a name="examples"></a>使用例  
 この例では、現在のセッションで使用する言語を `Italian` に設定し、`@@LANGID` を使用してイタリア語の ID を返します。  
  
```  
SET LANGUAGE 'Italian'  
SELECT @@LANGID AS 'Language ID'  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Changed language setting to Italiano.  
Language ID  
-----------  
6            
```  
  
## <a name="see-also"></a>参照  
 [構成関数 &#40;Transact-SQL&#41;](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [言語を設定する (&) #40 です。TRANSACT-SQL と #41 です。](../../t-sql/statements/set-language-transact-sql.md)   
 [sp_helplanguage (&) #40 です。TRANSACT-SQL と #41 です。](../../relational-databases/system-stored-procedures/sp-helplanguage-transact-sql.md)  
  
  
