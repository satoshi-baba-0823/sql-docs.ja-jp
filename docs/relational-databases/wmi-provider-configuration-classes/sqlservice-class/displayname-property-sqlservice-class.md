---
title: DisplayName プロパティ (SqlService クラス) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: reference
apiname:
- DisplayName Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: cc02c91985aa96c8dd1d01d40fd77a328de84802
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47699070"
---
# <a name="displayname-property-sqlservice-class"></a>DisplayName プロパティ (SqlService クラス)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  サービスの表示名を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object.DisplayName [= value]  
```  
  
## <a name="parts"></a>要素  
 *object*  
 サービスを表す [SqlService クラス](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) オブジェクト。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 サービスの表示名を指定する文字列値。  
  
## <a name="remarks"></a>コメント  
 この文字列の長さは最大 256 文字です。 名前は [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 構成マネージャーで大文字と小文字が区別されます。 ただし、表示名の比較時には、常に大文字と小文字は区別されません。  
  
## <a name="example"></a>例  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a>参照  
 [開始とサービスの停止](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
