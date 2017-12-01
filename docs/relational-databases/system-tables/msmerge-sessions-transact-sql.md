---
title: "MSmerge_sessions (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- MSmerge_sessions
- MSmerge_sessions_TSQL
dev_langs: TSQL
helpviewer_keywords: MSmerge_sessions system table
ms.assetid: 09ada8fc-c148-4379-9524-7826b1b0216c
caps.latest.revision: "26"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a081578000d831f85f00d8de2da725e6d078e5a8
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="msmergesessions-transact-sql"></a>MSmerge_sessions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSmerge_sessions**の以前のマージ エージェント ジョブ セッションの結果の履歴行を保持します。 このテーブルには、マージ エージェントが実行されるたびに、新しい行が追加されます。 このテーブルは、ディストリビューション データベースに保存されます。  
  
|列名|データ型|Description|  
|-----------------|---------------|-----------------|  
|**session_id**|**int**|マージ エージェント ジョブ セッションの ID。|  
|**agent_id**|**int**|マージ エージェントの ID です。|  
|**start_time**|**datetime**|ジョブの実行開始時刻。|  
|**end_time**|**datetime**|ジョブの実行完了時刻。|  
|**duration**|**int**|秒単位で、このジョブ セッションの累積時間。|  
|**delivery_time**|**int**|変更のバッチを適用するために要する秒数。|  
|**upload_time**|**int**|変更をパブリッシャーにアップロードするために要する秒数。|  
|**download_time**|**int**|変更をサブスクライバーにダウンロードするために要する秒数。|  
|**delivery_rate**|**float**|1 秒あたりの配信コマンド数の平均です。|  
|**time_remaining**|**int**|アクティブなセッション内の残り秒数の推定。|  
|**percent_complete**|**decimal**|アクティブなセッションで既に配信された全変更の推定パーセンテージ。|  
|**upload_inserts**|**int**|パブリッシャー側で適用される挿入の数です。|  
|**upload_updates**|**int**|パブリッシャーで適用された更新数。|  
|**upload_deletes**|**int**|パブリッシャー側で適用される削除の数です。|  
|**upload_conflicts**|**int**|パブリッシャー側で変更を適用する間に発生した競合の数です。|  
|**upload_conflicts_resolved**|**int**|パブリッシャーで変更を適用中に発生した競合のうち、既に解決された競合の数。|  
|**upload_rows_retried**|**int**|パブリッシャーにアップロードされた行数のうち、再試行された行数。|  
|**download_inserts**|**int**|サブスクライバー側で適用される挿入の数です。|  
|**download_updates**|**int**|サブスクライバーで適用された更新数。|  
|**download_deletes**|**int**|サブスクライバー側で適用される削除の数です。|  
|**download_conflicts**|**int**|サブスクライバー側で変更を適用する間に発生した競合の数です。|  
|**download_conflicts_resolved**|**int**|サブスクライバーで変更を適用中に発生した競合のうち、既に解決された競合の数。|  
|**download_rows_retried**|**int**|サブスクライバーにダウンロードされた行数のうち、再試行された行数。|  
|**schema_changes**|**int**|セッション中に適用されたスキーマ変更の数。|  
|**metadata_rows_cleanedup**|**int**|セッション中にクリーンアップされたメタデータの行数。|  
|**runstatus**|**int**|実行ステータスです。<br /><br /> **1** = 開始します。<br /><br /> **2** = 成功します。<br /><br /> **3** = 実行中です。<br /><br /> **4** = アイドル状態です。<br /><br /> **5** = 再試行します。<br /><br /> **6** = 失敗します。|  
|**estimated_upload_changes**|**int**|パブリッシャーで適用する必要がある変更の推定数。|  
|**estimated_download_changes**|**int**|サブスクライバーで適用する必要がある変更の推定数。|  
|**「接続タイプ」**|**int**|アップロード中に使用される接続。次の接続があります。<br /><br /> **1** = ローカル エリア ネットワーク (LAN)。<br /><br /> **2** = ダイヤルアップ ネットワークに接続します。<br /><br /> **3** = web 同期します。|  
|**timestamp**|**timestamp**|このテーブルのタイムスタンプ列です。|  
  
## <a name="see-also"></a>参照  
 [レプリケーション テーブル &#40;です。TRANSACT-SQL と #41 です。](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーション ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  