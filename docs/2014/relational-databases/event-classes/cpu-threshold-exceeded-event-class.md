---
title: CPU Threshold Exceeded イベント クラス | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
caps.latest.revision: 15
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 7883dff5b548ad0b6903934c4dd8d90be8cf2423
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37164689"
---
# <a name="cpu-threshold-exceeded-event-class"></a>CPU Threshold Exceeded イベント クラス
  CPU Threshold Exceeded イベント クラスは、REQUEST_MAX_CPU_TIME_SEC に指定されている CPU しきい値を超えるクエリがリソース ガバナーによって検出されたことを示します。  
  
> [!NOTE]  
>  このイベントの検出間隔は 5 秒です。 クエリが指定の制限を超えた時間が 5 秒以上の場合は、このイベントの生成が保証されます。 クエリが指定のしきい値を超えた時間が 5 秒未満の場合、クエリのタイミングと前回の検出スイープの時間によっては検出されない場合もあります。  
  
## <a name="cpu-threshold-exceeded-data-columns"></a>CPU Threshold Exceeded のデータ列  
  
|データ列名|データ型|説明|列 ID|フィルターの適用|  
|----------------------|---------------|-----------------|---------------|----------------|  
|CPU|`int`|CPU 使用率 (ミリ秒単位)。|18|はい|  
|EventClass|`int`|214|27|いいえ|  
|EventSubClass|`int`|CPU 制限違反。|21|はい|  
|GroupID|`int`|違反が発生したグループ ID。|66|はい|  
|OwnerID|`int`|違反の原因となったプロセスの SPID。|58|はい|  
|SPID|`int`|このイベントを発生させたサーバー プロセスの ID。<br /><br /> 注: システム スレッドが CPU 使用率をバックグラウンド タスクとして検証する場合は、この ID が実際のユーザー SPID と異なることがあります。|12|はい|  
|StartTime|`datetime`|このイベントが発生した時刻。|14|はい|  
  
## <a name="see-also"></a>参照  
 [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  