---
title: getObject (int, java.util.Map) メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.getObject (int, java.util.Map)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 164532be-7ed6-40fa-a273-dece4c8d72c4
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e86cadfbb230255fc3512768ef0886409267923d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47667502"
---
# <a name="getobject-method-int-javautilmap"></a>getObject (int, java.util.Map) メソッド
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  パラメーターに渡されたインデックスと Map オブジェクトを使用して、指定されたパラメーターの値が Java プログラミング言語のオブジェクトとして取得されます。  
  
> [!NOTE]  
>  このメソッドは、現在 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] ではサポートされていません。 このメソッドを使用すると、常に既定のマッピングが返されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
public java.lang.Object getObject(int index,  
                                  java.util.Map map)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *index*  
  
 パラメーターのインデックスを示す **int** です。  
  
 *map*  
  
 マップ オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 **Object** 値。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 この setObject メソッドは、java.sql.CallableStatement インターフェイスの setObject メソッドで指定されています。  
  
 このメソッドは、指定された列の値を Java オブジェクトとして返します。 この Java オブジェクトの型は、JDBC 仕様に指定されている組み込み型のマッピングに基づく、列の SQL 型に対応する既定の Java オブジェクト型です。 値が SQL NULL の場合、ドライバーは Java の null を返します。  
  
 このメソッドは、データベース固有の抽象データ型を読み取る場合にも使用できます。 JDBC 2.0 API では、SQL のユーザー定義型のデータを具体化するよう、getObject メソッドの動作が拡張されています。 列に構造化された値または個別の値が含まれている場合、このメソッドの動作は `getObject(columnIndex, this.getStatement().getConnection().getTypeMap())` を呼び出した場合と同様です。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] JDBC Driver 3.0 以降:  
  
-   date 型の値は java.sql.Date オブジェクトとして返されます。  
  
-   time 型の値は java.sql.Time オブジェクトとして返されます。  
  
-   datetime2 型の値は java.sql.Timestamp オブジェクトとして返されます。  
  
-   datetimeoffset 型の値は microsoft.sql.DateTimeOffset オブジェクトとして返されます。  
  
## <a name="see-also"></a>参照  
 [getObject メソッド &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getobject-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement のメンバー](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement クラス](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
