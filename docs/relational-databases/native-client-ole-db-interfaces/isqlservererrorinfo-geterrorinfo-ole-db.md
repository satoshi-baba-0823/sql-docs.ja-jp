---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB)。マイクロソフトのドキュメント
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apiname:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
apitype: COM
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3c140e3891b5d1f5e73600a3cb623e5a0e8ce463
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606634"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a>ISQLServerErrorInfo::GetErrorInfo (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  ポインターを返します、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ネイティブ クライアント OLE DB プロバイダー SSERRORINFO 構造を含む、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]エラーの詳細です。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ネイティブ クライアント OLE DB プロバイダーを定義します**ISQLServerErrorInfo**インタ フェースのエラーです。 このインターフェイスは、重大度や状態など、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エラーの詳細情報を返します。  

  
## <a name="syntax"></a>構文  
  
```  
  
HRESULT GetErrorInfo(  
   SSERRORINFO**ppSSErrorInfo,  
   OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a>引数  
 *ppSSErrorInfo*[out]  
 SSERRORINFO 構造体へのポインター。 メソッドが失敗するか、エラーに関連する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 情報がない場合、プロバイダーはメモリの割り当てを行わず、出力時に *ppSSErrorInfo* 引数に NULL ポインターを設定します。  
  
 *ppErrorStrings*[out]  
 Unicode 文字列ポインターへのポインター。 メソッドが失敗するか、エラーに関連する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 情報がない場合、プロバイダーはメモリの割り当てを行わず、出力時に *ppErrorStrings* 引数に NULL ポインターを設定します。 **IMalloc::Free** メソッドを使用して *ppErrorStrings* 引数を解放すると、メモリがブロック単位で割り当てられているので、結果の SSERRORINFO 構造体の 3 つの各文字列メンバーが解放されます。  
  
## <a name="return-code-values"></a>リターン コードの値  
 S_OK  
 メソッドが成功しました。  
  
 E_INVALIDARG  
 いずれか、 *ppSSErrorInfo*または*割り当てません*された引数が NULL です。  
  
 E_OUTOFMEMORY  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ネイティブ クライアント OLE DB プロバイダーは要求を完了するための十分なメモリを割り当てられませんでした。  
  
## <a name="remarks"></a>コメント  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ネイティブ クライアント OLE DB プロバイダーは、コンシューマーによって渡されたポインターを通じて返される SSERRORINFO と OLECHAR の文字列にメモリを割り当てます。 コンシューマーはエラー データにアクセスする必要がなくなった時点で、**IMalloc::Free** メソッドを使用してこのメモリの割り当てを解除する必要があります。  
  
 SSERRORINFO 構造体は、次のように定義されています。  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|Member|説明|  
|------------|-----------------|  
|*pwszMessage*|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のエラー メッセージ。 このメッセージは、**IErrorInfo::GetDescription** メソッドにより返されます。|  
|*pwszServer*|エラーが発生した [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスの名前。|  
|*pwszProcedure*|エラーがストアド プロシージャ内で発生している場合は、エラーが発生したストアド プロシージャの名前です。それ以外の場合は、空文字列になります。|  
|*lNative*|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のエラー番号。 このエラー番号は、**ISQLErrorInfo::GetSQLInfo** メソッドの *plNativeError* パラメーターに返されるものと同じになります。|  
|*bState*|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エラーの状態。|  
|*bClass*|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エラーの重大度。|  
|*wLineNumber*|該当する場合は、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ストアド プロシージャのエラー メッセージを生成した行です。 プロシージャが関係していない場合は、既定値 1 が使用されます。|  
  
 構造体内のポインターは、*ppErrorStrings* 引数に返される文字列内のアドレスを指します。  
  
## <a name="see-also"></a>参照  
 [ISQLServerErrorInfo &#40;OLE DB&#41;](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1)   
 [RAISERROR &#40;Transact-SQL&#41;](../../t-sql/language-elements/raiserror-transact-sql.md)  
  
  
