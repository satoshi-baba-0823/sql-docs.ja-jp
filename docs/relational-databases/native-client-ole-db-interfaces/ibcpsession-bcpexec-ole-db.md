---
title: :Bcpexec (OLE DB) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apiname:
- IBCPSession::BCPExec (OLE DB)
apitype: COM
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 52f370a7dc7e830a7a5963dca745e98bb7d84cd9
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47820457"
---
# <a name="ibcpsessionbcpexec-ole-db"></a>IBCPSession::BCPExec (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  一括コピー操作を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
  
HRESULT BCPExec(   
      DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a>コメント  
 **BCPExec** メソッドでは、[IBCPSession::BCPInit](../../relational-databases/native-client-ole-db-interfaces/ibcpsession-bcpinit-ole-db.md) メソッドで使用されている *eDirection* パラメーターの値に従って、データをユーザー ファイルからデータベース テーブルに、またはデータベース テーブルからユーザー ファイルにコピーします。  
  
 **BCPExec** を呼び出す前に、有効なユーザー ファイル名を指定して **BCPInit** メソッドを呼び出します。 この操作を行わないと、エラーが発生します。 唯一の例外は、一括コピーの出力操作にクエリを使用する場合です。 この場合は、**BCPInit** メソッドでテーブル名に NULL を指定してから、BCP_OPTION_HINTS オプションを使用してクエリを指定します。  
  
 **BCPExec** メソッドは、短時間に優れた結果を得られる唯一の一括コピー メソッドです。 そのため、このメソッドは非同期モードをサポートする唯一の一括コピー メソッドでもあります。 非同期モードを使用するには、プロバイダー固有のセッション プロパティ SSPROP_ASYNCH_BULKCOPY を VARIANT_TRUE に設定してから、**BCPExec** メソッドを呼び出します。 このプロパティは、DBPROPSET_SQLSERVERSESSION プロパティ セットに含まれています。 コピーの完了を確認するには、同じパラメーターを指定して **BCPExec** メソッドを呼び出します。 一括コピーがまだ完了していない場合は、**BCPExec** メソッドから DB_S_ASYNCHRONOUS が返されます。 また、*pRowsCopied* 引数には、サーバーとの間で送受信される行数の進行状況を表す数も返されます。 サーバーに送信された行は、バッチの終わりに到達するまではコミットされません。  
  
## <a name="arguments"></a>引数  
 *pRowsCopied*[out]  
 DWORD へのポインターです。 **BCPExec** メソッドは、正常にコピーされた行数を使用して、DWORD を設定します。 *pRowsCopied* 引数に NULL を設定すると、**BCPExec** メソッドはこの引数を無視します。  
  
## <a name="return-code-values"></a>リターン コードの値  
 S_OK  
 メソッドが成功しました。  
  
 E_FAIL  
 プロバイダー固有のエラーが発生しました。詳細を確認するには、[ISQLServerErrorInfo](http://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1) インターフェイスを使用してください。  
  
 E_UNEXPECTED  
 メソッドの呼び出しが予期されませんでした。 たとえば、このメソッドを呼び出す前に、**BCPInit** メソッドが呼び出されなかった場合などです。 また、操作が BCP_OPTION_ABORT オプションを使用して中断され、その後、**BCPExec** メソッドが呼び出された場合にも発生します。  
  
 E_OUTOFMEMORY  
 メモリ不足エラーです。  
  
 DB_S_ENDOFROWSET  
 一括コピー操作が終了し、すべてのデータ転送が完了しました。  
  
 DB_S_ASYNCHRONOUS  
 行の現在のバッチがコピーされました。 次のバッチを転送するには、**BCPExec** メソッドを再度呼び出します。  
  
 DB_S_ERRORSOCCURRED  
 一括コピー操作中にエラーが発生しました。そのため、一部の行がコピーされなかった可能性があります。 エラー数は、許容されるエラーの最大数には達していません。  
  
## <a name="see-also"></a>参照  
 [IBCPSession &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/ibcpsession-ole-db.md)   
 [一括コピー操作の実行](../../relational-databases/native-client/features/performing-bulk-copy-operations.md)  
  
  
