---
title: catalog.deploy_packages | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: 8e861df6-d103-4d84-8438-e822533f6849
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3416d7244d89a4cfe959ec8608f77d56fb20e0a0
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47769550"
---
# <a name="catalogdeploypackages"></a>catalog.deploy_packages
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] カタログ内のフォルダーにパッケージを 1 つ以上展開するか、既に展開されている既存のパッケージを更新します。  
  
## <a name="syntax"></a>構文  
  
```sql  
[catalog].[deploy_packages]     [ @folder_name = ] folder_name,    [ @project_name = ] project_name,    [ @packages_table = ] packages_table,     [ @operation_id OUTPUT ] operation_id OUTPUT ]  
```  
  
## <a name="arguments"></a>引数  
 [ @folder_name = ] *folder_name*  
 フォルダーの名前。 *folder_name* は **nvarchar(128)** です。  
  
 [ @project_name = ] *project_name*  
 フォルダー、プロジェクトの名前。 *project_name* は **nvarchar(128)** です。  
  
 [ @packages_table = ] *packages_table*  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] パッケージ (.dtsx) ファイルのバイナリ コンテンツ。 *Packages_table* は **[catalog].[Package_Table_Type]** です。  
  
 [ @operation_id = ] *operation_id*  
 配置操作の一意識別子を返します。 *operation_id* は **bigint** です。  
  
## <a name="return-code-value"></a>リターン コード値  
 成功した場合は 0 を返します。  
  
## <a name="result-sets"></a>結果セット  
 なし  
  
## <a name="permissions"></a>アクセス許可  
 このストアド プロシージャには、次の権限のいずれかが必要です。  
  
-   プロジェクトまたはパッケージを更新するパッケージの変更のアクセス許可に対する CREATE_OBJECTS 権限、します。  
  
-   **ssis_admin** データベース ロールのメンバーシップ  
  
-   **sysadmin** サーバー ロールのメンバーシップ  
  
## <a name="errors-and-warnings"></a>エラーおよび警告  
 このストアド プロシージャがエラーを発生させる可能性がある条件を以下に示します。  
  
-   パラメーターが存在しないオブジェクトを参照、パラメーターが、既に存在するオブジェクトを作成しようとしています。 または、パラメーターは他の方法では無効です。  
  
-   ユーザーに十分な権限がない  
  
  
