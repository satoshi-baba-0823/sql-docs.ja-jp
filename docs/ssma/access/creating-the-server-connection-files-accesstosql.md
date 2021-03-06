---
title: サーバー接続ファイル (AccessToSQL) の作成 |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 08/17/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 829153be-aa8e-4162-87e8-69882feecf19
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: f083b38d64927ded898366434def4505cd3f67c7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47672660"
---
# <a name="creating-the-server-connection-files-accesstosql"></a>サーバー接続ファイル (AccessToSQL) の作成
サーバーの情報は、スクリプト ファイルの [サーバー] セクションでいずれかを指定します。 サーバーの情報は、別のサーバー接続ファイルにも指定できます。 サーバー接続ファイルのコマンド ライン パラメーターが`-c <serverconnectionfile>`します。 同じサーバー id がスクリプトとサーバーの両方の接続ファイルに存在する場合は、スクリプト ファイル内のサーバー定義と見なされます。  
  
```xml  
<!--Sample of server connection file commands -->  
<!--Connection to SQL Server-->  
  
<sql-server name="target_3">  
  
  <sql-server-authentication>  
  
    <server value="$TargetServerName$"/>  
  
    <database value="$TargetDB$"/>  
  
    <user-id value="$TargetUserName$"/>  
  
    <password value="$TargetPassword$"/>  
  
    <encrypt value="true"/>  
  
    <trust-server-certificate value="true"/>  
  
  </sql-server-authentication>  
  
</sql-server>  
```  
  
```xml  
<!--Connection to SQL Azure-->  
  
<sql-azure name="target_azure">  
  
  <server value="$TargetAzureServerName$"/>  
  
  <database value="$TargetAzureDB$"/>  
  
  <user-id value="$TargetAzureUserName$"/>  
  
  <password value="$TargetAzurePassword$"/>  
  
</sql-azure>  
```  
  
## <a name="server-connection-file-validation"></a>サーバー接続ファイルの検証  
ユーザーがスキーマ定義ファイルに対して自分のサーバー接続ファイルを簡単に検証できます **'A2SSConsoleScriptServersSchema.xsd'** 'スキーマ' フォルダー内にあります。  
  
## <a name="next-step"></a>次の手順  
コンソールの運用には、次の手順は[SSMA コンソールの実行&#40;AccessToSQL&#41;](../../ssma/access/executing-the-ssma-console-accesstosql.md)  
  
## <a name="see-also"></a>関連項目  
[SSMA コンソール (アクセス) の実行](http://msdn.microsoft.com/aa1bf665-8dc0-4259-b36f-46ae67197a43)  
  
