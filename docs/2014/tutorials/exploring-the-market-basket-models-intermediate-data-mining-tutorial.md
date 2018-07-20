---
title: マーケット バスケット モデル (中級者向けデータ マイニング チュートリアル) の検証 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: da1c9cb7-6c32-4b9b-96ec-ecea772aeb77
caps.latest.revision: 33
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: c81bba0a055f812afddb56eac604111796f464d7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37179139"
---
# <a name="exploring-the-market-basket-models-intermediate-data-mining-tutorial"></a>マーケット バスケット モデルの検証 (中級者向けデータ マイニング チュートリアル)
  これでビルドした、`Association`モデルでは、利用できることを使用して、[!INCLUDE[msCoName](../includes/msconame-md.md)]アソシエーション ビューアーで、**マイニング モデル ビューアー**データ マイニング デザイナーのタブ。 このチュートリアルでは、ビューアーを使用してアイテム間の関係を検証する方法を、順を追って学習します。 ビューアーを使用すると、どの製品とどの製品がよく一緒に表示されるかが一目でわかるほか、新たなパターンの概観も可能です。  
  
 [!INCLUDE[msCoName](../includes/msconame-md.md)]アソシエーション ビューアーには、3 つのタブが含まれています:**ルール**、**アイテム セット**、および**依存関係ネットワーク**します。 これらのタブにはデータがそれぞれ少しずつ異なる形で表示されるため、モデルを検証する際には、異なるペインの間を何度も切り替えながら調査を進めるのが一般的です。  
  
-   [依存関係ネットワーク タブ](#bkmk_DepNet)  
  
-   [アイテム セット タブ](#bkmk_Itemsets)  
  
-   [[規則] タブ](#bkmk_Rules)  
  
-   [汎用コンテンツ ツリー ビューアー](#bkmk_ContentViewer)  
  
 このチュートリアルで開始、**依存関係ネットワーク**タブをクリックしを使用して、**ルール** タブと**アイテム セット**関係の理解を深めるには、タブビューアーで明らかになりました。 また、使用、 **Microsoft 汎用コンテンツ ツリー ビューアー**を個々 のルールやアイテム セットの詳細な統計情報を取得します。  
  
##  <a name="bkmk_DepNet"></a> 依存関係ネットワーク タブ  
 **依存関係ネットワーク** タブで、モデルのさまざまなアイテムの相互作用を調査することができます。 ビューアーの各ノードはアイテムを表し、アイテム間を結ぶ線はルールを表します。 ノードを選択すると、選択したアイテムが他のどのノードによって予測されるか、また現在のアイテムがどのアイテムを予測するかがわかります。 アイテム間に双方向の関係がある (つまり同一トランザクション内に発生する可能性が高い) 場合もあります。 タブの下部にある色の凡例を参照すると、関係の方向を確認できます。  
  
 2 つのアイテムを結ぶ線は、それらのアイテムが同じトランザクションに含まれる可能性が高いことを示しています。 つまり、顧客がそれらのアイテムをまとめて購入する可能性が高いということになります。 スライダーはルールの確率に関連付けられています。 スライダーを下方向に移動すると、緊密な関係 (確率の高いルール) のみが表示されます。  
  
 依存関係ネットワークのグラフには、"A->B" として論理的に表現できる 1 対 1 のルールが表示されます。これは、製品 A が購入された場合は製品 B も購入される可能性が高いことを表します。 このグラフでは、AB->C のようなルールを表示することはできません。 すべてのルールが表示される位置までスライダーを動かしてもグラフに線が表示されない場合は、アルゴリズム パラメーターの条件を満たす 1 対 1 のルールが存在しないことになります。  
  
 属性名の最初の数文字を入力してノードを名前で検索することもできます。 詳細については、「[[ノードの検索] ダイアログ ボックス (マイニング モデル ビューアー)](../../2014/analysis-services/find-node-dialog-box-mining-model-viewer.md)」を参照してください。  
  
#### <a name="to-open-the-association-mode-in-the-microsoft-assocaition-rules-viewer"></a>Microsoft アソシエーション ルール ビューアーで Association モデルを開くには  
  
1.  **ソリューション エクスプ ローラー**、Association 構造をダブルクリックします。  
  
2.  データ マイニング デザイナーで、 **[マイニング モデル ビューアー]** タブをクリックします。  
  
3.  内のマイニング モデルの一覧からアソシエーションを選択して、**マイニング モデル**ドロップダウン リスト。  
  
#### <a name="to-navigate-the-dependency-graph-and-locate-specific-nodes"></a>依存関係のグラフを操作して特定のノードを見つけるには  
  
1.  **マイニング モデル ビューアー**タブをクリックし、**依存関係ネットワーク**タブ。  
  
2.  をクリックして**ズームイン**数回、まで、各ノードのラベルを簡単に確認できます。  
  
     既定では、すべてのノードが見えるようにグラフが表示されます。 複雑なモデルでは、ノードの数が多いためにそれぞれのノードが非常に小さくなることがあります。  
  
3.  をクリックして、 **+** ビューアーの右下隅にサインインし、グラフの周りをパンするマウス ボタンを押したままです。  
  
4.  ビューアーの左側にあるスライダーを移動することから、下にドラッグ**すべてのリンク**(既定値) のスライダー コントロールの下部にします。  
  
5.  グラフが更新されて、最も強いアソシエーション (Touring Tire と Touring Tire Tube の間のアソシエーション) のみが表示されます。  
  
6.  というラベルの付いたノードをクリックします。 **Touring Tire Tube = Existing**します。  
  
     グラフが更新されて、このアイテムとの間に強い関連があるアイテムのみが強調表示されます。 2 つのアイテム間の矢印の向きに注目してください。  
  
7.  ビューアーの左側で、スライダーをドラッグして一番下から真ん中あたりまで戻します。  
  
     2 つのアイテムを結ぶ矢印の変化に注目してください。  
  
8.  選択 **[属性名のみ**依存関係ネットワーク] ウィンドウの上部にあるドロップダウン リストから。  
  
     グラフのテキスト ラベルが更新されて、モデル名のみが表示されます。  
  
 [ページのトップへ](#bkmk_DepNet)  
  
##  <a name="bkmk_Itemsets"></a> アイテム セット タブ  
 次に、Touring Tire と Touring Tire Tube という 2 つの製品についてモデルによって生成された、ルールとアイテムセットの詳細を調べます。 **アイテム セット** タブには、アイテム セットに関連する情報の 3 つの重要な情報が表示される[!INCLUDE[msCoName](../includes/msconame-md.md)]アソシエーション アルゴリズムを検出します。  
  
-   **サポート:** アイテム セットが発生したトランザクションの数。  
  
-   **サイズ:** アイテム セット内の項目の数。  
  
-   **項目:** 各アイテム セットに含まれる項目の一覧。  
  
 アルゴリズム パラメーターの設定方法によっては、多数のアイテムセットが生成される場合があります。 ビューアーに返される各アイテムセットは、アイテムが販売されたトランザクションを表します。 上部にあるコントロールを使用して、**アイテム セット** タブで、指定された最小のサポートとアイテム セット サイズが含まれているアイテム セットのみを表示するビューアーをフィルター処理できます。  
  
 別のマイニング モデルを使用していてアイテムセットが表示されない場合、それは、アルゴリズム パラメーターの条件を満たすアイテムセットが存在しないからです。 そのような場合は、サポートの値がもっと低いアイテムセットが許可されるようにアルゴリズム パラメーターを変更できます。  
  
#### <a name="to-filter-the-itemsets-that-are-shown-in-the-viewer-by-name"></a>ビューアーに表示されるアイテムセットを名前で絞り込むには  
  
1.  をクリックして、**アイテム セット**ビューアーのタブ。  
  
2.  **アイテム セットのフィルター**ボックスに「 `Touring Tire`、[] ボックス外側をクリックします。  
  
     その文字列を含むすべてのアイテムが返されます。  
  
3.  **表示**一覧で、 **属性名のみ**します。  
  
4.  選択、**長い名前を表示**チェック ボックスをオンします。  
  
     アイテムセットの一覧が更新されて、"Touring Tire" という文字列を含むアイテムセットのみが表示されます。 アイテムセットの長い名前には、各アイテムの属性と値を含むテーブルの名前が含まれます。  
  
5.  クリア、**長い名前を表示**チェック ボックスをオンします。  
  
     アイテムセットの一覧が更新されて、短い名前のみが表示されます。  
  
 内の値、**サポート**列は、各アイテム セットのトランザクションの数を指定します。 アイテムセットのトランザクションとは、アイテムセット内のすべてのアイテムを含む購入のことです。  
  
 既定では、アイテムセットはサポートの降順でビューアーに表示されます。 列のヘッダーをクリックすると、アイテムセットを別の列 (アイテムセットのサイズや名前など) で並べ替えることができます。 アイテムセットに含まれる個々のトランザクションの詳細に関心がある場合は、アイテムセットから個々のケースにドリルスルーすることもできます。 ドリルスルーの結果には、モデルでは使用されなかった顧客の収入レベルと顧客 ID の構造列が含まれます。  
  
#### <a name="to-view-details-for-an-itemset"></a>アイテムセットの詳細を表示するには  
  
1.  アイテム セットの一覧でクリックして、**アイテム セット**列見出しを名前で並べ替えます。  
  
2.  項目を検索`Touring Tire`(2 番目のアイテムを含まない)。  
  
3.  項目を右クリックして`Touring Tire`を選択します**ドリル スルー**、し、**モデルおよび構造列**します。  
  
     **ドリル スルー**  ダイアログ ボックスには、このアイテム セットのサポートとして使用される個別のトランザクションが表示されます。  
  
4.  入れ子になったテーブル vAssocSeqLineItems を展開して、トランザクションの実際の購入の一覧を表示します。  
  
#### <a name="to-filter-itemsets-by-support-or-size"></a>アイテムセットをサポートまたはサイズで絞り込むには  
  
1.  可能性のある任意のテキストをクリア、**アイテム セットのフィルター**ボックス。 テキスト フィルターと数値フィルターを同時に使用することはできません。  
  
2.  **最小のサポート**ボックスに、100 を入力し、ビューアーの背景をクリックします。  
  
     アイテムセットの一覧が更新されて、サポートが 100 以上のアイテムセットのみが表示されます。  
  
 [ページのトップへ](#bkmk_DepNet)  
  
##  <a name="bkmk_Rules"></a> [規則] タブ  
 **ルール** タブには、アルゴリズムの検索ルールに関連する次の情報が表示されます。  
  
-   **確率:** 、*尤度*ルールの右辺のアイテムの左側にある項目を指定した確率として定義されているのです。  
  
-   **重要:** ルールの有用性の測定します。 この値が大きいほどルールの有効性が高くなります。  
  
     ルールの有効性を判断するための基準として重要度が用意されているのは、確率だけでは誤った判断を招く可能性があるためです。 たとえば、プロモーションの一環として各顧客のカートに自動的に水筒が追加される場合は、すべてのトランザクションに水筒が含まれるため、水筒の確率を 1 として予測するルールがモデルによって作成されます。 このルールは、確率に基づく限りはきわめて正確ですが、有用な情報にはなりません。  
  
-   **ルール:** ルールの定義。 マーケット バスケット モデルのルールでは、アイテムの特定の組み合わせを記述します。  
  
 各ルールを使用すると、他のアイテムが存在するかどうかに基づいて、あるアイテムがトランザクションに含まれるかどうかを予測することができます。 同じように、**アイテム セット** タブで、最も関心のあるルールのみが表示されるようにルールをフィルター処理することができます。 使用しているマイニング モデルにルールが 1 つもない場合は、アルゴリズム パラメーターを変更して、ルールの確率のしきい値を下げることができます。  
  
#### <a name="to-see-only-rules-that-include-the-mountain-200-bicycle"></a>Mountain-200 という自転車を含むルールのみを表示するには  
  
1.  **マイニング モデル ビューアー**タブをクリックし、**ルール**タブ。  
  
2.  **フィルタの規則**ボックスに、入力`Mountain-200`します。  
  
     クリア、**長い名前を表示**チェック ボックスをオンします。  
  
3.  **表示**一覧で、 **属性名のみ**します。  
  
     ビューアーは、単語を含むルールのみを表示し、"`Mountain-200`"。 ルールの確率は、どの程度にされるときにだれかが購入を指示する`Mountain-200`自転車、そのユーザーは他の製品を購入してもします。  
  
 ルールは確率の降順で表示されますが、列見出しをクリックして並べ替え順を変更できます。 特定のルールの詳細に関心がある場合は、ドリルスルーを使用して、そのルールをサポートするケースを表示することもできます。  
  
#### <a name="to-view-cases-that-support-a-particular-rule"></a>特定のルールをサポートするケースを表示するには  
  
1.  **ルール** タブで、表示するルールを右クリックします。  
  
2.  選択**ドリル スルー**、し、**モデル列のみ**、または**モデルおよび構造列**します。  
  
     **ドリル スルー**  ダイアログ ボックス、ペインの上部とルールのサポート データとして使用されていたすべてのケースの一覧にルールの概要を提供します。  
  
 [ページのトップへ](#bkmk_DepNet)  
  
##  <a name="bkmk_ContentViewer"></a> 汎用コンテンツ ツリー ビューアー  
 このビューアーは、アルゴリズムやモデルの種類に関係なく、すべてのモデルで使用できます。 **Microsoft 汎用コンテンツ ツリー ビューアー**から利用できますが、**ビューアー**ドロップダウン リスト。  
  
 コンテンツ ツリーは、マイニング モデルを一連のノードで表したものです。各ノードは、データのサブセットに関する学習済みの知識を表します。 ノードには、いくつかの特徴が共通するパターン、一連のルール、クラスター、または日付範囲の定義を含めることができます。 ノードの正確な内容はアルゴリズムや予測可能な属性の種類に応じて変わりますが、内容の全体的な表示は同じです。 各ノードを展開して、より詳細なレベルで表示したり、任意のノードの内容をクリップボードにコピーしたりできます。  
  
#### <a name="to-view-details-about-the-rule-by-using-the-content-viewer"></a>コンテンツ ビューアーを使用してルールの詳細を表示するには  
  
1.  **マイニング モデル ビューアー** ] タブで [ **Microsoft 汎用コンテンツ ツリー ビューアー**から、**ビューアー**一覧。  
  
2.  [ノードのキャプション] ペインで、一覧を一番下までスクロールして最後のノードをクリックします。  
  
     ビューアーでは、最初にアイテムセット、次にルールが表示されますが、グループ化はされていません。 特定のノードを見つけるには、コンテンツ クエリを作成するのが最も簡単です。 詳細については、「 [結合モデルのクエリ例](../../2014/analysis-services/data-mining/association-model-query-examples.md)」を参照してください。  
  
3.  [ノードの詳細] ペインで、NODE_TYPE と NODE_DESCRIPTION の値を確認します。  
  
     ルールのノードの種類は 8 で、アイテムセットのノードの種類は 7 です。 ルールの NODE_DESCRIPTION の値は、ルールを構成する条件を表します。 アイテムセットの NODE_DESCRIPTION の値は、アイテムセットに含まれるアイテムを表します。  
  
 コンテンツ クエリを作成してルールの詳細な統計情報を取得することもできます。 マイニング モデルの内容とその解釈方法の詳細については、次を参照してください。[アソシエーション モデルのマイニング モデル コンテンツ&#40;Analysis Services - データ マイニング&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md)します。  
  
 [ページのトップへ](#bkmk_DepNet)  
  
## <a name="next-task-in-lesson"></a>このレッスンの次の作業  
 [マイニング モデルの入れ子になったテーブルをフィルター処理&#40;中級者向けデータ マイニング チュートリアル&#41;](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>参照  
 [レッスン 3: マーケット バスケット シナリオの作成&#40;中級者向けデータ マイニング チュートリアル&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)   
 [レッスン 4: シーケンス クラスター シナリオの作成&#40;中級者向けデータ マイニング チュートリアル&#41;](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)   
 [Microsoft アソシエーション アルゴリズム](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md)   
 [Microsoft アソシエーション アルゴリズム テクニカル リファレンス](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md)  
  
  