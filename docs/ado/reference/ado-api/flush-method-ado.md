---
title: "Flush メソッド (ADO) |Microsoft ドキュメント"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- _Stream::Flush
- _Stream::raw_Flush
helpviewer_keywords:
- Flush method [ADO]
ms.assetid: 938522b4-f836-4c80-8d27-a598a000f0ee
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: dc0e90c43b2f691f1dff705e813ffe77fe5fc35a
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="flush-method-ado"></a>Flush メソッド (ADO)
内容を強制的、[ストリーム](../../../ado/reference/ado-api/stream-object-ado.md)を基になるオブジェクトに ADO バッファーに残っている、**ストリーム**が関連付けられています。  
  
## <a name="syntax"></a>構文  
  
```  
  
Stream.Flush  
```  
  
## <a name="remarks"></a>解説  
 このメソッドは、基になるオブジェクトにストリーム バッファーの内容を送信する使用できます: ノードまたはのソースでは、URL で表されるファイルなど、**ストリーム**オブジェクト。 すべての変更することを確認する場合、このメソッドを呼び出す必要がありますの内容に加えられた、**ストリーム**書き込まれています。 ただし、ADO と必要はありません通常を呼び出す**フラッシュ**ADO は継続的にバック グラウンドで可能な限り、バッファーをフラッシュします。 コンテンツの変更、**ストリーム**は自動的に行わ、までにキャッシュされていない**フラッシュ**と呼びます。  
  
 閉じる、**ストリーム**で、[閉じる](../../../ado/reference/ado-api/close-method-ado.md)メソッドの内容はフラッシュ、**ストリーム**自動的に; がありますに明示的に呼び出す必要はありません**をフラッシュ**直前**閉じる**です。  
  
## <a name="applies-to"></a>適用対象  
 [ストリーム オブジェクト (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)