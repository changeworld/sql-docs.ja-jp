---
title: "その他のファイル | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- files [SQL Server Management Studio], miscellaneous
- projects [SQL Server Management Studio], files
- solutions [SQL Server Management Studio], files
- miscellaneous files folder [SQL Server]
ms.assetid: 3c952b0b-8f5f-4d86-9e5d-616c10b9df0d
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 6ea72cab23f488c8330d78dc5c6a1275e043728a
ms.lasthandoff: 04/11/2017

---
# <a name="miscellaneous-files"></a>その他のファイル
プロジェクトの外部のファイルのことを *その他のファイル*といいます。 ソリューションを開いているときには、プロジェクトに関連するその他のファイルを開いて修正できます。 その他のファイルとして分類されるのは、プロジェクトのコード エディターにファイル拡張子が関連付けられていないファイルです。 たとえば、 [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] スクリプト プロジェクトの場合、拡張子が .txt や .mdx のファイルはその他のファイルとして扱われます。 MDX プロジェクトでは、拡張子が .txt や .sql のファイルはその他のファイルとして扱われます。 ファイル拡張子をコード エディターに関連付ける方法については、「 [ファイル拡張子をコード エディターに関連付ける方法](http://msdn.microsoft.com/en-us/193630f4-93de-4950-8f36-68702531f925)」をご覧ください。  
  
プロジェクトにその他のファイルを追加する機能は、いろいろな面で役立ちます。 たとえば、ソリューションの開発に不可欠ではあっても、必ずしもスクリプトとして認識されているわけではないファイルが存在します。 一般的な例としては、開発に関するメモや指示書、データ ファイル、コードの一部などがあります。  
  
その他のファイルを活用すれば、柔軟な対応が可能になります。 たとえば、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] スクリプト プロジェクトに、テーブルやストアド プロシージャをデータベース内に作成するためのスクリプトがいくつかあるとします。 また、テーブルのデータ ファイルとして拡張子 .BCP のファイルがいくつかあり、実行用の指示書として README.TXT ファイルがあるとします。 そのようなデータ ファイルや README ファイルをその他のファイルとしてプロジェクトに追加すれば、プロジェクト システムのソース管理機能や他の機能を活用できるようになります。  
  
[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] のメニューやツール バーは、開くファイルの形式に応じて変わるようになっています。 たとえば、テキスト ファイルを開けば、[テキスト エディター] ツール バーが表示されます。 XML スキーマ ファイルを開けば、[XML スキーマ] ツール バーが表示されます。 XML スキーマを編集しているときに、[テキスト エディター] ツール バーは使用できません。 プロジェクト ファイルからその他のファイルに切り替えれば、プロジェクトに関連したコマンドやツール バーがすべてその他のファイルに関連したコマンドやツール バーに置き換えられます。  
  
## <a name="see-also"></a>参照  
[ソリューションとプロジェクトを管理するためのファイル](../../ssms/solution/files-that-manage-solutions-and-projects.md)  
[ソリューション (SQL Server Management Studio)](../../ssms/solution/solutions-sql-server-management-studio.md)  
[プロジェクト (SQL Server Management Studio)](../../ssms/solution/projects-sql-server-management-studio.md)  
  
