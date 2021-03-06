---
title: 多次元モデリング (Adventure Works チュートリアル) |Microsoft ドキュメント
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: def2d0f3b09fd7f78b499ed64b83661e6e51f690
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "34023759"
---
# <a name="multidimensional-modeling-adventure-works-tutorial"></a>多次元モデリング (Adventure Works チュートリアル)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] のチュートリアルへようこそ。 このチュートリアルでは、架空の会社 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] の例を使用しながら、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] で [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] プロジェクトの開発と配置を行う方法を説明します。  
  
## <a name="what-you-learn"></a>学習内容  
このチュートリアルでは、次の内容を学習します。  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] の [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]プロジェクトにおいて、データ ソース、データ ソース ビュー、ディメンション、属性、属性リレーションシップ、階層、およびキューブを定義する方法  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] プロジェクトを [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]のインスタンスに配置してキューブとディメンションのデータを表示する方法と、配置したオブジェクトを処理して、基になるデータ ソースからのデータをオブジェクトに格納する方法  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] プロジェクトのメジャー、ディメンション、階層、属性、メジャー グループを変更する方法と、変更した差分を開発サーバーの配置済みキューブに配置する方法  
  
-   キューブ内で計算、主要業績評価指標 (KPI)、アクション、パースペクティブ、翻訳、およびセキュリティ ロールを定義する方法  
  
これらのレッスンのコンテキストをよりよく理解できるように、このチュートリアルにはシナリオの説明が付属しています。 詳細については、「 [Analysis Services のチュートリアル シナリオ](../analysis-services/analysis-services-tutorial-scenario.md)」を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
このチュートリアルのすべてのレッスンを完了するには、サンプル データ、サンプル プロジェクト ファイル、およびソフトウェアが必要です。 このチュートリアルの必要条件を入手およびインストールする方法については、「 [Analysis Services 多次元モデリング チュートリアル用のサンプル データおよびプロジェクトのインストール](../analysis-services/install-sample-data-and-projects.md)」を参照してください。  
  
また、このチュートリアルを正常に完了するには、次の権限が付与されている必要があります。  
  
-   作業者が、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] コンピューターの Administrators ローカル グループのメンバーであるか、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]インスタンスのサーバー管理ロールのメンバーである。  
  
-   アクセス許可の読み取りが必要、 **AdventureWorksDW**サンプル データベース。 このサンプル データベースは、 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] リリースで有効です。  
  
## <a name="lessons"></a>レッスン  
このチュートリアルには次のレッスンが含まれています。  
  
|レッスン|推定所要時間|  
|----------|------------------------------|  
|[レッスン 1: 分析結果内のデータ ソース ビューを定義するサービス プロジェクト](../analysis-services/lesson-1-defining-a-data-source-view-within-an-analysis-services-project.md)|15 分|  
|[レッスン 2: 定義して、キューブの展開](../analysis-services/lesson-2-defining-and-deploying-a-cube.md)|30 分|  
|[レッスン 3: メジャー、属性および階層を変更する](../analysis-services/lesson-3-modifying-measures-attributes-and-hierarchies.md)|45 分|  
|[レッスン 4: 高度な属性およびディメンションのプロパティを定義します。](../analysis-services/lesson-4-defining-advanced-attribute-and-dimension-properties.md)|120 分|  
|[レッスン 5: ディメンションとメジャー グループ間のリレーションシップを定義します。](../analysis-services/lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)|45 分|  
|[レッスン 6: 計算の定義](../analysis-services/lesson-6-defining-calculations.md)|45 分|  
|[レッスン 7: 主要業績評価指標を定義する & #40 です。Kpi"&"#41;](../analysis-services/lesson-7-defining-key-performance-indicators-kpis.md)|30 分|  
|[レッスン 8: アクションの定義](../analysis-services/lesson-8-defining-actions.md)|30 分|  
|[レッスン 9: Defining Perspectives and Translations](../analysis-services/lesson-9-defining-perspectives-and-translations.md)|30 分|  
|[レッスン 10: 管理ロールの定義](../analysis-services/lesson-10-defining-administrative-roles.md)|15 分|  
  
> [!NOTE]  
> このチュートリアルで作成するキューブ データベースの簡易バージョンでは、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] GitHub でダウンロードできる Adventure Works サンプル データベースの一部である多次元モデル プロジェクト。 Adventure Works 多次元データベースのチュートリアル バージョンは、すぐに習得することが望まれる特定のスキルを中心にして簡易化されています。 チュートリアルの終了後は、自分で多次元モデル プロジェクトを用意してさまざまな操作を行うと、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 多次元モデリングの理解が深まります。  
  
## <a name="next-step"></a>次の手順  
チュートリアルを開始するには、最初のレッスン「 [レッスン 1: Analysis Services プロジェクト内でのデータ ソース ビューの定義](../analysis-services/lesson-1-defining-a-data-source-view-within-an-analysis-services-project.md)」に進んでください。  
  
  
  
