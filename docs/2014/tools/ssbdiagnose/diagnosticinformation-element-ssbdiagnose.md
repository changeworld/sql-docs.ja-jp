---
title: DiagnosticInformation 要素 (ssbdiagnose) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: a6dfc3946f0087b65699968448bdb1c014750572
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48194887"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a>DiagnosticInformation 要素 (ssbdiagnose)
  **DiagnosticInformation** 要素には、ユーティリティによって検出された診断情報を報告するすべての要素が含まれます。 **DiagnosticInformation** は、 **ssbdiagnostic** XML 出力ファイルのルート要素です。  
  
## <a name="syntax"></a>構文  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a>要素の属性  
  
|属性|説明|  
|---------------|-----------------|  
|`None`|なし|  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|**データ型と長さ**|[なし] :|  
|**既定値**|[なし] :|  
|**個数**|**ssbdiagnose** XML 出力ファイルごとに 1 つ。|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|--------------|  
|**親要素**|[なし] :|  
|**子要素**|[Banner 要素&#40;ssbdiagnose&#41;](banner-element-ssbdiagnose.md)<br /><br /> [Issue 要素&#40;ssbdiagnose&#41;](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a>Remarks  
 XML 名前空間の詳細については、 [MSDN Library の「](http://go.microsoft.com/fwlink/?LinkId=7341) XML ドキュメントにおける名前空間 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ssbdiagnose ユーティリティ &#40;Service Broker&#41;](ssbdiagnose-utility-service-broker.md)  
  
  
