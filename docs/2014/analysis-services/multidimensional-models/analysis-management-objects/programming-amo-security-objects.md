---
title: AMO セキュリティ オブジェクトのプログラミング |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- programming [AMO]
- Analysis Management Objects, security
- AMO, security
ms.assetid: 5d963721-6e6e-46eb-bc9b-18724dd0b751
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 7cd595825659b303e9bb705ce4fd9051a76f9f61
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48120782"
---
# <a name="programming-amo-security-objects"></a>AMO セキュリティ オブジェクトのプログラミング
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]、セキュリティ オブジェクトをプログラミングまたは AMO セキュリティ オブジェクトを使用するアプリケーションを実行するサーバーの管理者グループまたはデータベース管理者グループのメンバーである必要があります。 サーバー管理者とデータベース管理者は、アクセス レベルは、によって提供される[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]します。  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] では、オブジェクトに割り当てられたロールと権限の組み合わせを使用してオブジェクトへのユーザー アクセスが行われます。 詳細については、次を参照してください。 [AMO セキュリティ クラス](amo-security-classes.md)します。  
  
## <a name="role-and-permission-objects"></a>Role オブジェクトと Permission オブジェクト  
 サーバー ロールのコレクションに含まれる唯一のロールが Administrators ロールです。 新しいロールをサーバー ロールのコレクションに追加することはできません。 Administrators ロールのメンバーは、サーバー内のすべてのオブジェクトに完全にアクセスできます。  
  
 <xref:Microsoft.AnalysisServices.Role> オブジェクトはデータベース レベルで作成されます。 ロールのメンテナンスで必要な作業は、ロールへのメンバーの追加またはロールからのメンバーの削除と、<xref:Microsoft.AnalysisServices.Database> オブジェクトへのロールの追加または削除だけです。 ロールに関連付けられた <xref:Microsoft.AnalysisServices.Permission> オブジェクトが存在する場合は、ロールを削除できません。 ロールを削除するには、<xref:Microsoft.AnalysisServices.Permission> オブジェクト内の <xref:Microsoft.AnalysisServices.Database> オブジェクトをすべて検索し、<xref:Microsoft.AnalysisServices.Role> を権限から削除する必要があります。その後、<xref:Microsoft.AnalysisServices.Role> を <xref:Microsoft.AnalysisServices.Database> から削除できます。  
  
 権限は、権限が設定されたオブジェクトに対する有効なアクションを定義します。 権限は、<xref:Microsoft.AnalysisServices.Database>、<xref:Microsoft.AnalysisServices.DataSource>、<xref:Microsoft.AnalysisServices.Dimension>、<xref:Microsoft.AnalysisServices.Cube>、<xref:Microsoft.AnalysisServices.MiningStructure>、および <xref:Microsoft.AnalysisServices.MiningModel> の各オブジェクトに対して設定できます。 権限のメンテナンスには、対応するアクセス プロパティによる、有効なアクセスの許可や取り消しが含まれます。 それぞれの有効なアクセスには、必要なアクセス レベルを設定できるプロパティがあります。 Process、ReadDefinition、Read、Write、および Administer の各操作に対してアクセスを定義できます。 Administer アクセスは、<xref:Microsoft.AnalysisServices.Database> オブジェクトに対してのみ定義されます。 Administer データベース権限をロールに付与すると、データベース管理者のセキュリティ レベルが得られます。  
  
 次のサンプルでは、Database Administrators、Processors、Writers、Readers の 4 つのロールを作成します。  
  
 Database Administrators は指定されたデータベースを管理できます。  
  
 Processors は、データベース内のすべてのオブジェクトを処理して結果を検証できます。 結果を検証するには、指定されたキューブに対してデータベース オブジェクトへの読み取りアクセスを明示的に有効にする必要があります。読み取り権限は子オブジェクトに適用されないためです。  
  
 Writers は、指定されたキューブの読み取りおよび書き込みが可能です。また、セルへのアクセスは顧客ディメンションの "United States" に制限されます。  
  
 Readers は指定されたキューブの読み取りが可能です。また、セルへのアクセスは顧客ディメンションの "United States" に制限されます。  
  
```  
static public void CreateRolesAndPermissions(Database db, Cube cube)  
{  
    Role role;  
    DatabasePermission dbperm;  
    CubePermission cubeperm;  
  
    #region Create the Database Administrators role  
  
    // Create the Database Administrators role.  
    role = db.Roles.Add("Database Administrators");  
    role.Members.Add(new RoleMember("")); // e.g. domain\user  
    role.Update();  
  
    // Assign administrative permissions to this role.  
    // Members of this role can perform any operation within the database.  
    dbperm = db.DatabasePermissions.Add(role.ID);  
    dbperm.Administer = true;  
    dbperm.Update();  
  
    #endregion  
  
    #region Create the Processors role  
  
    // Create the Processors role.  
    role = db.Roles.Add("Processors");  
    role.Members.Add(new RoleMember("")); // e.g. myDomain\johndoe  
    role.Update();  
  
    // Assign Read and Process permissions to this role.  
    // Members of this role can process objects in the database and query them to verify results.  
    // Process permission applies to all contained objects, i.e. all dimensions and cubes.  
    // Read permission does not apply to contained objects, so we must assign the permission explicitly on the cubes.  
    dbperm = db.DatabasePermissions.Add(role.ID);  
    dbperm.Read = ReadAccess.Allowed;  
    dbperm.Process = true;  
    dbperm.Update();  
  
    cubeperm = cube.CubePermissions.Add(role.ID);  
    cubeperm.Read = ReadAccess.Allowed;  
    cubeperm.Update();  
  
    #endregion  
  
    #region Create the Writers role  
  
    // Create the Writers role.  
    role = db.Roles.Add("Writers");  
    role.Members.Add(new RoleMember("")); // e.g. redmond\johndoe  
    role.Update();  
  
    // Assign Read and Write permissions to this role.  
    // Members of this role can discover, query and writeback to the Adventure Works cube.  
    // However cell access and writeback is restricted to the United States (in the Customer dimension).  
    dbperm = db.DatabasePermissions.Add(role.ID);  
    dbperm.Read = ReadAccess.Allowed;  
    dbperm.Update();  
  
    cubeperm = cube.CubePermissions.Add(role.ID);  
    cubeperm.Read = ReadAccess.Allowed;  
    cubeperm.Write = WriteAccess.Allowed;  
    cubeperm.CellPermissions.Add(new CellPermission(CellPermissionAccess.Read, "[Customer].[Country-Region].CurrentMember is [Customer].[Country-Region].[Country-Region].&[United States]"));  
    cubeperm.CellPermissions.Add(new CellPermission(CellPermissionAccess.ReadWrite, "[Customer].[Country-Region].CurrentMember is [Customer].[Country-Region].[Country-Region].&[United States]"));  
    cubeperm.Update();  
  
    #endregion  
  
    #region Create the Readers role  
  
    // Create the Readers role.  
    role = db.Roles.Add("Readers");  
    role.Members.Add(new RoleMember("")); // e.g. redmond\johndoe  
    role.Update();  
  
    // Assign Read permissions to this role.  
    // Members of this role can discover and query the Adventure Works cube.  
    // However the Customer dimension is restricted to the United States.  
    dbperm = db.DatabasePermissions.Add(role.ID);  
    dbperm.Read = ReadAccess.Allowed;  
    dbperm.Update();  
  
    cubeperm = cube.CubePermissions.Add(role.ID);  
    cubeperm.Read = ReadAccess.Allowed;  
    Dimension dim = db.Dimensions.GetByName("Customer");  
    DimensionAttribute attr = dim.Attributes.GetByName("Country-Region");  
    CubeDimensionPermission cubedimperm = cubeperm.DimensionPermissions.Add(dim.ID);  
    cubedimperm.Read = ReadAccess.Allowed;  
    AttributePermission attrperm = cubedimperm.AttributePermissions.Add(attr.ID);  
    attrperm.AllowedSet = "{[Customer].[Country-Region].[Country-Region].&[United States]}";  
    cubeperm.Update();  
  
    #endregion  
}  
```  
  
## <a name="see-also"></a>参照  
 <xref:Microsoft.AnalysisServices>   
 [AMO クラスの概要](amo-classes-introduction.md)   
 [AMO セキュリティ オブジェクトのプログラミング](programming-amo-security-objects.md)   
 [アクセス許可とアクセス権&#40;Analysis Services - 多次元データ&#41;](https://msdn.microsoft.com/library/ms174786(v=sql.120).aspx)   
 [Analysis Services のインスタンスをセキュリティで保護します。](https://technet.microsoft.com/library/ms175663\(v=sql.110\).aspx)   
 [論理アーキテクチャ&#40;Analysis Services - 多次元データ&#41;](../olap-logical/understanding-microsoft-olap-logical-architecture.md)   
 [データベース オブジェクト&#40;Analysis Services - 多次元データ&#41;](../olap-logical/database-objects-analysis-services-multidimensional-data.md)  
  
  
