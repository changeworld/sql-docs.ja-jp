---
title: MSSQL_ENG021385 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 1f7f2d0d1b5a8e0cc2ac1a8c6766584493de4b98
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48142822"
---
# <a name="mssqleng021385"></a>MSSQL_ENG021385
    
## <a name="message-details"></a>メッセージの詳細  
  
|||  
|-|-|  
|製品名|SQL Server|  
|イベント ID|21385|  
|イベント ソース|MSSQLSERVER|  
|コンポーネント|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|シンボル名||  
|メッセージ テキスト|スナップショットはパブリケーション '%s' の処理に失敗しました。 アクティブなスキーマ変更または新しいアーティクルが追加されたことが原因の可能性があります。|  
  
## <a name="explanation"></a>説明  
 このエラーは、アーティクルの追加や削除、パブリッシュされたオブジェクトへのスキーマ変更の実行など、パブリケーション データベースに対する変更が実行中のときに、スナップショット エージェントが起動されると発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 パブリケーション データベースに対する変更が完了した後に、スナップショット エージェントを再起動します。 詳細については、「[レプリケーション エージェントを起動および停止する &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)」および「[レプリケーション エージェント実行可能ファイルの概念](concepts/replication-agent-executables-concepts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [エラーとイベントのリファレンス &#40;レプリケーション&#41;](errors-and-events-reference-replication.md)  
  
  
