---
title: Showplan XML For Query Compile イベント クラス | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML For Query Compile event class
ms.assetid: 48919fcb-3a22-43ca-a63c-b210cf2c32d5
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 770929b0838fabaf6a4584c80482a5169befe823
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47712522"
---
# <a name="showplan-xml-for-query-compile-event-class"></a>Showplan XML For Query Compile イベント クラス
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Showplan XML For Query Compile イベント クラスは、 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] によって SQL ステートメントがコンパイルされたときに発生します。 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]で Showplan 操作を識別するには、このイベント クラスを含めます。  
  
 Showplan XML For Query Compile イベント クラスでは完全なコンパイル時のデータが表示されるので、このイベント クラスを含んでいるトレースによって大きなパフォーマンス上のオーバーヘッドが発生する可能性があります。 これを最小限に抑えるには、特定の問題を短い期間監視するトレース以外に、このイベント クラスを使用しないようにします。  
  
 Showplan XML ドキュメントには、スキーマが関連付けられています。 このスキーマは、 [Microsoft Web サイト](http://go.microsoft.com/fwlink/?LinkId=41740)で提供されています。また、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインストールの一部として提供されています。  
  
## <a name="showplan-xml-for-query-compile-event-class-data-columns"></a>Showplan XML For Query Compile イベント クラスのデータ列  
  
|データ列名|データ型|[説明]|列 ID|フィルターの適用|  
|----------------------|---------------|-----------------|---------------|----------------|  
|ApplicationName|**nvarchar**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のインスタンスへの接続を作成したクライアント アプリケーションの名前。 この列には、プログラムの表示名ではなく、アプリケーションによって渡された値が格納されます。|10|[ユーザー アカウント制御]|  
|BinaryData|**image**|クエリのコストの推定値。|2|いいえ|  
|ClientProcessID|**int**|クライアント アプリケーションが実行されているプロセスに対し、ホスト コンピューターが割り当てた ID。 クライアントでクライアント プロセス ID が指定されると、このデータ列が作成されます。|9|[ユーザー アカウント制御]|  
|DatabaseID|**int**|USE *database* ステートメントで指定されたデータベースの ID、または特定のインスタンスについて USE *database*ステートメントが実行されていない場合は既定のデータベースの ID となります。 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] では、ServerName データ列がトレースにキャプチャされ、そのサーバーが利用可能な場合、データベースの名前が表示されます。 データベースに対応する値は、DB_ID 関数を使用して特定します。|3|[ユーザー アカウント制御]|  
|DatabaseName|**nvarchar**|ユーザーのステートメントが実行されているデータベースの名前。|35|[ユーザー アカウント制御]|  
|Event Class|**int**|イベントの種類 = 168。|27|いいえ|  
|EventSequence|**int**|要求内の特定のイベントのシーケンス。|51|いいえ|  
|HostName|**nvarchar**|クライアントが実行されているコンピューターの名前。 このデータ列には、クライアントがホスト名を指定している場合にデータが格納されます。 ホスト名を指定するには、HOST_NAME 関数を使用します。|8|[ユーザー アカウント制御]|  
|IntegerData|**int**|返される行数の推定値。|25|[ユーザー アカウント制御]|  
|IsSystem|**int**|イベントがシステム プロセスとユーザー プロセスのどちらで発生したか。 1 はシステム、0 はユーザーです。|60|[ユーザー アカウント制御]|  
|LineNumber|**int**|エラーを含む行番号を表示します。|5|[ユーザー アカウント制御]|  
|LoginName|**nvarchar**|ユーザーのログイン名 ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] セキュリティ ログインまたは DOMAIN\username という形式の [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ログイン資格情報)。|11|[ユーザー アカウント制御]|  
|LoginSID|**image**|ログイン ユーザーのセキュリティ ID 番号 (SID)。 この情報は、sys.server_principals カタログ ビューで参照できます。 各 SID はサーバーのログインごとに一意です。|41|いいえ|  
|NestLevel|**int**|@@NESTLEVEL から返されるデータを表す整数。|29|[ユーザー アカウント制御]|  
|NTDomainName|**nvarchar**|ユーザーが所属する Windows ドメイン。|7|[ユーザー アカウント制御]|  
|NTUserName|**nvarchar**|Windows のユーザー名。|6|[ユーザー アカウント制御]|  
|ObjectID|**int**|システムによって割り当てられたオブジェクト ID。|22|[ユーザー アカウント制御]|  
|ObjectName|**nvarchar**|参照されているオブジェクトの名前。|34|[ユーザー アカウント制御]|  
|ObjectType|**int**|イベントに関係するオブジェクトの種類を表す値。 この値は sys.objects の type 列に対応します。 値については、「 [ObjectType トレース イベント列](../../relational-databases/event-classes/objecttype-trace-event-column.md)」を参照してください。|28|[ユーザー アカウント制御]|  
|RequestID|**int**|ステートメントが含まれている要求の ID。|49|[ユーザー アカウント制御]|  
|ServerName|**nvarchar**|トレースされている [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスの名前。|26|いいえ|  
|SessionLoginName|**nvarchar**|セッションを開始したユーザーのログイン名。 たとえば、Login1 を使用して [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] に接続し、Login2 でステートメントを実行すると、SessionLoginName には Login1 が表示され、LoginName には Login2 が表示されます。 この列には、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ログインと Windows ログインの両方が表示されます。|64|[ユーザー アカウント制御]|  
|SPID|**int**|イベントが発生したセッションの ID。|12|[ユーザー アカウント制御]|  
|StartTime|**datetime**|イベントの開始時刻 (取得できた場合)。|14|[ユーザー アカウント制御]|  
|TextData|**ntext**|トレースでキャプチャされたイベント クラスに依存するテキスト値。|1|[ユーザー アカウント制御]|  
|TransactionID|**bigint**|システムによって割り当てられたトランザクション ID。|4|[ユーザー アカウント制御]|  
|XactSequence|**bigint**|現在のトランザクションを説明するトークン。|50|[ユーザー アカウント制御]|  
|GroupID|**int**|SQL トレース イベントが発生したワークロード グループの ID。|66|[ユーザー アカウント制御]|  
  
## <a name="see-also"></a>参照  
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [プラン表示の論理操作と物理操作のリファレンス](../../relational-databases/showplan-logical-and-physical-operators-reference.md)  
  
  
