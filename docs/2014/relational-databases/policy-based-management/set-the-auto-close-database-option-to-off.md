---
title: AUTO_CLOSE データベース オプションを OFF に設定 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 43cabd1eed4aaf84cb510428310c4c778a7d947c
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48076553"
---
# <a name="set-the-autoclose-database-option-to-off"></a>AUTO_CLOSE データベース オプションを OFF に設定
  このルールは、AUTO_CLOSE オプションが OFF に設定されているかどうかをチェックします。 AUTO_CLOSE が ON に設定されると、頻繁にアクセスされるデータベースでパフォーマンスが低下する場合があります。これは、接続するたびにデータベースを開いたり閉じたりするオーバーヘッドが増加するためです。 また、AUTO_CLOSE は、接続が終了するたびにプロシージャ キャッシュをフラッシュします。  
  
## <a name="best-practices-recommendations"></a>ベスト プラクティスと推奨事項  
 頻繁にアクセスされるデータベースでは、AUTO_CLOSE オプションを OFF に設定してください。  
  
## <a name="for-more-information"></a>詳細情報  
 [ALTER DATABASE SET のオプション &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a>参照  
 [ポリシー ベースの管理を使用したベスト プラクティスの監視と実行](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
