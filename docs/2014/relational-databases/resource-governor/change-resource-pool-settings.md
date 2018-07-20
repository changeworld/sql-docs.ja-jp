---
title: リソース プールの設定の変更 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
caps.latest.revision: 14
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 7c13aa402d1837e9fcb220481edefc75d8d301c1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37214952"
---
# <a name="change-resource-pool-settings"></a>リソース プールの設定の変更
  リソース プールの設定を変更するには、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] または [!INCLUDE[tsql](../../includes/tsql-md.md)]を使用します。  
  
-   **Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)  
  
-   **リソース プールの設定変更に使用するもの:**  [SQL Server Management Studio](#ChgRPProp)、 [Transact-SQL](#ChgRPTSQL)  
  
##  <a name="BeforeYouBegin"></a> 作業を開始する準備  
  
###  <a name="LimitationsRestrictions"></a> 制限事項と制約事項  
 CPU の割合の最大値は、CPU の割合の最小値以上にする必要があります。 メモリの割合の最大値は、メモリの割合の最小値以上にする必要があります。  
  
 すべてのリソース プールの CPU の割合の最小値の合計およびメモリの割合の最小値の合計が、それぞれ 100 を超えないようにしてください。  
  
###  <a name="Permissions"></a> Permissions  
 リソース プールの設定を変更するには、CONTROL SERVER 権限が必要です。  
  
##  <a name="ChgRPProp"></a> SQL Server Management Studio を使用してリソース プールの設定を変更する  
 **リソース プールの設定を変更するには - [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
1.  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]でオブジェクト エクスプローラーを開き、 **[管理]** ノードを **[リソース プール]** ノードまで再帰的に展開します。  
  
2.  変更するリソース プールを右クリックし、 **[プロパティ]** をクリックします。  
  
3.  **[リソース ガバナーのプロパティ]** ページで、自動的に **[リソース プール]** グリッドの対象リソース プールの行が選択されない場合は、その行を選択します。  
  
4.  変更する行のセルをクリックまたはダブルクリックし、新しい値を入力します。  
  
5.  変更を保存するには、 **[OK]** をクリックします。  
  
##  <a name="ChgRPTSQL"></a> Transact-SQL を使用してリソース プールの設定を変更する  
 **リソース プールの設定を変更するには - [!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
1.  変更するプロパティ値を指定する `ALTER RESOURCE POOL` ステートメントを実行します。  
  
2.  **ALTER RESOURCE GOVERNOR RECONFIGURE** ステートメントを実行します。  
  
### <a name="example-transact-sql"></a>例 (Transact-SQL)  
 次の例では、 `poolAdhoc`という名前のリソース プールの CPU の割合の最大値を変更します。  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [[リソース ガバナー]](resource-governor.md)   
 [リソース ガバナーの有効化](enable-resource-governor.md)   
 [リソース プールの作成](create-a-resource-pool.md)   
 [リソース プールの削除](delete-a-resource-pool.md)   
 [リソース ガバナー ワークロード グループ](resource-governor-workload-group.md)   
 [リソース ガバナーの分類子関数](resource-governor-classifier-function.md)   
 [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql)   
 [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  