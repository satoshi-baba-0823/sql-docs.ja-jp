---
title: Working with Schema Rowsets in ADOMD.NET |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- metadata [ADOMD.NET]
- retrieving metadata
- schema rowsets [ADOMD.NET]
ms.assetid: 7bf75bf8-f1e1-44f6-ac42-c38a681654cf
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f00e4e22549cf73bf95f538b1d26797d6a8509f1
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48051925"
---
# <a name="working-with-schema-rowsets-in-adomdnet"></a>ADOMD.NET でのスキーマ行セットの操作
  ADOMD.NET オブジェクト モデルで使用可能なメタデータよりも多くのメタデータが必要な場合のために、ADOMD.NET には、XML for Analysis (XMLA)、OLE DB、OLE DB for OLAP、および OLE DB for Data Mining のすべてのスキーマ行セットを取得する機能が用意されています。  
  
 **XML for Analysis メタデータ**  
 XML for Analysis スキーマ行セットでは、サーバーに関する詳細情報を取得できます。 取得できる情報には、サーバーで使用可能なデータ ソース、プロバイダーによって予約されているキーワード、プロバイダーがサポートしているリテラルなどがあります。 XML for Analysis スキーマ行セットを使用して、プロバイダーがサポートするすべてのスキーマ行セットを検出することもできます。  
  
 詳細については: [XML for Analysis スキーマ行セット](../schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
 **OLE DB メタデータ**  
 OLE DB スキーマ行セットは、さまざまなプロバイダーから情報を取得するための業界標準の方法を提供します。  
  
 詳細については: [OLE DB スキーマ行セット](../schema-rowsets/ole-db/ole-db-schema-rowsets.md)  
  
 **OLAP メタデータ**  
 分析データ ソースのスキーマ情報には、分析データ ソースで使用できるデータベースやカタログ、データベース内のキューブとマイニング モデル、データ ソースのキューブに割り当てられているロールなどがあります。  
  
 詳細については: [OLE DB for OLAP スキーマ行セット](../schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
 **データ マイニング メタデータ**  
 OLAP メタデータの他に、スキーマ行セットを使用してデータ マイニング メタデータを取得できます。 使用可能な行セットは、データベース内で使用できるデータ マイニング モデル、使用可能なマイニング アルゴリズム、アルゴリズムに必要なパラメーター、マイニング構造などに関する情報を提供します。  
  
 詳細については:[データ マイニング スキーマ行セット](../schema-rowsets/data-mining/data-mining-schema-rowsets.md)  
  
 これらのさまざまな各スキーマ行セットについて、<xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A> オブジェクトの <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> メソッドを使用して GUID または XMLA 名を渡すことにより、行セットからメタデータを取得します。  
  
## <a name="retrieving-metadata-by-passing-guids"></a>GUID の引き渡しによるメタデータの取得  
 <xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid> クラスには、プロバイダーおよび分析データ ソースによってサポートされる、最も一般的なスキーマ行セットを表すフィールドの一覧が格納されます。 プロバイダーまたは分析データ ソースから一般的なメタデータとプロバイダー固有のメタデータの両方を取得するには、次のいずれかのメソッドで、<xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid> オブジェクト内に格納されている GUID を使用します。  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
> [!NOTE]  
>  ADOMD.NET データ プロバイダーは、特定のプロバイダーおよび分析データ ソースで使用可能な機能を使用してスキーマ情報を提供します。 プロバイダーおよびデータ ソースごとに、異なるメタデータを提供できます。  
  
## <a name="retrieving-metadata-by-passing-xmla-names"></a>XMLA 名の引き渡しによるメタデータの取得  
 次のメソッドでは、返されるスキーマ情報を特定する XMLA スキーマ名、および返される列の制限の配列を引数として指定します。  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
 これらの各メソッドは、スキーマ情報を使用して作成された `DataSet` オブジェクトのインスタンスを返します。 `DataSet` オブジェクトは、Microsoft .NET Framework クラス ライブラリの `System.Data` 名前空間にあります。  
  
## <a name="example"></a>例  
 次の例では、GetActions 関数接続、キューブ名、座標、および座標の種類を取得、 [MDSCHEMA_ACTIONS 行セット](../schema-rowsets/ole-db-olap/mdschema-actions-rowset.md)、選択した座標で使用可能なアクションを返します。  
  
 [!code-csharp[Adomd.NetClient#GetActions](../../snippets/csharp/SQL14/adomd.net/adomd.netclient/cs/adomdexample.cs#getactions)]  
  
## <a name="see-also"></a>参照  
 [分析データ ソースからのメタデータの取得](retrieving-metadata-from-an-analytical-data-source.md)  
  
  
