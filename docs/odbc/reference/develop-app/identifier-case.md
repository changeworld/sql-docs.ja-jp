---
title: 識別子のケース |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQL statements [ODBC], interoperability
- identifiers [ODBC], case
- interoperability of SQL statements [ODBC], identifier case
ms.assetid: ee8a31aa-389d-4dd1-bfa9-547f6b50bc70
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6445cffd5faa8b825c81ec729d7b28c90e14a7b3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47678352"
---
# <a name="identifier-case"></a>識別子の大文字と小文字の区別
SQL ステートメントとカタログ関数の引数では、識別子と引用符で囲まれた識別子できますか大文字か、アプリケーションを呼び出すことによって判断できますが、 **SQLGetInfo** SQL_IDENTIFIER_CASE SQL_QUOTED_ とIDENTIFIER_CASE オプション。  
  
 これらの各オプションは、4 つの戻り値: 1 つを示す識別子または引用符で囲まれた識別子のケースが区別されると、3 つを示すは区別されません。 さらに、小文字は区別されません、3 つの値には、識別子がシステム カタログに格納されているケースがについて説明します。 アプリケーションが、カタログ関数の結果を表示する場合など、表示目的でのみに関連がシステム カタログの識別子を格納する方法識別子の大文字小文字の区別は変更されません。
