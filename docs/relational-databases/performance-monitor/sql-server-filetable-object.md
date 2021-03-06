---
title: SQL Server、FileTable オブジェクト | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
s.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:FileTable
ms.assetid: 325f5e58-1095-450f-9321-dfacfe6fd55f
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 8544f91e62343ea5e1be6a1191b73db298cce7af
ms.sourcegitcommit: ca038f1ef180e4e1b27910bbc5d87822cd1ed176
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52158900"
---
# <a name="sql-server-filetable-object"></a>SQL Server、FileTable オブジェクト
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
**SQLServer:FileTable** パフォーマンス オブジェクトは、FileTable および非トランザクション アクセスに関連する統計カウンターを提供します。

次の表では、SQL Server **FileTable** パフォーマンス オブジェクトについて説明します。

|**SQL Server FileTable のカウンター**|[説明]|  
|-------------|-----------------|  
|**Avg time delete FileTable item**|FileTable アイテムの削除に要した平均時間 (ミリ秒)。|
|**Avg time FileTable enumeration**|FileTable の列挙要求に要した平均時間 (ミリ秒)。|
|**Avg time FileTable handle kill**|FileTable ハンドルの強制終了に要した平均時間 (ミリ秒)。|
|**Avg time move FileTable item**|FileTable アイテムの移動に要した平均時間 (ミリ秒)。|
|**Avg time per file I/O request**|受信ファイル I/O 要求の処理に要した平均時間 (ミリ秒)。|
|**Avg time per file I/O response**|送信ファイル I/O 応答の処理に要した平均時間 (ミリ秒)。|
|**Avg time rename FileTable item**|FileTable アイテムの名前変更に要した平均時間 (ミリ秒)。|
|**Avg time to get FileTable item**|FileTable アイテムの取得に要した平均時間 (ミリ秒)。|
|**Avg time update FileTable item**|FileTable アイテムの更新に要した平均時間 (ミリ秒)。|
|**FileTable db operations/sec**|FileTable ストア コンポーネントによって 1 秒間に処理されたデータベース操作イベントの総数。|
|**FileTable enumeration reqs/sec**|1 秒間に処理された FileTable の列挙要求の総数。|
|**FileTable file I/O requests/sec**|1 秒間に処理された受信 FileTable ファイル I/O 要求の総数。|
|**FileTable file I/O response/sec**|1 秒間に処理された送信ファイル I/O 応答の総数。|
|**FileTable item delete reqs/sec**|1 秒間に処理された FileTable アイテムの削除要求の総数。|
|**FileTable item get requests/sec**|1 秒間に処理された FileTable アイテムの取得要求の総数。|
|**FileTable item move reqs/sec**|1 秒間に処理された FileTable アイテムの移動要求の総数。|
|**FileTable item rename reqs/sec**|1 秒間に処理された FileTable アイテムの名前変更要求の総数。|
|**FileTable item update reqs/sec**|1 秒間に処理された FileTable アイテムの更新要求の総数。|
|**FileTable kill handle ops/sec**|1 秒間に処理された FileTable ハンドル強制終了操作の総数。|
|**FileTable table operations/sec**|FileTable ストア コンポーネントによって 1 秒間に処理されたテーブル操作イベントの総数。|
|**Time delete FileTable item BASE**|内部使用のみです。|
|**Time FileTable enumeration BASE**|内部使用のみです。|
|**Time FileTable handle kill BASE**|内部使用のみです。|
|**Time move FileTable item BASE**|内部使用のみです。|
|**Time per file I/O request BASE**|内部使用のみです。|
|**Time per file I/O response BASE**|内部使用のみです。|
|**Time rename FileTable item BASE**|内部使用のみです。|
|**Time to get FileTable item BASE**|内部使用のみです。|
|**Time update FileTable item BASE**|内部使用のみです。| 
 
## <a name="see-also"></a>参照  
[リソースの利用状況の監視 (システム モニター)](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)
