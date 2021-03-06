---
title: 'タスク 8: Excel で State エンティティの新しい値の追加 |Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 04fe6fa0a9036ca3835fd4bc0afcb0e35854fd85
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48222162"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a>タスク 8: Excel で State エンティティに新しい値を追加する
  ここでは、Excel で State エンティティの値を追加し、MDS サーバーに変更をパブリッシュします。  
  
1.  追加、**作業シート**下部にある新しいタブをクリックして Excel でします。  
  
     ![Excel - 新しいワークシートのタブ](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - 新しいワークシートのタブ")  
  
2.  **Excel**、] をクリックして、**マスター データ**メニューで、タブをクリックして **[エクスプ ローラーの**リボン上。  
  
3.  **マスター データ エクスプ ローラー**、 **Suppliers**の**モデル**します。 2 つのエンティティを表示する必要があります: **Supplier**と**状態**エンティティの一覧にします。  
  
4.  ダブルクリック**状態**一覧にします。 すべてのメンバー、**状態**がワークシートに MDS からのエンティティを表示する必要があります。  
  
5.  ここで、次の値の末尾に行を追加:**ノースカロライナ**の**名前**と**NC**の**コード**します。 コードの色分けで、新しい/更新済みレコードと他のレコードを区別します。  
  
     ![Excel - 州にノース カロライナ状態を追加](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - 州にノース カロライナ状態を追加")  
  
6.  クリックして**発行**を MDS に変更を発行するには、リボンです。  
  
     ![Excel - [マスター データ] タブのボタンの発行](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - [マスター データ] タブのボタンの発行")  
  
7.  **パブリッシュと注釈設定** ダイアログ ボックスで、注意、**同じ注釈を使用して、すべての変更の**が選択されています。 すべての変更についての単一の注釈をここに入力できます。  
  
8.  選択**変更を確認し、注釈を個別に提供**(この場合は、1 つだけ) 内の各変更の注釈を指定することです。  
  
     ![Excel - [パブリッシュし、注釈設定] ダイアログ ボックス](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - [パブリッシュし、注釈設定] ダイアログ ボックス")  
  
9. クリックして**発行**MDS にデータを発行します。  
  
10. 注意**色分け**を持つ行の**ノースカロライナ**として、**状態**は他のレコードと同じようになりました。  
  
11. **省略可能:** に新しいメンバー (NC) が追加されたことを確認して、**状態**エンティティを使用して、**エクスプ ローラー**で**マスター データ マネージャー**します。  
  
12. Excel を右クリックし、**状態** をクリックして、一番下にあるワークシート**削除**ワークシートを削除します。 ワークシートを削除しても MDS サーバーからデータは削除されません。  
  
## <a name="next-step"></a>次の手順  
 [タスク 9: マスター データ マネージャーを使用して派生階層を作成する](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
