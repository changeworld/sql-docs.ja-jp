---
title: プロパティ式を追加または変更する | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 5c571f92879a31399c0db4c7bc0acacc1355e169
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48178502"
---
# <a name="add-or-change-a-property-expression"></a>プロパティ式を追加または変更する
  パッケージ、タスク、Foreach ループ コンテナー、For ループ コンテナー、シーケンス コンテナー、イベント ハンドラー、パッケージおよびプロジェクト レベルの接続マネージャー、およびログ プロバイダーに対してプロパティ式を作成できます。  
  
 プロパティ式を作成または変更するには、 **[プロパティ式エディター]** か **[式ビルダー]** を使用します。 **[プロパティ式エディター]** には、タスクおよびコンテナーで使用可能なカスタム エディターか、 **[プロパティ]** ウィンドウからアクセスできます。 **[式ビルダー]** には、 **[プロパティ式エディター]** 内からアクセスできます。 **[プロパティ式エディター]** または **[式ビルダー]** のいずれかで式を作成することができますが、**[式ビルダー]** には、複雑な式の作成を容易にするグラフィカル ツール セットが備わっています。  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] が提供する構文、演算子、および関数の詳細については、「[ &#40;SSIS 式&#41;](operators-ssis-expression.md)」および「[ &#40;SSIS 式&#41;](functions-ssis-expression.md)」を参照してください。 各演算子または関数のトピックには、式で演算子や関数を使用する例が含まれます。 複雑な式の例については、「 [パッケージでプロパティ式を使用する](use-property-expressions-in-packages.md)」を参照してください。  
  
### <a name="to-create-or-change-a-property-expression"></a>プロパティ式を作成または変更するには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]で、目的の [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] パッケージが含まれているプロジェクトを開きます。  
  
2.  ソリューション エクスプローラーで、パッケージをダブルクリックして開き、次のいずれかの操作を行います。  
  
    -   アイテムがタスクまたはコンテナーの場合は、アイテムをダブルクリックし、エディターの **[式]** をクリックします。  
  
    -   アイテムを右クリックし、 **[プロパティ]** をクリックします。  
  
3.  **[式]** ボックス内でクリックし、省略記号 [...] をクリックします。  
  
4.  **[プロパティ式エディター]** で、 **[プロパティ]** ボックスの一覧からプロパティを選択し、次のいずれかの操作を行います。  
  
    -   **[式]** 列で直接プロパティ式を入力するか変更し、 **[OK]** をクリックします。  
  
         — または —  
  
    -   プロパティの式の行の省略記号 [...] をクリックし、 **[式ビルダー]** ダイアログ ボックスを開きます。  
  
5.  (省略可能) **[式ビルダー]** での次のタスクのいずれかを実行します。  
  
    -   システム変数およびユーザー定義変数にアクセスするには、 **[変数]** を展開します。  
  
    -   [!INCLUDE[ssIS](../../includes/ssis-md.md)] 式言語で提供される関数、キャスト、および演算子にアクセスするには、 **[数学関数]**、 **[文字列関数]**、 **[日付/時刻関数]**、 **[NULL 関数]**、 **[型キャスト]**、および **[演算子]** を展開します。  
  
    -   **[式ビルダー]** で式を作成または変更するには、変数、列、関数、演算子、およびキャストを **[式]** ボックスにドラッグするか、または式をボックスに入力します。  
  
    -   式の評価結果を表示するには、 **[式ビルダー]** の **[式の評価]** をクリックします。  
  
         式が有効でない場合は、式の構文エラーを示す警告が出力されます。  
  
        > [!NOTE]  
        >  式の評価を行っても、評価結果はプロパティに割り当てられません。  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>参照  
 [Integration Services &#40;SSIS&#41; 式](integration-services-ssis-expressions.md)   
 [パッケージでプロパティ式を使用します。](use-property-expressions-in-packages.md)   
 [Integration Services &#40;SSIS&#41;パッケージ](../integration-services-ssis-packages.md)   
 [Integration Services コンテナー](../control-flow/integration-services-containers.md)   
 [Integration Services タスク](../control-flow/integration-services-tasks.md)   
 [Integration Services &#40;SSIS&#41; のイベント ハンドラー](../integration-services-ssis-event-handlers.md)   
 [Integration Services &#40;SSIS&#41; の接続](../connection-manager/integration-services-ssis-connections.md)   
 [Integration Services &#40;SSIS&#41; のログ記録](../performance/integration-services-ssis-logging.md)  
  
  
