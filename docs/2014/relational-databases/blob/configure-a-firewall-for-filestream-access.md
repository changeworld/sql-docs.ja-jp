---
title: FILESTREAM アクセスのためのファイアウォールの構成 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 6be07fffa636a2cdc51197916d2bdf218cdea289
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48073702"
---
# <a name="configure-a-firewall-for-filestream-access"></a>FILESTREAM アクセスのためのファイアウォールの構成
  ファイアウォールで保護された環境で FILESTREAM を使用するには、クライアントとサーバーの両方で、FILESTREAM ファイルが格納されているサーバーの DNS 名を解決できる必要があります。 FILESTREAM を使用する場合は、Windows ファイル共有ポート 139 および 445 を開く必要があります。  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a>Windows 7 を実行しているコンピューターで Windows ファイル共有ポートを開くには  
  
1.  コントロール パネルで、 **[Windows ファイアウォール]** を開きます。  
  
2.  左側のペインの **[詳細設定]** をクリックします。 管理者のパスワードの入力または確認入力を求めるメッセージが表示されたら、パスワードを入力するか、確認入力を行います。  
  
3.  **[セキュリティが強化された Windows ファイアウォール]** ダイアログ ボックスの左ペインの **[受信の規則]** をクリックした後、右ペインの **[新しい規則]** をクリックします。  
  
4.  新規の受信の規則のウィザードに従って、TCP ポート 139 を追加します。  
  
5.  前の手順をもう一度実行して、TCP ポート 445 を追加します。  
  
6.  **[セキュリティが強化された Windows ファイアウォール]** ダイアログ ボックスを閉じます。  
  
  
