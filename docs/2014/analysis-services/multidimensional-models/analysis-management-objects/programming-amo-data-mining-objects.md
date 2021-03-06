---
title: AMO データ マイニング オブジェクトのプログラミング |Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- programming [AMO]
- data mining [AMO]
- AMO, data mining
- Analysis Management Objects, data mining
ms.assetid: d27f58b9-91be-449c-8403-439aa6dd1ff9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 12844542252dac6781eae55fa16c463776731cbd
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48165762"
---
# <a name="programming-amo-data-mining-objects"></a>AMO データ マイニング オブジェクトのプログラミング
  AMO を使用すれば、データ マイニング オブジェクトを簡単にプログラミングできます。 まず、マイニング プロジェクトをサポートするデータ構造モデルを作成します。 次に、マイニング アルゴリズムをサポートするデータ マイニング モデルを作成します。マイニング アルゴリズムは、データに含まれる未知のリレーションシップを予測または検出するために使用します。 構造やアルゴリズムなどのマイニング プロジェクトを作成したら、マイニング モデルを処理することにより、後でクライアント アプリケーションからクエリや予測を行うときに使用するトレーニングされたモデルを取得できます。  
  
 1 つ覚えておく必要があるのは、AMO ではクエリを実行できないという点です。AMO は、マイニング構造およびマイニング モデルの管理に使用します。 データを照会するには、使用[ADOMD.NET での開発](../adomd-net/developing-with-adomd-net.md)します。  
  
 このトピックには、次のセクションが含まれます。  
  
-   [MiningStructure オブジェクト](#MiningStructure)  
  
-   [MiningModel オブジェクト](#MiningModel)  
  
##  <a name="MiningStructure"></a> MiningStructure オブジェクト  
 マイニング構造は、すべてのマイニング モデルの作成に使用するデータ構造の定義です。 マイニング構造には、データベースで定義されたデータ ソース ビューへのバインドと、マイニング モデル内のすべての列定義が含まれます。 マイニング構造には複数のマイニング モデルを含めることができます。  
  
 作成、<xref:Microsoft.AnalysisServices.MiningStructure>オブジェクトには、次の手順が必要です。  
  
1.  <xref:Microsoft.AnalysisServices.MiningStructure> オブジェクトを作成し、基本属性を設定します。 基本属性には、オブジェクト名、オブジェクト ID (内部 ID)、およびデータ ソース バインドがあります。  
  
2.  モデルの列を作成します。 列はスカラー定義またはテーブル定義のいずれかです。  
  
     各列には、名前、内部 ID、種類、コンテンツ定義、およびバインドが必要です。  
  
3.  オブジェクトの Update メソッドを使用して、サーバー上で <xref:Microsoft.AnalysisServices.MiningStructure> オブジェクトを更新します。  
  
     マイニング構造は処理可能です。マイニング構造を処理すると、子マイニング モデルが処理または再トレーニングされます。  
  
 次のサンプル コードでは、売り上げを時系列で予測するマイニング構造を作成します。 サンプル コードを実行する前に必ずデータベース*db*のパラメーターとして渡される`CreateSalesForecastingMiningStructure`に含まれています`db.DataSourceViews[0]`ビューへの参照*dbo.vTimeSeries* で[!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)]サンプル データベース。  
  
```  
public static MiningStructure CreateSalesForecastingMiningStructure(Database db)  
{  
    MiningStructure ms = db.MiningStructures.FindByName("Forecasting Sales Structure");  
    if (ms != null)  
        ms.Drop();  
    ms = db.MiningStructures.Add("Forecasting Sales Structure", "Forecasting Sales Structure");  
    ms.Source = new DataSourceViewBinding(db.DataSourceViews[0].ID);  
  
    ScalarMiningStructureColumn amount = ms.Columns.Add("Amount", "Amount");  
    amount.Type = MiningStructureColumnTypes.Double;  
    amount.Content = MiningStructureColumnContents.Continuous;  
    amount.KeyColumns.Add("vTimeSeries", "Amount", OleDbType.Currency);  
  
    ScalarMiningStructureColumn modelRegion = ms.Columns.Add("Model Region", "Model Region");  
    modelRegion.IsKey = true;  
    modelRegion.Type = MiningStructureColumnTypes.Text;  
    modelRegion.Content = MiningStructureColumnContents.Key;  
    modelRegion.KeyColumns.Add("vTimeSeries", "ModelRegion", OleDbType.WChar, 56);  
  
    ScalarMiningStructureColumn qty = ms.Columns.Add("Quantity", "Quantity");  
    qty.Type = MiningStructureColumnTypes.Long;  
    qty.Content = MiningStructureColumnContents.Continuous;  
    qty.KeyColumns.Add("vTimeSeries", "Quantity", OleDbType.Integer);  
  
    ScalarMiningStructureColumn timeIndex = ms.Columns.Add("TimeIndex", "TimeIndex");  
    timeIndex.IsKey = true;  
    timeIndex.Type = MiningStructureColumnTypes.Long;  
    timeIndex.Content = MiningStructureColumnContents.KeyTime;  
    timeIndex.KeyColumns.Add("vTimeSeries", "TimeIndex", OleDbType.Integer);  
  
    ms.Update();  
    return ms;  
}  
```  
  
##  <a name="MiningModel"></a> MiningModel オブジェクト  
 マイニング モデルは、マイニング アルゴリズムで使用されるすべての列および列定義のリポジトリです。  
  
 作成、<xref:Microsoft.AnalysisServices.MiningModel>オブジェクトには、次の手順が必要です。  
  
1.  <xref:Microsoft.AnalysisServices.MiningModel> オブジェクトを作成し、基本属性を設定します。  
  
     基本属性には、オブジェクト名、オブジェクト ID (内部 ID)、およびマイニング アルゴリズムの仕様があります。  
  
2.  マイニング モデルの列を追加します。 列の 1 つをケース キーとして定義する必要があります。  
  
3.  オブジェクトの Update メソッドを使用して、サーバー上で <xref:Microsoft.AnalysisServices.MiningModel> オブジェクトを更新します。  
  
     <xref:Microsoft.AnalysisServices.MiningModel> オブジェクトは、親の <xref:Microsoft.AnalysisServices.MiningStructure> に含まれる他のモデルから独立して処理できます。  
  
 次のサンプル コードでは、"Forecasting Sales Structure" マイニング構造に基づいて Microsoft タイム シリーズ予測モデルを作成します。  
  
```  
public static MiningModel CreateSalesForecastingMiningModel(MiningStructure ms)  
{  
    if (ms.MiningModels.ContainsName("Sales Forecasting Model"))  
    {  
        ms.MiningModels["Sales Forecasting Model"].Drop();  
    }  
    MiningModel mm = ms.CreateMiningModel(true, "Sales Forecasting Model");  
    mm.Algorithm = MiningModelAlgorithms.MicrosoftTimeSeries;  
    mm.AlgorithmParameters.Add("PERIODICITY_HINT", "{12}");  
  
    MiningModelColumn amount = new MiningModelColumn();  
    amount.SourceColumnID = "Amount";  
    amount.Usage = MiningModelColumnUsages.Predict;  
  
    MiningModelColumn modelRegion = new MiningModelColumn();  
    modelRegion.SourceColumnID = "Model Region";  
    modelRegion.Usage = MiningModelColumnUsages.Key;  
  
    MiningModelColumn qty = new MiningModelColumn();  
    qty.SourceColumnID = "Quantity";  
    qty.Usage = MiningModelColumnUsages.Predict;  
  
    MiningModelColumn ti = new MiningModelColumn();  
    ti.SourceColumnID = "TimeIndex";  
    ti.Usage = MiningModelColumnUsages.Key;  
  
    mm.Update();  
    mm.Process(ProcessType.ProcessFull);  
    return mm;  
}  
```  
  
## <a name="see-also"></a>参照  
 <xref:Microsoft.AnalysisServices>   
 [AMO 基礎クラス](amo-fundamental-classes.md)   
 [AMO クラスの概要](amo-classes-introduction.md)   
 [AMO データ マイニング クラス](amo-data-mining-classes.md)   
 [論理アーキテクチャ&#40;Analysis Services - 多次元データ&#41;](../olap-logical/understanding-microsoft-olap-logical-architecture.md)   
 [データベース オブジェクト&#40;Analysis Services - 多次元データ&#41;](../olap-logical/database-objects-analysis-services-multidimensional-data.md)  
  
  
