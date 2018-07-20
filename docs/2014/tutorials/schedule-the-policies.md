---
title: ポリシーのスケジュール設定 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
caps.latest.revision: 5
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: c328073f25c27ff05b8b6edbd79a56ad1fda85ab
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37315132"
---
# <a name="schedule-the-policies"></a>ポリシーのスケジュール設定
  ここでは、前の作業でインポートしたベスト プラクティス ポリシーをスケジュールします。  
  
### <a name="to-schedule-the-best-practices-policies"></a>ベスト プラクティス ポリシーをスケジュールするには  
  
1.  オブジェクト エクスプ ローラーで、**管理**、展開**ポリシーの管理**、展開**ポリシー**ベスト プラクティス ポリシーを右クリックし、クリックして**プロパティ**します。  
  
    > [!NOTE]  
    >  代わりに、ベスト プラクティスに関連付けられているポリシーを簡単に確認し、最高の並べ替えにプラクティスのカテゴリを展開し、**管理**、展開**ポリシーの管理**をクリックして**ポリシー**します。 **[表示]** メニューの **[オブジェクト エクスプローラーの詳細]** をクリックします。 **オブジェクト エクスプ ローラーの詳細**ウィンドウで、をクリックして、**カテゴリ**見出しをカテゴリで、ポリシーを並べ替えます。 ベスト プラクティス ポリシーがあるプレフィックス**マイクロソフトのベスト プラクティス**します。 ポリシーを構成し、をクリックするを右クリックして**プロパティ**します。  
  
2.  **全般**のページ、**ポリシーを開く**] ダイアログ ボックスで、**評価モード**一覧で、[**スケジュールで**します。  
  
3.  横に、**スケジュール**ボックスで、**選択**に既存のスケジュールを指定するかクリックして**新規**新しいスケジュールを作成します。  
  
4.  スケジュールを構成した後は、選択、**有効**スケジュールされたポリシーを有効にするページの上部にあるチェック ボックスをオンします。  
  
5.  スケジュールするポリシーごとに、手順 1. ～ 4. を繰り返します。  
  
    > [!NOTE]  
    >  スケジュールされたポリシーが実行された後に評価結果を表示するには、対象インスタンスのポリシー履歴ログを開きます。 ログを開くを右クリックして**ポリシーの管理**、 をクリックし、**履歴の表示**します。  
  
## <a name="summary"></a>まとめ  
 スケジュールしたポリシーを [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] の単一インスタンス上で実行するよう構成しました。 スケジュールしたポリシーを複数のインスタンスに配置するには、このチュートリアルの次の作業に進みます。  
  
## <a name="next-steps"></a>次の手順  
 [スケジュールされたポリシーの複数インスタンスへの配置](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  