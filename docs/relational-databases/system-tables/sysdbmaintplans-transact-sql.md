---
title: sysdbmaintplans (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysdbmaintplans_TSQL
- sysdbmaintplans
dev_langs:
- TSQL
helpviewer_keywords:
- sysdbmaintplans system table
ms.assetid: 0363296a-3082-48a9-9eb5-a1020b2f541a
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0525a50b30036470336dafe10c78a42218486c63
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47774670"
---
# <a name="sysdbmaintplans-transact-sql"></a>sysdbmaintplans (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  次の表に記載されて[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]の既存の情報を保持するために、以前のバージョンからアップグレードされたインスタンス[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]します。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] このテーブルの内容は変更されません。 このテーブルに格納されます、 **msdb**データベース。  
  
 [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  

  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**plan_id**|**uniqueidentifier**|データベース メンテナンス プランの ID|  
|**plan_name**|**sysname**|データベース メンテナンス プランの名前。|  
|**date_created**|**datetime**|データベース メンテナンス プランが作成された日付。|  
|**所有者**|**sysname**|データベース メンテナンス プランの所有者。|  
|**max_history_rows**|**int**|システム テーブル内で、データベース メンテナンス プランの履歴の記録用に割り当てられる行数の最大値。|  
|**remote_history_server**|**sysname**|履歴レポートがリモート サーバーに書き込まれる場合のサーバーの名前。|  
|**max_remote_history_rows**|**int**|履歴レポートがリモート サーバーに書き込まれる場合の、サーバー上のシステム テーブル内で割り当てられる行数の最大値。|  
|**user_defined_1**|**int**|既定値は NULL|  
|**user_defined_2**|**nvarchar(100)**|既定値は NULL|  
|**user_defined_3**|**datetime**|既定値は NULL|  
|**user_defined_4**|**uniqueidentifier**|既定値は NULL|  
|**log_shipping**|**bit**|ログ配布の状態。<br /><br /> **0** = 無効になっている**1** = 有効になっています。|  
  
  
