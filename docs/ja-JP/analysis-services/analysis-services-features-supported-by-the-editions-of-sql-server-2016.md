---
title: Analysis Services の SQL Server 2016 の各エディションでサポートされている機能 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/29/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: multidimensional-tabular
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09d7be1-bd63-43f8-b91c-bf19166b4457
caps.latest.revision: 4
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 64dc653bb76225f00bed96da4b0e44ad49263807
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="analysis-services-features-supported-by-sql-server-editions"></a>SQL Server のエディションでサポートされている analysis Services 機能
[!INCLUDE[ssas-appliesto-sql2016-later](../includes/ssas-appliesto-sql2016-later.md)]

このトピックでは、SQL Server 2016 Analysis Services のさまざまなエディションでサポートされる機能の詳細を説明します。 Evaluation および Developer エディションでサポートされる機能、Enterprise edition を参照してください。

## <a name="analysis-services-servers"></a>Analysis Services (サーバー)
  
|機能|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|開発者|  
|-------------|----------------|--------------|---------|------------------------------------|------------------------|-------------|---------------|  
|スケーラブルな共有データベース|はい||||||はい|  
|データベースのバックアップ/復元、アタッチ/デタッチ|はい|[ユーザー アカウント制御]|||||はい|  
|データベースの同期|はい||||||はい|  
|Always On フェールオーバー クラスター インスタンス|はい<br /><br /> ノードの数はオペレーティング システムの最大容量|はい<br /><br /> 2 つのノードのサポート|||||はい<br /><br /> ノードの数はオペレーティング システムの最大容量|  
|プログラミング (AMO、ADOMD.Net、OLEDB、XML/A、ASSL、TMSL)|はい|[ユーザー アカウント制御]|||||はい|  
  
## <a name="tabular-models"></a>テーブル モデル 
  
|機能|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|開発者|  
|-------------|----------------|--------------|---------|------------------------------------|------------------------|-------------|---------------|  
|階層|はい|[ユーザー アカウント制御]|||||はい|  
|KPI|はい|[ユーザー アカウント制御]|||||はい|  
|パースペクティブ|はい||||||はい|  
|翻訳|はい|[ユーザー アカウント制御]|||||はい|  
|DAX 計算、DAX クエリ、MDX クエリ|はい|[ユーザー アカウント制御]|||||はい|  
|行レベルのセキュリティ|はい|[ユーザー アカウント制御]|||||はい|  
|複数パーティション|はい||||||はい|  
|インメモリ ストレージ モード|はい|[ユーザー アカウント制御]|||||はい|  
|DirectQuery ストレージ モード|はい||||||はい|  

## <a name="multidimensional-models"></a>多次元モデル 
  
|機能|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|開発者|  
|-------------|----------------|--------------|---------|------------------------------------|------------------------|-------------|---------------|  
|準加法メジャー|はい|不可 <sup>1</sup>|||||はい|  
|階層|はい|[ユーザー アカウント制御]|||||はい|  
|KPI|はい|[ユーザー アカウント制御]|||||はい|  
|パースペクティブ|はい||||||はい|  
|アクション|はい|[ユーザー アカウント制御]|||||はい|  
|勘定科目インテリジェンス|はい|[ユーザー アカウント制御]|||||はい|  
|タイム インテリジェンス|はい|[ユーザー アカウント制御]|||||はい|  
|カスタム ロールアップ|はい|[ユーザー アカウント制御]|||||はい|  
|キューブの書き戻し|はい|[ユーザー アカウント制御]|||||はい|  
|ディメンションの書き戻し|はい||||||はい|  
|セルの書き戻し|はい|[ユーザー アカウント制御]|||||はい|  
|ドリルスルー|はい|[ユーザー アカウント制御]|||||はい|  
|高度な階層の種類 (親子、不規則階層)|はい|[ユーザー アカウント制御]|||||はい|  
|高度なディメンション (参照ディメンション、多対多ディメンション)|はい|[ユーザー アカウント制御]|||||はい|  
|リンク メジャーとディメンション|はい|可  <sup>2</sup> |||||はい|  
|翻訳|はい|[ユーザー アカウント制御]|||||はい|  
|集計|はい|[ユーザー アカウント制御]|||||はい|  
|複数パーティション|はい|可 (3 つまで)|||||はい|  
|プロアクティブ キャッシュ|はい||||||はい|  
|カスタム アセンブリ (ストアド プロシージャ)|はい|[ユーザー アカウント制御]|||||はい|  
|MDX クエリおよびスクリプト|はい|[ユーザー アカウント制御]|||||はい|  
|DAX クエリ|はい|[ユーザー アカウント制御]|||||はい|  
|ロールベースのセキュリティ モデル|はい|[ユーザー アカウント制御]|||||はい|  
|ディメンションおよびセル レベルのセキュリティ|はい|[ユーザー アカウント制御]|||||はい|  
|スケーラブルな文字列ストレージ|はい|[ユーザー アカウント制御]|||||はい|  
|MOLAP、ROLAP、および HOLAP ストレージ モード|はい|[ユーザー アカウント制御]|||||はい|  
|バイナリおよび圧縮 XML の転送|はい|[ユーザー アカウント制御]|||||はい|  
|プッシュモード処理|はい||||||はい|  
|直接書き戻し|はい||||||はい|  
|メジャー式|はい||||||はい|  
  
 <sup>1</sup> LastChild 準加法メジャーは Standard Edition でサポートされますが、他の準加法メジャー (None、FirstChild、FirstNonEmpty、LastNonEmpty、AverageOfChildren、ByAccount など) はサポートされません。 加法メジャー (Sum、Count、Min、Max など) や非加法メジャー (DistinctCount) はすべてのエディションでサポートされます。  
  <sup>2</sup>リンクのメジャーとディメンションが、同じデータベース内の他のデータベースまたはインスタンスからではなく standard edition をサポートしています。
  
## <a name="power-pivot-for-sharepoint"></a>Power Pivot for SharePoint  
  
|機能|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|開発者|  
|-------------|----------------|--------------|---------|------------------------------------|------------------------|-------------|---------------|  
|共有サービス アーキテクチャに基づく SharePoint ファーム統合|はい||||||はい|  
|使用状況レポート|はい||||||はい|  
|状態の監視のルール|はい||||||はい|  
|Power Pivot ギャラリー|はい||||||はい|  
|Power Pivot データ更新|はい||||||はい|  
|Power Pivot データ フィード|はい||||||はい|  
  
## <a name="data-mining"></a>データ マイニング  
  
|機能名|Enterprise|Standard|Web|Express with Advanced Services|Express with Tools|Express|開発者|  
|------------------|----------------|--------------|---------|------------------------------------|------------------------|-------------|---------------|  
|標準アルゴリズム|はい|[ユーザー アカウント制御]|||||はい|  
|データ マイニング ツール (ウィザード、エディター、クエリ ビルダー)|はい|[ユーザー アカウント制御]|||||はい|  
|相互検証|はい||||||はい|  
|マイニング構造データのフィルター選択したサブセットのモデル|はい||||||はい|  
|時系列: ARTXP 法と ARIMA 法のカスタムな組み合わせ|はい||||||はい|  
|時系列: 新しいデータでの予測|はい||||||はい|  
|無制限の同時 DM クエリ|はい||||||はい|  
|データ マイニング アルゴリズムの構成とチューニングの拡張オプション|はい||||||はい|  
|プラグイン アルゴリズムのサポート|はい||||||はい|  
|並列モデル処理|はい||||||はい|  
|時系列: 系列のクロス予測|はい||||||はい|  
|アソシエーション ルールの無制限の属性|はい||||||はい|  
|シーケンス予測|はい||||||はい|  
|複数の Naïve Bayes の予測ターゲット、ニューラル ネットワーク、およびロジスティック回帰|はい||||||はい|  
  
 ## <a name="see-also"></a>参照  
 [SQL Server 2016 の製品仕様](http://msdn.microsoft.com/library/6445fd53-6844-4170-a86b-7fe76a9f64cb)   
 [SQL Server をインストールする](../database-engine/install-windows/installation-for-sql-server-2016.md)  

