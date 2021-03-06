---
title: getURL メソッド (SQLServerDataSource) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getURL
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: dd0d5d2c-91fe-4b0f-a162-69d898ba176e
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a0f4a7e90ee115470715cf7474a4d05be7a86158
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47755940"
---
# <a name="geturl-method-sqlserverdatasource"></a>getURL メソッド (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  データ ソースへの接続に使用する URL を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public java.lang.String getURL()  
```  
  
## <a name="return-value"></a>戻り値  
 URL を含む**文字列**です。  
  
## <a name="remarks"></a>Remarks  
 セキュリティ上の理由から、[setURL](../../../connect/jdbc/reference/seturl-method-sqlserverdatasource.md) メソッドに渡す URL にはパスワードを含めないでください。 これは、サードパーティの Java アプリケーション サーバーでは、データ ソースの構成用ユーザー インターフェイスに、URL プロパティの値セットが表示されることが非常に多いためです。 パスワードを含める代わりに、[setPassword](../../../connect/jdbc/reference/setpassword-method-sqlserverdatasource.md) メソッドを使用してパスワード値を設定してください。 Java アプリケーション サーバーで、データ ソース内に設定されたパスワードが構成用ユーザー インターフェイスに表示されなくなります。  
  
> [!NOTE]  
>  setURL メソッドを事前に呼び出さずに getURL メソッドを呼び出すと、getURL は既定値の "jdbc:sqlserver://" を返します。  
  
## <a name="see-also"></a>参照  
 [SQLServerDataSource のメンバー](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource クラス](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
