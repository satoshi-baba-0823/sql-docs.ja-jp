---
title: 対象サーバーでの暗号化オプションの設定 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 8ac5ea2fbf7188fc117c20a3d0d3956cfaed0694
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47713452"
---
# <a name="set-encryption-options-on-target-servers"></a>対象サーバーでの暗号化オプションの設定
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

マスター サーバーと一部またはすべての対象サーバーの間で SSL (Secure Sockets Layer) 暗号通信の証明書を使用できない場合、これらの間のチャネルを暗号化するには、必要なセキュリティ レベルを使用するように対象サーバーを構成します。  
  
マスター サーバーと対象サーバーの間の特定の通信チャネルに求められる適切なセキュリティ レベルを構成するには、対象サーバーの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントのレジストリ サブキー **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** を、次のいずれかの値に設定します。 \<*instance_name*> の値は **MSSQL.**_n_ です。 たとえば、 **MSSQL.1** や **MSSQL.3**となります。  
  
|ReplTest1|[説明]|  
|---------|---------------|  
|**0**|この対象サーバーとマスター サーバーの間の暗号化を無効にします。 対象サーバーとマスター サーバー間のチャネルのセキュリティを別の手段で保護する場合にこのオプションを選択します。|  
|**1**|この対象サーバーとマスター サーバーの間のみ暗号化を有効にしますが、証明書の検証は必要ありません。|  
|**2**|この対象サーバーとマスター サーバーの間で、完全な SSL 暗号化と証明書の検証を有効にします。 この設定が既定値です。 別の値を選択する具体的な理由がある場合を除いて、この値を変更しないことをお勧めします。|  
  
**1** または **2** を指定する場合、マスター サーバーと対象サーバーの両方で SSL を有効にしている必要があります。 **2** を指定する場合、マスター サーバーには適切に署名された証明書も必要になります。  
  
> [!CAUTION]  
> [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a>参照  
[データベース エンジンへの暗号化接続を有効にする方法 (SQL Server 構成マネージャー)](http://msdn.microsoft.com/en-us/e1e55519-97ec-4404-81ef-881da3b42006)  
  
