---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d56dbcb5fe1d37e3fce223bc910830b063484aa5
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48117452"
---
# <a name="localdberrorinstanceexistswithlowerversion"></a>LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION
    
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|SQL Server|  
|イベント ID|258|  
|イベント ソース|SQL Server Local Database Runtime 12.0|  
|コンポーネント|Local Database Runtime API|  
|メッセージ テキスト|指定されたバージョンのローカル データベース インスタンスを作成できません。 同じ名前のインスタンスは既に存在しますが、指定されたバージョンよりも下位のバージョンになっています。|  
  
## <a name="explanation"></a>説明  
 指定したインスタンスは既に存在しますが、そのバージョンは要求よりも低いバージョンです。  
  
## <a name="user-action"></a>ユーザーの操作  
 既存のインスタンスを削除し、操作を再試行してください。  
  
  
