---
title: 'SSIS チュートリアル: パッケージの配置 |Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
helpviewer_keywords:
- deployment tutorial [Integration Services]
- deploying packages [Integration Services]
- SSIS, tutorials
- Integration Services, tutorials
- deploying packages [Integration Services], installing
- SQL Server Integration Services, tutorials
- walkthroughs [Integration Services]
- deployment utility [Integration Services]
- deploying packages [Integration Services], configurations
ms.assetid: de18468c-cff3-48f4-99ec-6863610e5886
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 49aff131d55dbc38511fdae0dc930e161904a985
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48188972"
---
# <a name="ssis-tutorial-deploying-packages"></a>SSIS チュートリアル : パッケージの配置
  [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] には、パッケージを別のコンピューターへ簡単に配置できるツールが用意されています。 この配置ツールでは、パッケージに必要な構成やファイルなどの依存関係を管理することもできます。 このチュートリアルでは、これらのツールを使用して、対象のコンピューターにパッケージとその依存関係をインストールする方法を学習します。  
  
 まず、配置の準備を行います。 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] で新しい [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] プロジェクトを作成し、既存のパッケージとデータ ファイルをプロジェクトに追加します。 新しいパッケージを最初から作成するのではなく、このチュートリアル用に作成された既存のパッケージで作業を行います。 このチュートリアルでパッケージの機能は変更しませんが、パッケージをプロジェクトに追加した後、 [!INCLUDE[ssIS](../includes/ssis-md.md)] デザイナーでパッケージを開いて内容を確認しておくことをお勧めします。 パッケージの内容を確認すると、ログ ファイルなどのパッケージの依存関係やその他の便利な機能について理解できます。  
  
 また、配置の前に、パッケージが構成を使用するように更新しておきます。 構成によって、実行時にパッケージやパッケージ オブジェクトのプロパティを更新できます。 このチュートリアルでは、構成を使用して、ログ ファイルとテキスト ファイルの接続文字列、およびパッケージが使用する XML ファイルと XSD ファイルの場所を更新します。 詳細については、「 [パッケージ構成](../../2014/integration-services/package-configurations.md) 」および「 [パッケージ構成を作成する](../../2014/integration-services/create-package-configurations.md)」を参照してください。  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]でパッケージが正常に実行されることを確認したら、パッケージのインストールに使用する配置バンドルを作成します。 配置バンドルは、 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] プロジェクトに追加したパッケージ ファイルとその他の項目、 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] に自動的に含まれるパッケージの依存関係、および構築した配置ユーティリティから構成されます。 詳細については、「 [配置ユーティリティを作成する](../../2014/integration-services/create-a-deployment-utility.md)」を参照してください。  
  
 配置バンドルを対象のコンピューターにコピーし、パッケージ インストール ウィザードを実行して、パッケージとパッケージの依存関係をインストールします。 パッケージは msdb SQL Server データベースにインストールされ、サポート ファイルと補助ファイルはファイル システムにインストールされます。 配置されたパッケージは構成を使用するので、新しい値に更新して、パッケージを新しい環境で正常に実行できるようにします。  
  
 最後に、パッケージ実行ユーティリティを使用して、 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] でパッケージを実行します。  
  
 このチュートリアルの目的は、実際の配置で発生する可能性のある複雑な問題をシミュレーションすることです。 ただし、パッケージを別のコンピューターに配置できない場合は、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]のローカル インスタンスの msdb データベースにパッケージをインストールし、パッケージを同じインスタンスの [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] から実行して、このチュートリアルを行うこともできます。  
  
## <a name="what-you-will-learn"></a>学習する内容  
 [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] の新しいツール、コントロール、機能などに慣れる最良の方法は、実際に使ってみることです。 このチュートリアルでは、 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] プロジェクトを作成し、パッケージとその他の必要なファイルをプロジェクトに追加する手順を紹介します。 プロジェクトが完成したら、配置バンドルを作成し、バンドルを目的のコンピューターにコピーして、そのコンピューターにパッケージをインストールします。  
  
## <a name="requirements"></a>要件  
 このチュートリアルは、ファイル システムの基本的な操作は理解していても、 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]の新機能はほとんど使用したことがないユーザーを対象にしています。 基本を理解する[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]このチュートリアルで使用する配置は概念、便利に最初に、次の手順に[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]チュートリアル: [、SQL Server インポートおよびエクスポート ウィザードを実行](import-export-data/start-the-sql-server-import-and-export-wizard.md)と[SSIS チュートリアル: 簡単な ETL パッケージを作成する](../integration-services/ssis-how-to-create-an-etl-package.md)します。  
  
 **ソース コンピューター** 配置バンドルを作成するコンピューターには、次のコンポーネントがインストールされている必要があります。  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] および AdventureWorks データベース。 セキュリティ強化のため、既定ではサンプル データベースがインストールされません。 サンプル データベースをダウンロードする[CodePlex](http://msftdbprodsamples.codeplex.com/releases/view/125550)します。  
  
-   AdventureWorks に対してテーブルの作成および削除を行うための権限。  
  
-   このチュートリアルには、サンプル データ、完成したパッケージ、構成、Readme も必要です。 これらの項目のファイルは、サンプルと共にインストールされます。 サンプル データが見つからない場合は、前の手順に戻り、必要なインストール操作を完了してください。  
  
-   ビジネス インテリジェンスの開発環境、[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]。  
  
 **配置先コンピューター** パッケージを配置するコンピューターには、次のコンポーネントがインストールされている必要があります。  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] および AdventureWorks データベース。  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]。  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]」を参照してください。  
  
-   AdventureWorks でテーブルを作成および削除する権限と、[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] でパッケージを実行する権限が必要です。  
  
-   必要で読み取りおよび書き込みアクセス許可、msdb の sysssispackages テーブル[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]システム データベースです。  
  
 配置バンドルを作成したコンピューターにパッケージを配置する場合は、そのコンピューターが配置元コンピューターと配置先コンピューターの両方の必要条件を満たしている必要があります。  
  
 **このチュートリアルの推定所要時間:** 2 時間  
  
## <a name="lessons-in-this-tutorial"></a>このチュートリアルで行うレッスン  
 [レッスン 1: 配置バンドルを作成する準備](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md)  
 このレッスンでは、新しい [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] プロジェクトを作成し、パッケージとその他の必要なファイルをプロジェクトに追加して、ETL ソリューションを配置する準備を行います。  
  
 [レッスン 2: 配置バンドルの作成](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
 このレッスンでは、配置ユーティリティを構築し、配置バンドルに必要なファイルが含まれていることを確認します。  
  
 [レッスン 3: パッケージのインストール](../integration-services/lesson-3-install-ssis-package.md)  
 このレッスンでは、配置バンドルを対象のコンピューターにコピーし、パッケージをインストールして、パッケージを実行します。  
  
![Integration Services のアイコン (小)](media/dts-16.gif "Integration Services アイコン (小)")**Integration Services の日付を維持します。** <br /> マイクロソフトが提供する最新のダウンロード、アーティクル、サンプル、ビデオ、およびコミュニティで選択されたソリューションについては、MSDN の [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] のページを参照してください。<br /><br /> [MSDN の Integration Services のページを参照してください。](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> これらの更新が自動で通知されるようにするには、ページの RSS フィードを定期受信します。  
  
  
