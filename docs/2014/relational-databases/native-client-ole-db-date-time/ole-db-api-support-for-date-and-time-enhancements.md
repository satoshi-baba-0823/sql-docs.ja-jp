---
title: OLE DB API による機能強化された日付と時刻のサポート | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 536860699bcdbed6753724bfad7832bc9fa7705e
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48144010"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a>OLE DB API による機能強化された日付と時刻のサポート
  機能強化された日付や時刻をサポートする OLE DB API を次に示します。  
  
|機能|説明|  
|--------------|-----------------|  
|IAccessor::CreateAccessor|アプリケーションで `datetime`、`datetime2`、および `smalldatetime` の各値を区別できるように、DBBINDING 構造体にフラグが用意されています。 詳細については、次を参照してください。[パラメーターと行セットのメタデータ](metadata-parameter-and-rowset.md)します。|  
|IBCPSession::BCPColFmt|詳細については、次を参照してください。[強化された日付と時刻型向けの一括コピーの変更&#40;OLE DB および ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)します。|  
|ICommandWithParameters::GetParameterInfo|詳細については、次を参照してください。[パラメーターと行セットのメタデータ](metadata-parameter-and-rowset.md)します。|  
|ICommandWithParameters::SetParameterinfo|詳細については、次を参照してください。[パラメーターと行セットのメタデータ](metadata-parameter-and-rowset.md)します。|  
|IColumnsRowset::GetColumnsRowset|詳細については、次を参照してください。[パラメーターと行セットのメタデータ](metadata-parameter-and-rowset.md)します。|  
|IColumnsInfo::GetColumnInfo|詳細については、次を参照してください。[パラメーターと行セットのメタデータ](metadata-parameter-and-rowset.md)します。|  
|IDBSchemaRowset::GetRowset|影響を受けるスキーマ行セットの詳細については、次を参照してください。[日付と時刻、およびスキーマ行セット](../native-client-ole-db-rowsets/rowsets.md)します。|  
|IRowsetFastLoad|このインターフェイスは新しい日付と時刻の型をサポートしますが、インターフェイスに変更はありません。|  
|ITableDefinition::CreateTable|詳細については、次を参照してください。 [OLE DB の日付と時刻の強化に対するデータ型のサポート](data-type-support-for-ole-db-date-and-time-improvements.md)します。|  
  
## <a name="see-also"></a>参照  
 [日付と時刻の強化機能 &#40;OLE DB&#41;](date-and-time-improvements-ole-db.md)  
  
  
