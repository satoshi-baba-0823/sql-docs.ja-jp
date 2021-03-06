---
title: DQS でのデータ プロファイルと通知 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- data-quality-services
ms.topic: conceptual
ms.assetid: a778bb5b-8e35-4a7b-b04a-ae2b46dec21b
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: bf51d32e9e56e0e8d377e0a1d87e079f0239823b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48221872"
---
# <a name="data-profiling-and-notifications-in-dqs"></a>DQS のデータ プロファイルと通知
  [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) のデータ プロファイルは、既存のデータ ソースのデータを分析し、DQS のアクティビティでデータに関する統計情報を表示するプロセスです。 このプロセスでは、データ品質が自動的に測定されます。 DQS のプロファイルは、DQS のナレッジ マネージメントおよびデータ品質プロジェクトに統合されており、 動的に調整が可能です。 プロファイルの主な目的は、一連のデータ品質プロセスを通じて意思決定を支援すること、およびプロセスの有効性を評価することの 2 つです。 DQS のプロファイル プロセスには次の利点があります。  
  
-   ソース データの品質について調べることができ、データ品質の問題を特定するのに役立ちます。  
  
-   データ品質プロセスの有効性を評価し、ナレッジ検出、データ クレンジング、照合ポリシー、および照合作業を順をおって行うことができます。  
  
-   最も関連性の高い情報が最も適切なタイミングで表示されます。  
  
-   重要な統計情報や対応が必要な可能性があるイベントを示す通知が生成されます。 多くの場合、DQS の通知には、現在の状況を示す情報とその状況を改善するための推奨される操作が示されます。  
  
 プロファイルを行うと、Data Quality Services をナレッジ検出、クレンジング、および照合に使用するだけでなく、分析ツールとしても使用することができます。 分析用のナレッジ ベースを 1 つ作成し、そのナレッジ ベースを使用してナレッジ検出を実行することで、ナレッジ ベースが検出、クレンジング、および照合のニーズを満たすかどうかをプロファイル統計情報から判断することができます。  
  
##  <a name="How"></a> プロファイルのしくみ  
 プロファイルは、ナレッジ ベースの品質を測定するものではなく、 ソース データの品質を測定するためのものです。 プロファイルにより、ナレッジ マネージメントまたはデータ品質プロジェクトで実行している特定の操作について、その操作によるソース データに対する効果を示す統計情報が提供されます。 プロファイルは常に、実行中の特定のアクティビティのコンテキストで実行されます。 画面に表示されるプロファイルのタブをクリックすることで、実行中のアクティビティのステージを終了せずにプロファイル データを表示できます。 プロファイル テーブルの値はプロセスの実行と同時にリアルタイムで設定されるため、データ品質タスクを実行しながら評価することが可能です。 クレンジングや重複除去の実行後にソース データが向上するかどうか、およびどの程度向上するかを確認することができます。  
  
 プロファイルの数値は、値の出現回数を示し、多くの場合は全体に占める割合も示します。ただし、一意性の基準は例外で、 値の出現回数に関係なく、値の絶対数を示します。  
  
 プロファイルは、DQS ナレッジ ドリブン ソリューションの一部であり、 ナレッジ ベース、照合、またはデータ クレンジングのプロセスに関する情報を、データ ソースのフィールドとナレッジ ベースのドメインのマッピングに基づいて提供します。 プロファイルはマッピングが完了している場合にのみ実行され、いずれかのアクティビティのマップ ステージ中は実行されません。 プロファイルは常にアクティビティにアタッチされます。 プロファイル プロセスは、ドメイン内のデータではなく、ドメインにマップされたデータで実行されます。 プロファイルは、アクティビティの次の手順に統合されています。  
  
-   ナレッジ検出アクティビティの **[検出]** と **[ドメイン値の管理]** の手順  
  
-   クレンジング アクティビティの **[最適化]** と **[結果の管理と表示]** の手順  
  
-   照合ポリシー アクティビティの **[照合ポリシー]** と **[照合結果]** の手順  
  
-   照合アクティビティの **[照合]** と **[エクスポート]** の手順  
  
 ドメイン管理アクティビティに対してはプロファイル統計情報は提供されません。  
  
##  <a name="Activity"></a> アクティビティ別のプロファイル データ  
 DQS のプロファイルでは、完全性 (データがどの程度存在するか)、正確性 (データがどの程度意図されたとおりに使用できるか)、および一意性 (異なるエンティティを異なる値でどの程度表すか) という、標準のデータ品質ディメンションを使用してデータの品質を表します。 既定では、存在しないと見なされるのは NULL 値と空の値で、これらの値があると完全性の割合が下がります。ただし、他の値も NULL に相当する値として定義すると、存在しないものと見なされるようになります。  
  
 プロファイルによってプロセスの評価に必要な統計情報が提供されますが、実際に評価するにはその統計情報を解釈する必要があります。 プロファイルの内容について理解するには、統計情報を列ごとに確認するようにしてください。  
  
 プロファイル統計情報は、DQS のアクティビティによって次のように異なります。  
  
-   正確性についてのプロファイル統計情報 (ドメイン別の割合) は、クレンジング アクティビティに対してのみ提供されます。 正確性に影響するものには、有効性、一貫性、構文エラー、およびドメイン ルールがあります。  
  
-   ソースの適切な値、修正された値、提案された値、およびドメイン別の修正された値と提案された値についてのプロファイル統計情報 (どちらも割合の数値) は、クレンジング アクティビティに対してのみ提供されます。  
  
-   有効性についてのプロファイル統計情報は、クレンジング アクティビティとナレッジ検出アクティビティに対して提供されます (クレンジングではレコード別、ナレッジ検出ではレコードおよびドメイン別)。 照合ポリシー アクティビティと照合アクティビティに対しては、有効性についての統計情報は提供されません。  
  
-   クレンジング アクティビティに対しては、一意性についてのプロファイル統計情報は提供されません。 一意性についてのプロファイル統計情報 (ソース全体およびドメイン別の数と割合) は、ナレッジ検出、照合ポリシー、および照合のアクティビティに対して提供されます。  
  
 アクティビティに関連する特定のプロファイル統計情報の詳細については、以下のトピックのプロファイルに関するセクションを参照してください。  
  
-   [ナレッジ検出を実行する](../../2014/data-quality-services/perform-knowledge-discovery.md)  
  
-   [DQS &#40;内部&#41; ナレッジを使用したデータのクレンジング](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md)  
  
-   [照合ポリシーを作成する](../../2014/data-quality-services/create-a-matching-policy.md)  
  
-   [照合プロジェクトを実行する](../../2014/data-quality-services/run-a-matching-project.md)  
  
##  <a name="Monitoring"></a> アクティビティ監視のプロファイル データ  
 ナレッジ検出、照合ポリシー、照合、およびクレンジングのアクティビティに対するプロファイル情報は、Data Quality Client のアクティビティのページだけでなく、アクティビティ監視でも確認できます。 アクティビティ監視には、現在と過去のアクティビティの概要が表示されます。 アクティビティのプロパティおよび関連する計算プロセスに加え、各アクティビティに対して生成されるプロファイル情報を 1 か所で確認することができます。 アクティビティのテーブルでアクティビティを選択すると、下のテーブルにプロファイル結果が表示されます。 プロファイル結果はエクスポートすることもできます。 詳細については、次を参照してください。 [DQS 管理](../../2014/data-quality-services/dqs-administration.md)します。  
  
##  <a name="Notifications"></a> 通知  
 DQS では、プロファイルによって重要な統計情報や基準を収集して表示することに加え、表示されるプロファイル統計情報に基づいて推奨される操作がある場合に、そのことを示す通知が生成されます (有効にしている場合)。 通知は、データ ソースについての重要な情報を強調すると共に、現在のアクティビティの実行された目的に対する有効性を示すために使用されます。 通知で提供されるヒントや推奨事項には、現在の状況を示す情報と、ナレッジ検出、データ クレンジング、またはデータ照合のアクティビティを改善するための推奨される方法が示されます。  
  
 DQS の通知は、ユーザーに関連すると思われる問題を提起したり、潜在的な問題に対処したりすることを目的としたものです。 通知が示されたときにそれに対処するかどうかは、目的に関連するかどうかに応じて選択できます。 たとえば、データ クレンジングで修正された値や提案された値がなく、完全性と正確性がどちらも 100% である場合に DQS で通知が生成されたとします。 この通知はアクティビティを実行する必要がないことを示していると考えられますが、 アクティビティを実行するかどうかはユーザーが選択できます。  
  
 通知は、 **[プロファイル]** タブに感嘆符付きのツールヒントで示されます。通知に関連付けられた統計情報は、その通知の根拠となる統計情報であることがわかるように赤色で表示されます。  
  
 通知の有効 (既定) と無効の切り替えは、Data Quality Client のホーム ページの **[全般設定]** タブにある **[管理]** セクションで行えます。 通知を無効にすると、ツールヒントは表示されず、統計情報も赤色になりません。 通知を無効にすることでパフォーマンスが大幅に向上することはありません。 通知を無効にしてもプロファイルは実行されます。  
  
 アクティビティの通知に関連付けられている特定の条件については、以下を参照してください。  
  
-   [ナレッジ検出を実行する](../../2014/data-quality-services/perform-knowledge-discovery.md)  
  
-   [DQS &#40;内部&#41; ナレッジを使用したデータのクレンジング](../../2014/data-quality-services/cleanse-data-using-dqs-internal-knowledge.md)  
  
-   [照合ポリシーを作成する](../../2014/data-quality-services/create-a-matching-policy.md)  
  
-   [照合プロジェクトを実行する](../../2014/data-quality-services/run-a-matching-project.md)  
  
## <a name="related-tasks"></a>Related Tasks  
  
|タスクの説明|トピック|  
|----------------------|-----------|  
|DQS で通知を有効または無効にする方法について説明します。|[DQS のプロファイル通知の有効化または無効化](../../2014/data-quality-services/enable-or-disable-profiling-notifications-in-dqs.md)|  
  
  
