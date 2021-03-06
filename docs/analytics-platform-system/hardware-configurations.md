---
title: ハードウェアの構成 - Analytics Platform System |Microsoft ドキュメント
description: Analytics Platform System (APS) アプライアンス ハードウェアは、設計拡張性の高いユニット ビジネス ニーズに合わせて適切な処理と記憶域容量を購入するようにします。 アプライアンスは、データの単位からペタバイト単位以上 6 数テラバイトから Parallel Data Warehouse の記憶域を拡張できます。
author: mzaman1
manager: craigg
ms.prod: sql
ms.technology: data-warehouse
ms.topic: conceptual
ms.date: 04/17/2018
ms.author: murshedz
ms.reviewer: martinle
ms.openlocfilehash: 5677298e1924959c83cd95b86845e37eab7340e9
ms.sourcegitcommit: 056ce753c2d6b85cd78be4fc6a29c2b4daaaf26c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2018
ms.locfileid: "31544724"
---
# <a name="hardware-configurations---analytics-platform-system"></a>Analytics Platform System のハードウェア構成
Analytics Platform System (APS) ハードウェアは、設計拡張性の高いユニット ビジネス ニーズに合わせて適切な処理と記憶域容量を購入するようにします。 アプライアンスは、記憶域の SQL Server 並列データ Wareouse (PDW) 数テラバイトからを超える 6 ペタバイト級のデータをスケーリングします。  
  
## <a name="contents"></a>目次  
  
-   [1 つのラック構成](#section1)  
  
-   [複数のラック構成](#section2)  

  
## <a name="section1"></a>1 つのラック構成  
アプライアンス内の最初のラックには、PDW の実行に必要なコンポーネントが含まれています。 最小アプライアンス構成は、ラック、ネットワーク、および基本スケール単位です。 これらの図は、アプライアンスの最初のラックを構成できることを方法を示します。 2 ノードと 9 コンピューティング ノードのハードウェアの製造元によって、最初のラックにことができます。  
  
### <a name="first-rack-configurations---dell"></a>DELL の構成をまずラックします。  
DELL アプライアンスの最小構成には、3 つのコンピューティング ノードがあります。 9 のコンピューティング ノードの合計については、最初のラックに最大 2 つのデータのスケール ユニットを追加できます。  
  
![Dell 最初のラック構成](media/first-rack-configurations-dell.png "Dell 最初のラック構成")  
  
### <a name="first-rack-configurations---hpe"></a>最初の構成 - HPE をラックします。  
HPE アプライアンスの最小構成には、2 つのコンピューティング ノードがあります。 8 のコンピューティング ノードの合計については、最初のラックには、最大 3 つのデータのスケール ユニットを追加できます。  
  
![HPE が HPE の構成をまずラック](media/first-rack-configurations-hpe.png "HPE が最初に構成をラック")  
  
## <a name="section2"></a>複数のラック構成  
PDW に容量を追加するには、ネットワー キング、必要に応じて、適切な能力を提供する、追加のラック & ネットワーク コンポーネントと共にデータのスケール ユニットを追加して、インフラストラクチャをラックすることができます。 各追加ラック & ネットワークには、パッシブ ホストが必要です。  
  
各ハードウェア ベンダーには、アプライアンスの容量を指定できますを追加するデータのスケール ユニットの数を指定します。 少なくとも、20% へのアップグレードのパフォーマンスを表示するための十分なデータのスケール ユニットを追加することをお勧めします。 たとえば、1 つのデータのスケールを追加する 20 のデータのスケール ユニットが既にいるアプライアンスに単位可能性がありますごくわずかでありのパフォーマンスが向上。 純利益は、コストと労力の価値があるでしょう。  
  
### <a name="scale-out-example---hpe"></a>スケール アウト HPE の使用例  
この図では、20 のコンピューティング ノードを含む 3 HP ラック マウント型アプライアンスを示します。  
  
![20 の計算ノードを伴う HPE アプライアンス](media/scale-out-hpe.png "20 の計算ノードを伴う HPE アプライアンス")  
  
### <a name="scale-out-example--dell-quanta"></a>スケール アウトの例 – DELL、クォンタム  
この図では、21 のコンピューティング ノードを含む 3 つのラック DELL または Quanta アプライアンスを示します。  
  
![21 の計算ノードを伴う Dell アプライアンス](media/scale-out-dell.png "21 の計算ノードを伴う Dell アプライアンス")  
 
