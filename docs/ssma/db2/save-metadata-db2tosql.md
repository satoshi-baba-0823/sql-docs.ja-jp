---
title: "メタデータ (DB2ToSQL) 保存 |Microsoft ドキュメント"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 9a76083e-4902-449e-b125-7e9259fc37f7
caps.latest.revision: 3
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: f0b6735caf1918cf7473c66e56fc6fd6b808c8d9
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="save-metadata-db2tosql"></a>メタデータ (DB2ToSQL) の保存します。
**メタデータの保存** ダイアログ ボックスでは、SSMA プロジェクトにメタデータを保存する前にロードするように求められます。 オフラインで使用したり、テクニカル サポート担当者など、他の人に送信できる完全なプロジェクト ファイルがあるこのできます。  
  
アクセスする、**メタデータの保存**ダイアログ ボックスで、プロジェクトを保存します。 すべてのメタデータが不足している場合は、SSMA が表示されます、**メタデータの保存** ダイアログ ボックス。  
  
## <a name="options"></a>オプション  
**名前**  
プロジェクト内の各データベースの名前。  
  
**[状態]**  
SSMA プロジェクトにメタデータが読み込まれる場合、またはメタデータが不足している場合を示します。  
  
SSMA は、必要に応じて、プロジェクトにメタデータを読み込みます。 参照メタデータのスキーマを変換すると、メタデータが自動的に読み込まれます。  
  
**[すべて選択] します。**  
一覧内のすべてのデータベースを選択します。  
  
**Clear**  
メタデータの欠落しているすべてのデータベースのチェック ボックスをクリアします。 メタデータが読み込まれている場合は、チェック ボックスをオフすることはできません。  
  
**[保存]**  
メタデータが欠落している選択したデータベースのメタデータを読み込み、プロジェクトを保存します。  
  
**キャンセル**  
保存を取り消す操作します。 メタデータの欠落がプロジェクトに読み込まれていません。  
  
