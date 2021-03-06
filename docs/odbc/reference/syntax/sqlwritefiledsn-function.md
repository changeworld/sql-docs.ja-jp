---
title: SQLWriteFileDSN 関数 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLWriteFileDSN
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLWriteFileDSN
helpviewer_keywords:
- SQLWriteFileDSN [ODBC]
ms.assetid: 9e18f56f-1061-416b-83d4-ffeec42ab5a9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6b8c490da7ecfe0230eaad5f98da1c66293f99eb
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47758960"
---
# <a name="sqlwritefiledsn-function"></a>SQLWriteFileDSN 関数
**準拠**  
 バージョンが導入されています。 ODBC 3.0  
  
 **概要**  
 **SQLWriteFileDSN**ファイル DSN に情報を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
  
BOOL SQLWriteFileDSN(  
     LPCSTR     lpszFileName,  
     LPCSTR     lpszAppName,  
     LPCSTR     lpszKeyName,  
     LPCSTR     lpszString);  
```  
  
## <a name="arguments"></a>引数  
 *場合*  
 [入力]ファイル DSN の名前へのポインター。 DSN の拡張機能は、DSN の拡張機能がまだないすべてのファイル名に追加されます。  
  
 *lpszAppName*  
 [入力]アプリケーションの名前へのポインター。 これは、ODBC のセクションの"ODBC"です。  
  
 *lpszKeyName*  
 [入力]読み取るキーの名前へのポインター。 予約済みキーワードは、「コメント」を参照してください。  
  
 *lpszString*  
 [出力]書き込まれるキーに関連付けられた文字列の指します。 この引数が指す文字列の最大長は 32,767 バイトです。  
  
## <a name="returns"></a>戻り値  
 関数は、成功した場合、FALSE が失敗した場合に TRUE を返します。  
  
## <a name="diagnostics"></a>診断  
 ときに**SQLWriteFileDSN** 、関連付けられている FALSE が返されます *\*pfErrorCode*を呼び出して値を取得する**SQLInstallerError**します。 次の表、  *\*pfErrorCode*によって返される値**SQLInstallerError**とこの関数のコンテキストでそれぞれについて説明します。  
  
|*\*pfErrorCode*|[エラー]|説明|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|一般的なインストーラーのエラー|エラーが発生する特定のインストーラーのエラーがなかった。|  
|ODBC_ERROR_INVALID_PATH|無効なインストール パス|指定されたファイル名のパス、*場合*引数が無効です。|  
|ODBC_ERROR_INVALID_REQUEST_TYPE|要求の型が無効です。|*LpszAppName*、 *lpszKeyName*、または*lpszString*引数が NULL でした。|  
  
## <a name="comments"></a>コメント  
 ODBC では、接続情報を格納するための [ODBC] セクションの名前を予約します。 このセクションの予約済みキーワードは、内の接続文字列用に予約したのと同じ**SQLDriverConnect**します。 (詳細については、次を参照してください、 [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md)関数の説明です。)。  
  
 アプリケーションでは、ファイル DSN に直接情報を書き込む、これらの予約済みキーワードを使用できます。 呼び出すことができます、アプリケーションを作成またはファイル DSN に関連付けられている接続文字列を変更する場合、 **SQLWriteFileDSN** [ODBC] セクションでは、予約済みの接続文字列キーワードのいずれか。  
  
 場合、 *lpszString*引数が null ポインターが指すキーワード、 *lpszKeyName*引数は .dsn ファイルから削除されます。 場合、 *lpszString*と*lpszKeyName*引数が両方とも null のポインターが指すセクション、 *lpszAppName*引数は .dsn ファイルから削除されます。  
  
## <a name="related-functions"></a>関連する関数  
  
|詳細|参照先|  
|---------------------------|---------|  
|ファイル Dsn から情報の読み取り|[SQLReadFileDSN](../../../odbc/reference/syntax/sqlreadfiledsn-function.md)|
