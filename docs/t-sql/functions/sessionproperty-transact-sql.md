---
title: SESSIONPROPERTY (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- SESSIONPROPERTY
- SESSIONPROPERTY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- SET statement, SESSIONPROPERTY function
- SESSIONPROPERTY function
- sessions [SQL Server], SET options settings
ms.assetid: 1f3730b4-1495-4d3a-af43-e57952812df9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 36fb5844c7255aff7b8527ff5cc462ec5a573977
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47642910"
---
# <a name="sessionproperty-transact-sql"></a>SESSIONPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  セッションの SET オプション設定を返します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
SESSIONPROPERTY (option)  
```  
  
## <a name="arguments"></a>引数  
 *オプション*  
 このセッションの現在のオプション設定値です。 *オプション* 値は次のいずれかを指定することができます。  
  
|オプション|[説明]|  
|------------|-----------------|  
|ANSI_NULLS|= (等号) と <> (不等号) を NULL 値に対して使用した場合の ISO 動作を指定します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|ANSI_PADDING|文字データとバイナリ データにおいて、定義されている列のサイズより短い値がどのように格納されるか、および後続の空白が列にどのように格納されるかを制御します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|ANSI_WARNINGS|0 除算や算術オーバーフローなど、特定の状態に対するエラー メッセージまたは警告の出力について、ISO 標準の動作の適用を指定します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|ARITHABORT|クエリ実行中にオーバーフローまたは 0 除算エラーが発生した場合、クエリを終了するかどうかを指定します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|CONCAT_NULL_YIELDS_ NULL|連結の結果が NULL として取り扱われるのか、空文字列として取り扱われるのかを制御します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|NUMERIC_ROUNDABORT|式の丸め処理で精度が低下するときに、エラー メッセージおよび警告を出力するかどうかを指定します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|QUOTED_IDENTIFIER|識別子とリテラル文字列を区切る引用符の使用について、ISO 規則に従うかどうかを指定します。<br /><br /> 1 = ON <br /><br /> 0 = OFF|  
|\<その他の文字列>|NULL = 無効な入力|  
  
## <a name="return-types"></a>戻り値の型  
 **sql_variant**  
  
## <a name="remarks"></a>Remarks  
 SET オプションは、サーバー レベル、データベース レベル、およびユーザー指定のオプションを組み合わせることによって表されます。  
  
## <a name="examples"></a>使用例  
 次の例では、`CONCAT_NULL_YIELDS_NULL` オプションの設定を返します。  
  
```  
SELECT   SESSIONPROPERTY ('CONCAT_NULL_YIELDS_NULL')  
```  
  
## <a name="see-also"></a>参照  
 [sql_variant &#40;Transact-SQL&#41;](../../t-sql/data-types/sql-variant-transact-sql.md)   
 [SET ANSI_NULLS &#40;Transact-SQL&#41;](../../t-sql/statements/set-ansi-nulls-transact-sql.md)   
 [SET ANSI_PADDING &#40;Transact-SQL&#41;](../../t-sql/statements/set-ansi-padding-transact-sql.md)   
 [SET ANSI_WARNINGS &#40;Transact-SQL&#41;](../../t-sql/statements/set-ansi-warnings-transact-sql.md)   
 [SET ARITHABORT &#40;Transact-SQL&#41;](../../t-sql/statements/set-arithabort-transact-sql.md)   
 [SET CONCAT_NULL_YIELDS_NULL &#40;Transact-SQL&#41;](../../t-sql/statements/set-concat-null-yields-null-transact-sql.md)   
 [SET NUMERIC_ROUNDABORT &#40;Transact-SQL&#41;](../../t-sql/statements/set-numeric-roundabort-transact-sql.md)   
 [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](../../t-sql/statements/set-quoted-identifier-transact-sql.md)  
  
  
