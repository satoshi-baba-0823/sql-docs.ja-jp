---
title: sp_changesubscriptiondtsinfo (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sp_changesubscriptiondtsinfo
- sp_changesubscriptiondtsinfo_TSQL
helpviewer_keywords:
- sp_changesubscriptiondtsinfo
ms.assetid: 64fc085f-f81b-493b-b59a-ee6192d9736d
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 83355319cc8207369e36cf845005558fa38d4977
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47599800"
---
# <a name="spchangesubscriptiondtsinfo-transact-sql"></a>sp_changesubscriptiondtsinfo (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  サブスクリプションのデータ変換サービス (DTS) パッケージのプロパティを変更します。 このストアド プロシージャは、サブスクライバー側でサブスクリプション データベースについて実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_changesubscriptiondtsinfo [ [ @job_id = ] job_id ]  
    [ , [ @dts_package_name= ] 'dts_package_name' ]  
    [ , [ @dts_package_password= ] 'dts_package_password' ]  
    [ , [ @dts_package_location= ] 'dts_package_location' ]  
```  
  
## <a name="arguments"></a>引数  
 [  **@job_id=**] *job_id*  
 プッシュ サブスクリプションのディストリビューション エージェントのジョブ ID を指定します。 *job_id*は**varbinary (16)**、既定値はありません。 ディストリビューション ジョブ ID を見つけるには実行**sp_helpsubscription**または**sp_helppullsubscription**します。  
  
 [ **@dts_package_name**=] **'***dts_package_name***'**  
 DTS パッケージの名前を指定します。 *dts_package_name*は、 **sysname**、既定値は NULL です。 たとえば、パッケージを指定する名前付き**DTSPub_Package**、するには指定`@dts_package_name = N'DTSPub_Package'`します。  
  
 [ **@dts_package_password**=] **'***dts_package_password***'**  
 パッケージのパスワードを指定します。 *dts_package_password*は**sysname**既定値は null の場合、変更せずに残すパスワード プロパティが指定します。  
  
> [!NOTE]  
>  DTS パッケージにはパスワードが必要です。  
  
 [ **@dts_package_location**=] **'***dts_package_location***'**  
 パッケージの場所を指定します。 *dts_package_location*は、 **nvarchar (12)**、既定値は null の場合、変更せずに残す、パッケージの場所が指定します。 パッケージの場所を変更できます**ディストリビューター**または**サブスクライバー**します。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>コメント  
 **sp_changesubscriptiondtsinfo**スナップショット レプリケーションおよびトランザクション レプリケーションでプッシュ サブスクリプションのみに使用されます。  
  
## <a name="permissions"></a>アクセス許可  
 メンバーのみ、 **sysadmin**固定サーバー ロール、 **db_owner**固定データベース ロール、またはサブスクリプションの作成者が実行できる**sp_changesubscriptiondtsinfo**します。  
  
## <a name="see-also"></a>参照  
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
