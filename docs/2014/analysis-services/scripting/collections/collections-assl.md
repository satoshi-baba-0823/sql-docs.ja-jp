---
title: コレクション (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- collections [Analysis Services Scripting Language]
- Analysis Services Scripting Language, collections
- ASSL, collections
ms.assetid: 072b8c6b-1550-4cab-ae64-ba0e3e60b059
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 9f549a8d84f356b9315cdf3ec03ee41234e4dd0d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48199712"
---
# <a name="collections-assl"></a>コレクション (ASSL)
  このリファレンス セクションでは、Analysis Services スクリプト言語 (ASSL) スキーマでコレクションの役割を果たす各要素の構文と使い方について説明します。  
  
 ASSL スキーマには XML 要素しか含まれていませんが、開発者の観点から見ると、このセクションで説明する要素は `Dimensions` コレクションや `Cubes` コレクションなどのオブジェクトのコレクションに対応しています。  
  
 ほとんどの場合、コレクションはオブジェクト要素のコレクションです。ここで、複数名詞 (`Cubes` など) はコレクションを指定し、コレクションには同じ名詞の単数形 (`Cube` など) で指定された要素が含まれています。  
  
 場合によっては、スキーマがこの一般的な規則に従っていないことがあります。 たとえば、`ClassifiedColumns` コレクションには `ClassifiedColumnID` 要素が含まれています。  
  
 また、コレクションにはオブジェクトでなくオブジェクト プロパティに対応する要素が含まれている場合もあります。 たとえば、`Aliases` コレクションには `Alias` プロパティが含まれています。この各プロパティは単純な文字列値です。  
  
|要素|説明|  
|-------------|-----------------|  
|[要素をアカウント&#40;ASSL&#41;](accounts-element-assl.md)|定義されている勘定科目の種類のコレクションを格納する[データベース](../objects/database-element-assl.md)要素。|  
|[Actions 要素&#40;ASSL&#41;](actions-element-assl.md)|動作のコレクションが含まれています、[キューブ](../objects/cube-element-assl.md)または[パースペクティブ](../objects/perspective-element-assl.md)要素。|  
|[AggregationDesigns 要素&#40;ASSL&#41;](aggregationdesigns-element-assl.md)|データベースの複数のパーティションで共有できる集計デザインのコレクションを格納します。|  
|[AggregationInstances 要素&#40;ASSL&#41;](aggregationinstances-element-assl.md)|定義されている集計インスタンスのコレクションを格納する[パーティション](../objects/partition-element-assl.md)要素。|  
|[Aggregations 要素&#40;ASSL&#41;](aggregations-element-assl.md)|に対して定義された集計のコレクションを格納する[AggregationDesign](../objects/aggregationdesign-element-assl.md)要素。|  
|[AlgorithmParameters 要素&#40;ASSL&#41;](algorithmparameters-element-assl.md)|使用されるアルゴリズムのパラメーターのコレクションが含まれています、 [MiningModel](../objects/miningmodel-element-assl.md)要素。|  
|[Aliases 要素&#40;ASSL&#41;](aliases-element-assl.md)|コレクションを格納[エイリアス](../properties/alias-element-assl.md)要素に関連付けられた、[アカウント](../objects/account-element-assl.md)要素|  
|[AllMemberTranslations 要素&#40;ASSL&#41;](translations-element-assl.md)|コレクションを格納[翻訳](../objects/translation-element-assl.md)要素の All メンバーのキャプションに対する、[階層](../objects/hierarchy-element-assl.md)要素。|  
|[Annotations 要素&#40;ASSL&#41;](annotations-element-assl.md)|コレクションを格納[注釈](../objects/annotation-element-assl.md)親要素に関連付けられた要素。|  
|[Assemblies 要素&#40;ASSL&#41;](assemblies-element-assl.md)|コレクションを格納[アセンブリ](../objects/assembly-element-assl.md)要素に関連付けられた、 [Server](../objects/server-element-assl.md)要素または[データベース](../objects/database-element-assl.md)要素。|  
|[AttributeAllMemberTranslations 要素&#40;ASSL&#41;](attributeallmembertranslations-element-assl.md)|ディメンションの All メンバーのキャプションに対する翻訳のコレクションを格納します。|  
|[AttributePermissions 要素&#40;ASSL&#41;](attributepermissions-element-assl.md)|個々 の属性の権限のコレクションを格納[ロール](../objects/role-element-assl.md)の特定のディメンション上の要素を[キューブ](../objects/cube-element-assl.md)要素。|  
|[AttributeRelationships 要素&#40;ASSL&#41;](relationships-element-assl.md)|コレクションを格納[AttributeRelationship](../objects/attributerelationship-element-assl.md)属性の要素。|  
|[Attributes 要素&#40;ASSL&#41;](attributes-element-assl.md)|関連付けられているディメンションの属性のコレクションを格納します。|  
|[要素のブロック&#40;ASSL&#41;](blocks-element-assl.md)|バイナリ コンテンツを表すバイナリ データのブロックのコレクションを格納する[ClrAssemblyFile](../data-type/clrassemblyfile-data-type-assl.md)要素。|  
|[CalculationProperties 要素&#40;ASSL&#41;](calculationproperties-element-assl.md)|コレクションを格納[CalculationProperty](../objects/calculationproperty-element-assl.md)要素に関連付けられた、 [MdxScript](../objects/mdxscript-element-assl.md)要素。|  
|[Calculations 要素&#40;ASSL&#41;](calculations-element-assl.md)|コレクションを格納[PerspectiveCalculation](../data-type/perspectivecalculation-data-type-assl.md)要素に関連付けられた、[パースペクティブ](../objects/perspective-element-assl.md)要素。|  
|[CellPermissions 要素&#40;ASSL&#41;](cellpermissions-element-assl.md)|セルに関連付けられているアクセス許可のコレクションを格納[キューブ](../objects/cube-element-assl.md)要素。|  
|[ClassifiedColumns 要素&#40;ASSL&#41;](columns-element-assl.md)|により分類される関連列のコレクションを格納、 [ScalarMiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)要素。|  
|[Columns 要素&#40;ASSL&#41;](columns-element-assl.md)|親要素に関連付けられた列のコレクションを格納します。|  
|[要素をコマンド&#40;ASSL&#41;](commands-element-assl.md)|[MdxScript](../objects/mdxscript-element-assl.md) 要素に関連付けられた [Command](../objects/command-element-assl.md) 要素のコレクションを格納します。|  
|[CubePermissions 要素&#40;ASSL&#41;](cubepermissions-element-assl.md)|適用される権限のコレクションを格納する[キューブ](../objects/cube-element-assl.md)要素。|  
|[キューブ要素&#40;ASSL&#41;](cubes-element-assl.md)|コレクションを格納[キューブ](../objects/cube-element-assl.md)要素に関連付けられた、[データベース](../objects/database-element-assl.md)要素。|  
|[DatabasePermissions 要素&#40;ASSL&#41;](databasepermissions-element-assl.md)|コレクションを格納[DatabasePermission](../objects/databasepermission-element-assl.md)要素に関連付けられた、[データベース](../objects/database-element-assl.md)要素。|  
|[Databases 要素&#40;ASSL&#41;](databases-element-assl.md)|コレクションを格納[データベース](../objects/database-element-assl.md)要素に関連付けられた、 [Server](../objects/server-element-assl.md)要素。|  
|[DataSources 要素&#40;ASSL&#41;](datasources-element-assl.md)|コレクションを格納[DataSourcePermission](../objects/datasourcepermission-element-assl.md)要素に関連付けられた、 [DataSource](../data-type/datasource-data-type-assl.md)データ型。|  
|[DataSourcePermissions 要素&#40;ASSL&#41;](datasourcepermissions-element-assl.md)|コレクションを格納[DataSource](../objects/datasource-element-assl.md)要素に関連付けられた、[データベース](../objects/database-element-assl.md)要素。|  
|[DataSourceViews 要素&#40;ASSL&#41;](datasourceviews-element-assl.md)|コレクションを格納[DataSourceView](../objects/datasourceview-element-assl.md)要素に関連付けられた、[データベース](../objects/database-element-assl.md)要素。|  
|[DimensionPermissions 要素&#40;ASSL&#41;](dimensionpermissions-element-assl.md)|適用される権限のコレクションを格納する[ディメンション](../objects/dimension-element-assl.md)要素または[CubePermission](../objects/cubepermission-element-assl.md)要素。|  
|[要素の寸法&#40;ASSL&#41;](dimensions-element-assl.md)|親要素に関連付けられたディメンションのコレクションを格納します。|  
|[Events 要素&#40;ASSL&#41;](events-element-assl.md)|によってキャプチャされる Event 要素のコレクションを定義、[トレース](../objects/trace-element-assl.md)します。|  
|[要素をファイル&#40;ASSL&#41;](files-element-assl.md)|コレクションを格納[ファイル](../objects/file-element-assl.md)を構成する要素を[ClrAssembly](../data-type/assembly-data-type-assl.md)要素。|  
|[ForeignKeyColumns 要素&#40;ASSL&#41;](keycolumns-element-assl.md)|リレーショナル データ ソースの親テーブルへの結合を識別する列のコレクションを格納します。|  
|[Groups 要素&#40;ASSL&#41;](groups-element-assl.md)|属性にバインドされるメンバーのグループのコレクションを格納します。|  
|[Hierarchies 要素&#40;ASSL&#41;](hierarchies-element-assl.md)|コレクションを格納[階層](../objects/hierarchy-element-assl.md)親要素に関連付けられた要素。|  
|[IncrementalProcessingNotifications 要素&#40;ASSL&#41;](incrementalprocessingnotifications-element-assl.md)|コレクションを格納[IncrementalProcessingNotification](../objects/incrementalprocessingnotification-element-assl.md)要素に情報を提供する、 [ProactiveCaching](../objects/proactivecaching-element-assl.md)要素の進行状況を判断するために実行するクエリについて増分処理します。|  
|[KeyColumns 要素&#40;ASSL&#41;](keycolumns-element-assl.md)|コレクションを格納[KeyColumn](../objects/column-element-assl.md)親オブジェクトの要素の定義。|  
|[Kpis 要素&#40;ASSL&#41;](kpis-element-assl.md)|コレクションを格納[Kpi](../objects/kpi-element-assl.md)親要素に関連付けられた要素。|  
|[要素のレベル&#40;ASSL&#41;](levels-element-assl.md)|コレクションを格納[レベル](../objects/level-element-assl.md)内の要素を[階層](../objects/hierarchy-element-assl.md)要素。|  
|[MdxScripts 要素&#40;ASSL&#41;](mdxscripts-element-assl.md)|コレクションを格納[MdxScript](../objects/mdxscript-element-assl.md)要素に関連付けられた、[キューブ](../objects/cube-element-assl.md)要素。|  
|[MeasureGroups 要素&#40;ASSL&#41;](measuregroups-element-assl.md)|コレクションを格納[MeasureGroup](../objects/group-element-assl.md)親要素に関連付けられた要素。|  
|[要素の測定&#40;ASSL&#41;](measures-element-assl.md)|コレクションを格納[メジャー](../objects/measure-element-assl.md)親要素に関連付けられた要素。|  
|[Members 要素&#40;ASSL&#41;](members-element-assl.md)|コレクションを格納[メンバー](../objects/member-element-assl.md)の親要素の要素。|  
|[MiningModelPermissions 要素&#40;ASSL&#41;](miningmodelpermissions-element-assl.md)|アクセス許可のコレクションを格納する[MiningModel](../objects/miningmodel-element-assl.md)要素。|  
|[MiningModels 要素&#40;ASSL&#41;](miningmodels-element-assl.md)|コレクションを格納[MiningModel](../objects/miningmodel-element-assl.md)要素に関連付けられた、 [MiningStructure](../objects/miningstructure-element-assl.md)します。|  
|[MiningStructurePermissions 要素&#40;ASSL&#41;](miningstructurepermissions-element-assl.md)|アクセス許可のコレクションが含まれています、 [MiningStructure](../objects/miningstructure-element-assl.md)要素。|  
|[MiningStructures 要素&#40;ASSL&#41;](miningstructures-element-assl.md)|コレクションを格納[MiningStructure](../objects/miningstructure-element-assl.md)内の要素を[データベース](../objects/database-element-assl.md)要素。|  
|[ModelingFlags 要素&#40;ASSL&#41;](modelingflags-element-assl.md)|コレクションを格納[ModelingFlag](../objects/modelingflag-element-assl.md)内の列の要素を[MiningStructure](../objects/miningstructure-element-assl.md)または[MiningModel](../objects/miningmodel-element-assl.md)します。|  
|[NamingTemplateTranslations 要素&#40;ASSL&#41;](namingtemplatetranslations-element-assl.md)|ローカライズされた変換のコレクションを提供します、 [NamingTemplate](../properties/namingtemplate-element-assl.md)要素の親の[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)します。|  
|[要素をパーティション分割&#40;ASSL&#41;](partitions-element-assl.md)|コレクションを格納[パーティション](../objects/partition-element-assl.md)によって使用される要素を[MeasureGroup](../objects/group-element-assl.md)要素、またはの不一致を構成するパーティション バインドのコレクション[MeasureGroupBinding](../data-type/measuregroupbinding-data-type-out-of-line-assl.md)要素。|  
|[Perspectives 要素&#40;ASSL&#41;](perspectives-element-assl.md)|コレクションを格納[パースペクティブ](../objects/perspective-element-assl.md)要素に関連付けられた、[キューブ](../objects/cube-element-assl.md)要素。|  
|[QueryNotifications 要素&#40;ASSL&#41;](querynotifications-element-assl.md)|コレクションを格納[QueryNotification](../objects/querynotification-element-assl.md)要素に情報を提供する、 [ProactiveCaching](../objects/proactivecaching-element-assl.md)データ ソースが変更されているかどうかを判断するために実行するクエリについての要素。|  
|[ReportFormatParameters 要素&#40;ASSL&#41;](reportformatparameters-element-assl.md)|コレクションを格納[ReportFormatParameter](../objects/reportformatparameter-element-asl.md)の要素を[ReportAction](../data-type/action-data-type-assl.md)要素。|  
|[ReportParameters 要素&#40;ASSL&#41;](reportparameters-element-assl.md)|コレクションを格納[ReportParameter](../objects/reportparameter-element-assl.md)の要素を[ReportAction](../data-type/action-data-type-assl.md)要素。|  
|[Roles 要素&#40;ASSL&#41;](roles-element-assl.md)|親要素の下に定義された [Role](../objects/role-element-assl.md) 要素のコレクションを格納します。|  
|[ServerProperties 要素&#40;ASSL&#41;](serverproperties-element-assl.md)|コレクションを格納[ServerProperty](../objects/serverproperty-element-assl.md)要素に関連付けられた、 [Server](../objects/server-element-assl.md)要素。|  
|[TableNotifications 要素&#40;ASSL&#41;](tablenotifications-element-assl.md)|コレクションを格納[TableNotification](../objects/tablenotification-element-assl.md)要素の情報を提供する、 [ProactiveCaching](../objects/proactivecaching-element-assl.md)テーブルや変更されたデータ ソース ビューの要素。|  
|[要素をトレース&#40;ASSL&#41;](traces-element-assl.md)|[Server](../objects/server-element-assl.md) 要素に関連付けられた [Trace](../objects/trace-element-assl.md) 要素のコレクションを格納します。|  
|[Translations 要素&#40;ASSL&#41;](translations-element-assl.md)|コレクションを格納[翻訳](../objects/translation-element-assl.md)親要素に関連付けられた要素。|  
|[UnknownMemberTranslations 要素&#40;ASSL&#41;](unknownmembertranslations-element-assl.md)|キャプションに対する翻訳のコレクションを格納、 [UnknownMember](../properties/unknownmember-element-assl.md)ディメンションの要素。|  
  
## <a name="see-also"></a>参照  
 [Analysis Services スクリプト言語の XML 要素階層&#40;ASSL&#41;](../analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  
