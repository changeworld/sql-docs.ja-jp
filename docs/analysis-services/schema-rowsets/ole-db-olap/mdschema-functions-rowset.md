---
title: "MDSCHEMA_FUNCTIONS 行セット |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- MDSCHEMA_FUNCTIONS
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- MDSCHEMA_FUNCTIONS rowset
ms.assetid: 5253fa8c-b1ce-4504-aff6-a246b5e675c7
caps.latest.revision: 29
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2e0ce2d79d149e1cf3ba6fbbe0cbe14ed8dffa14
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="mdschemafunctions-rowset"></a>MDSCHEMA_FUNCTIONS 行セット
  データベースに接続されているクライアント アプリケーションで利用できる関数について記述します。  
  
## <a name="rowset-columns"></a>行セットの列  
 **MDSCHEMA_FUNCTIONS**行セットには、次の列が含まれています。  
  
|列名|型を表すインジケーター|Description|  
|-----------------|--------------------|-----------------|  
|**FUNCTION_NAME**|**DBTYPE_WSTR**|関数の名前です。|  
|**DESCRIPTION**|**DBTYPE_WSTR**|関数の説明。|  
|**PARAMETER_LIST**|**DBTYPE_WSTR**|[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic と同様の形式に設定されたパラメーターのコンマ区切りの一覧。 たとえば、パラメーターは String としての Name になります。|  
|**RETURN_TYPE**|**DBTYPE_I4**|**VARTYPE**関数の戻り値のデータ型。|  
|**配信元**|**DBTYPE_I4**|元の関数。<br /><br /> 1 は MDX 関数です。<br /><br /> 2 はユーザー定義関数です。|  
|**インターフェイス**|**DBTYPE_WSTR**|ユーザー定義関数のインターフェイス名。<br /><br /> 多次元式 (MDX) 関数のグループ名。|  
|**LIBRARY_NAME**|**DBTYPE_WSTR**|ユーザー定義関数のタイプ ライブラリ名。 **NULL** MDX 関数です。|  
|**DLL_NAME**|**DBTYPE_WSTR**|(省略可) ユーザー定義関数を実装するアセンブリの名前。<br /><br /> 返します**VT_** MDX 関数です。|  
|**HELP_FILE**|**DBTYPE_WSTR**|(省略可) ユーザー定義関数のヘルプ ドキュメントを含んでいるファイルの名前。<br /><br /> 返します**VT_** MDX 関数です。|  
|**HELP_CONTEXT**|**DBTYPE_I4**|(省略可) この関数のヘルプ コンテキスト ID を返します。|  
|**オブジェクト**|**DBTYPE_WSTR**|(省略可) プロパティが適用されるオブジェクト クラスの汎用的な名前。 たとえば、行セット < level_name > に対応します。メンバー関数が返される"**レベル**"です。<br /><br /> 返します**VT_**ユーザー定義関数、または非プロパティ MDX 関数です。|  
|**キャプション**|**DBTYPE_WSTR**|関数の表示キャプション。|  
  
 行セットが並べ替えられて**原点**、 **INTERFACE_NAME**、 **FUNCTION_NAME**です。  
  
## <a name="restriction-columns"></a>制限の列  
 **MDSCHEMA_FUNCTIONS**行セットは、次の表に示されている列で制限できます。  
  
|列名|型を表すインジケーター|制限の状態|  
|-----------------|--------------------|-----------------------|  
|**LIBRARY_NAME**|**DBTYPE_WSTR**|省略可。|  
|**インターフェイス**|**DBTYPE_WSTR**|省略可。|  
|**FUNCTION_NAME**|**DBTYPE_WSTR**|省略可。|  
|**配信元**|**DBTYPE_I4**|省略可。|  
  
## <a name="see-also"></a>参照  
 [OLE DB for OLAP スキーマ行セット](../../../analysis-services/schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
  