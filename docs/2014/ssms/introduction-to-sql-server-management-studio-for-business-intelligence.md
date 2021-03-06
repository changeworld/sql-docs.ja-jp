---
title: Business Intelligence for SQL Server Management Studio の概要 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio for Integration Services
- SQL Server Management Studio for Reporting Services
- SQL Server Management Studio for Analysis Services
ms.assetid: ffaa77b7-03d0-4d7a-aa42-c5091a4f2ceb
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 435bd85fd024ff8e302cdb91f63c8cbfa02ebb9e
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48152695"
---
# <a name="introduction-to-sql-server-management-studio-for-business-intelligence"></a>ビジネス インテリジェンスに使用される SQL Server Management Studio の概要
  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]、[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]、および [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] のアクセス、構成、管理を行うには、[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] を使用します。 この 3 つのビジネス インテリジェンス テクノロジは [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]を使用しますが、各テクノロジに関連付けられている管理タスクは少しずつ異なります。  
  
> [!NOTE]  
>  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]、 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]、および [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] の各ソリューションを作成および変更するには、 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ではなく [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]を使用します。 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] は、 [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[vsprvs](../includes/vsprvs-md.md)]をベースとする開発環境です。  
  
## <a name="managing-analysis-services-solutions-using-sql-server-management-studio"></a>SQL Server Management Studio を使用した Analysis Services ソリューションの管理  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] では、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] オブジェクトの管理を行うことができます (バックアップの実行やオブジェクトの処理など)。  
  
 [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] では、多次元式 (MDX)、データ マイニング拡張機能 (DMX)、および XML for Analysis (XMLA) で作成されるスクリプトの開発と保存を行う [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] スクリプト プロジェクトが提供されます。 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] スクリプト プロジェクトは、 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] インスタンスで管理タスクを実行したり、データベースやキューブなどのオブジェクトを再作成したりする場合に使用します。 たとえば、既存の [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] インスタンスで直接新しいオブジェクトを作成する XMLA スクリプトを [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] スクリプト プロジェクトで開発することができます。 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] スクリプト プロジェクトは、ソリューションの一部として保存し、ソース コード コントロールに統合できます。  
  
 使用する方法の詳細についての[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]を参照してください[SQL Server Management Studio で Analysis Services スクリプト プロジェクト](../analysis-services/instances/analysis-services-scripts-project-in-sql-server-management-studio.md)します。  
  
## <a name="managing-integration-services-solutions-using-sql-server-management-studio"></a>SQL Server Management Studio を使用した Integration Services ソリューションの管理  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] では、 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] サービスを使用して、パッケージの管理および実行中のパッケージの監視を行うことができます。 また [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] では、パッケージをフォルダーに編成できるほか、パッケージの実行、インポート、エクスポート、データ変換サービス (DTS) パッケージの移行、および [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] パッケージのアップグレードを行うことができます。  
  
## <a name="managing-reporting-services-projects-using-sql-server-management-studio"></a>SQL Server Management Studio を使用した Reporting Services プロジェクトの管理  
 SQL Server Management Studio では、Reporting Services の機能の有効化、サーバーとデータベースの管理、およびロールとジョブの管理を行うことができます。  
  
 [共有スケジュール] フォルダーを使用して共有スケジュールを管理し、レポート サーバー データベース (ReportServer、ReportServerTempdb) を管理します。 また、レポート サーバー データベースを新規または別の SQL Server データベース エンジン ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)]) に移動する場合は、master システム データベースで RSExecRole を作成します。 これらの作業の詳細については、次のトピックを参照してください。  
  
-   [SQL Server Management Studio の Reporting Services &#40;SSRS&#41;](../reporting-services/tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
-   [レポート サーバーのデータベース管理&#40;SSRS ネイティブ モード&#41;](../reporting-services/report-server/report-server-database-ssrs-native-mode.md)  
  
-   [RSExecRole を作成する](../reporting-services/security/create-the-rsexecrole.md)  
  
 また、各種機能の有効化と構成、サーバーの既定値の設定、およびロールとジョブの管理を行うことで、サーバーを管理します。 これらの作業の詳細については、次のトピックを参照してください。  
  
-   [レポート サーバーのプロパティを設定&#40;Management Studio&#41;](../reporting-services/tools/set-report-server-properties-management-studio.md)  
  
-   [作成、削除、またはロールを変更&#40;Management Studio&#41;](../reporting-services/security/role-definitions-create-delete-or-modify.md)  
  
-   [Reporting Services のクライアント側印刷機能の有効化と無効化](../reporting-services/report-server/enable-and-disable-client-side-printing-for-reporting-services.md)  
  
## <a name="see-also"></a>参照  
 [マルチ ディメンションを作成する SQL Server データ ツールの使用をモデル化&#40;SSDT&#41;](../analysis-services/multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)   
 [Reporting Services SQL Server Data Tools の&#40;SSDT&#41;](../reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt.md)  
  
  
