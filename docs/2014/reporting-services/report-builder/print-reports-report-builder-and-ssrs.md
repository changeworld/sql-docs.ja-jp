---
title: レポートの印刷 (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: 4bad1b6e-7d94-4b17-9502-ccd3dce0fdd9
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 0b0f0b2087471d8f0c905b1a173eff57a0be7fd4
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48096702"
---
# <a name="print-reports-report-builder-and-ssrs"></a>レポートの印刷 (レポート ビルダーおよび SSRS)
  レポートをレポート サーバーに保存した後は、ブラウザーやレポート マネージャーのほか、エクスポートされたレポートの表示に使用する任意のアプリケーションで、レポートを表示および印刷できます。 レポートを保存する前にプレビューする場合は、印刷することができます。  
  
 すべての印刷処理は、要求時にクライアント コンピューター上で行われます。 Web サーバーに接続されているプリンターに直接レポート サーバーから印刷ジョブを送信できるようなサーバー側印刷機能はありません。 プリンターや印刷オプションは、個々のレポート ユーザーが標準の **[印刷]** ダイアログ ボックスを使用して選択します。  
  
 印刷専用のレポートをデザインするレポート作成者は、改ページ、ページのヘッダーとフッター、式、背景画像などを使用して、印刷用のデザインを作成できます。 印刷用のレポート デザイン要素としては、たとえば、どのレポートの裏面にもよく印刷される使用条件や、レターヘッドを模したグラフィック要素やテキスト要素などが考えられます。  
  
 表示形式によってページの割り当て方法が異なるため、すべてのレポートのすべての表示形式で最適な印刷結果が得られるとは限りません。 次に例を示します。  
  
1.  レポートのページはデータ量の変化に適応するようにデザインされます。 たとえば、マトリックスを含むレポートでは、ユーザーが行や列の表示を対話的に切り替えることによって、ページが上下左右に広がる可能性があります。 この場合、マトリックスを展開したユーザーと展開していないユーザーとでは、印刷結果が異なります。  
  
2.  横置きモードと縦置きモードの両方のページを同じレポートで使用することはできません。また、印刷用のレイアウトを作成して、それをブラウザーやその他のアプリケーションで表示されるレポートのレイアウトと置き換えたり、両方のレイアウトを共存させたりすることもできません。  
  
3.  エクスポートしたレポートでは、ほとんどの場合、レポートに表示されるすべての要素 (ユーザーがコンピューターの画面上で見るすべての要素) がレポートの印刷結果に含まれます。 レポート デザイン画面上の空白は保持されます。 水平方向の余分な空白ページを追加または削除するには、レポートのページの幅を変更します。  
  
> [!NOTE]  
>  ブラウザーの印刷コマンドを使用して HTML レポートを印刷すると、最初のページの内容しか印刷されないことがあります。 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] のクライアント側印刷機能を使用すると、より優れた HTML レポートの印刷結果を得ることができます。 詳細については、次を参照してください。[印刷コントロールを使用したブラウザーからのレポートの印刷&#40;レポート ビルダーおよび SSRS&#41;](print-reports-from-a-browser-with-the-print-control-report-builder-and-ssrs.md)します。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a>このセクションの内容  
 [印刷コントロールを使用したブラウザーからレポートを印刷&#40;レポート ビルダーおよび SSRS&#41;](print-reports-from-a-browser-with-the-print-control-report-builder-and-ssrs.md)  
 クライアント側印刷機能を使用して Web ブラウザーやレポート マネージャーからレポートを印刷する方法を説明します。  
  
 [他のアプリケーションからレポートを印刷&#40;レポート ビルダーおよび SSRS&#41;](print-reports-from-other-applications-report-builder-and-ssrs.md)  
 別のアプリケーションにエクスポートされたレポートを印刷する方法を説明します。  
  
 [レポートを印刷する&#40;レポート ビルダーおよび SSRS&#41;](print-a-report-report-builder-and-ssrs.md)  
 レポートを印刷する手順、ページの余白を制御する手順、およびハード改ページ レンダラー (PDF、画像、または印刷) によってレンダリングされるレポートの用紙サイズを指定する手順について説明します。  
  
## <a name="see-also"></a>参照  
 [レポートのエクスポート&#40;レポート ビルダーおよび SSRS&#41;](export-reports-report-builder-and-ssrs.md)   
 [ページ ヘッダーとページ フッター&#40;レポート ビルダーおよび SSRS&#41;](../report-design/page-headers-and-footers-report-builder-and-ssrs.md)   
 [イメージ&#40;レポート ビルダーおよび SSRS&#41;](../report-design/images-report-builder-and-ssrs.md)   
 [Reporting Services の改ページ &#40;レポート ビルダーおよび SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md)  
  
  
