---
title: SetDefaults メソッド (ServerSettings クラス) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 8454317ff08a4576970c2ffc448605ac5825f1d1
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48080142"
---
# <a name="setdefaults-method-serversettings-class"></a>SetDefaults メソッド (ServerSettings クラス)
  インスタンスのすべての既定値を設定[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]既存のデータを上書きするオプションを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a>要素  
 *object*  
 A [ServerSettings クラス](serversettings-class.md)を表すオブジェクトを[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]クライアント インスタンス。  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|*OverwriteAll*|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] のインスタンス上の既存の値を上書きするかどうかを指定するブール値。既存のデータを上書きするには `true`、既存のデータを上書きしない場合は `false` を指定します。|  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 u`int32` 値。サービスが正常に変更された場合は 0、要求がサポートされない場合は 1 になります。それ以外の数値はエラーを示します。  
  
## <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>参照  
 [サーバー ネットワーク プロトコルとネットワーク ライブラリの構成](http://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
