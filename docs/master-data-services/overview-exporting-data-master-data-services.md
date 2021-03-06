---
title: '概要: データのエクスポート (Master Data Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 4bd0daeff5ae25dd0e1e7ff19e685b0cbc129384
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47647880"
---
# <a name="overview-exporting-data-master-data-services"></a>概要: データのエクスポート (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  この記事では、サブスクリプション ビュー形式の種類と、モデル オブジェクトが変更されたためにビューを編集する必要がある場合を判断する方法について説明します。  
  
 サブスクリプション ビューを作成して、 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] データを [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]のようなサブスクライブ システムにエクスポートします。 サブスクライブ システムを使用して、 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] データベースのデータを表示します。  サブスクライブ ビューを作成する方法については、「 [サブスクリプション ビューを作成してデータをエクスポートする (マスター データ サービス)](../master-data-services/create-a-subscription-view-to-export-data-master-data-services.md)  
  
 ビューの詳細については、「 [ビュー](../relational-databases/views/views.md)」を参照してください。  
  
## <a name="subscription-view-formats"></a>サブスクリプション ビュー形式  
 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]でビューを作成する場合は、 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] によって提供される一連の標準ビュー形式から選択します。 これらの形式を使用して、以下を表示するビューを作成できます。  
  
-   すべてのリーフ メンバーとその属性  
  
-   すべての統合メンバーとその属性  
  
-   すべてのコレクションとその属性  
  
-   コレクションに明示的に追加されたメンバー  
  
-   親子形式またはレベル形式の派生階層内のメンバー  
  
-   エンティティのすべての明示的階層内のメンバー (親子形式またはレベル形式)  
  
## <a name="subscription-views-can-become-out-of-date"></a>サブスクリプション ビューが古くなる可能性  
 エンティティまたは階層のサブスクリプション ビューを作成後、関連付けられたモデル オブジェクトへの変更が自動的にビューに反映されるわけではありません。 モデル オブジェクトに対する変更を反映するには、必要に応じて [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] でサブスクリプション ビューを再生成する必要があります。 モデル オブジェクトが変更されると、 **[エクスポート]** ページの **[変更]** 列が **[True]** に更新されます。 **[True]** は、サブスクリプション ビューを編集して保存する必要があることを示します。この操作により、ビューが再生成されます。  
  
## <a name="related-tasks"></a>Related Tasks  
  
|タスクの説明|トピック|  
|----------------------|-----------|  
|マスター データのサブスクリプション ビューを作成する。|[サブスクリプション ビューを作成してデータをエクスポートする (マスター データ サービス)](../master-data-services/create-a-subscription-view-to-export-data-master-data-services.md)|  
|既存のサブスクリプション ビューを削除する。|[サブスクリプション ビューを削除する (マスター データ サービス)](../master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a>関連コンテンツ  
  
-   [サブスクリプション ビュー形式 (マスター データ サービス)](../master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [ビュー](../relational-databases/views/views.md)  
  
  
