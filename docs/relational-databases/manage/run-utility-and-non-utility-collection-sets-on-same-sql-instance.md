---
title: "同じ SQL インスタンスでユーティリティとユーティリティ以外のコレクション セットを実行する | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
caps.latest.revision: 6
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: d6f1a687472d2ee83f48fe273008a0d60f51bc58
ms.lasthandoff: 04/11/2017

---
# <a name="run-utility-and-non-utility-collection-sets-on-same-sql-instance"></a>同じ SQL インスタンスでユーティリティとユーティリティ以外のコレクション セットを実行する
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティ コレクション セットは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティ以外のコレクション セットとサイド バイ サイドで実行できます。 つまり、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のマネージ インスタンスは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティのメンバーであれば、他のコレクション セットによって監視できます。 ただし、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティ以外のデータ収集機能は、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスが [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティに登録されている場合は無効にする必要があります。  
  
 インスタンスが UCP に登録されたら、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティ以外のコレクション セットを再開できます。 ただし、マネージ インスタンス上のすべてのコレクション セットは、そのデータをユーティリティ管理データ ウェアハウス (UMDW) にアップロードすることに注意してください。UMDW ファイル名は sysutility_mdw です。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティ コレクション セットを [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティ以外のコレクション セットとサイド バイ サイドで実行する場合は、次の点を考慮してください。  
  
-   コレクション セットはサイド バイ サイドで実行できます。  
  
-   インスタンスを [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティに登録している間は、既存のデータ コレクターを無効にする必要があります。  
  
-   検証要件を満たすには、次のストアド プロシージャを、UCP を作成する前に [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスで、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティに登録する前に [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスで実行する必要があります。  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     UCP の作成ウィザードまたはマネージ インスタンスの追加ウィザードを起動する前にこれらのストアド プロシージャを実行しないと、操作は失敗します。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ユーティリティの UMDW (sysutility_mdw) は、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]のマネージ インスタンス上のすべてのコレクション セットに対して使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [SQL Server ユーティリティの機能とタスク](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)   
 [ユーティリティ コントロール ポイント データ ウェアハウスの構成 &#40;SQL Server Utility&#41;](../../relational-databases/manage/configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  