---
title: "手順 6: がデータ ソースから切断 |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application process [ODBC], disconnecting from data source
- data sources [ODBC], disconnecting
- disconnecting from data source [ODBC]
ms.assetid: 6ad759ba-4721-4d8f-9b26-de976d4fc1a0
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ce3ea03a637e8edce89c83f196e4fcafd97dfdc8
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="step-6-disconnect-from-the-data-source"></a>手順 6: がデータ ソースから切断します。
最後の手順は、次の図に示すように、データ ソースから切断するのにです。 アプリケーションが呼び出すことによって、ステートメント ハンドルを解放する最初に、 **SQLFreeHandle**です。 詳細については、次を参照してください。[ステートメント ハンドルの解放](../../../odbc/reference/develop-app/freeing-a-statement-handle-odbc.md)です。  
  
 ![データ ソースからの切断を示しています](../../../odbc/reference/develop-app/media/pr17.gif "pr17。")  
  
 次に、アプリケーションを使用して、データ ソースから接続が切断**SQLDisconnect**と接続ハンドルを解放し、 **SQLFreeHandle**です。 詳細については、次を参照してください。[データ ソースまたはドライバーからの切断](../../../odbc/reference/develop-app/disconnecting-from-a-data-source-or-driver.md)です。  
  
 アプリケーションが使用して、環境ハンドルを解放する最後に、 **SQLFreeHandle**と、ドライバー マネージャーをアンロードします。 詳細については、次を参照してください。[環境ハンドルの割り当て](../../../odbc/reference/develop-app/allocating-the-environment-handle.md)です。