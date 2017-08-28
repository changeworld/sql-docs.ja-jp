---
title: ": (範囲) (MDX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ':'
dev_langs:
- kbMDX
helpviewer_keywords:
- ': (range operator)'
- range operator (:)
ms.assetid: f9b36aca-4efd-49b4-9e4f-12914c1b24a6
caps.latest.revision: 37
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: b80f453f0553404d1d337e15e9194f7d4b97ccd7
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="-range-mdx"></a>: (範囲) (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  自然な順序で並べたセットを返すセット演算を実行します。指定された 2 つのメンバーが終端になり、その 2 つのメンバーの間にあるすべてのメンバーがセットのメンバーに含まれます。  
  
## <a name="syntax"></a>構文  
  
```  
  
Member_Expression : Member_Expression      
```  
  
#### <a name="parameters"></a>パラメーター  
 *メンバー式*  
 メンバーを 1 つ返す有効な多次元式 (MDX) 式です。  
  
## <a name="return-value"></a>戻り値  
 指定されているメンバーと、指定されているメンバーの間にあるすべてのメンバーを含むセットです。  
  
## <a name="remarks"></a>解説  
 両方のパラメーターに、ディメンションの同じレベルと同じ階層にあるメンバーを指定する必要があります。 両方のパラメーターが、同じメンバーを指定した場合、 **: (範囲)**演算子が指定されたメンバーのみを含むセットを返します。 最初のパラメーターが NULL の場合、2 番目のパラメーターで指定されたメンバーのレベルの、最初のメンバーからその指定されたメンバー (その指定されたメンバーを含む) までのすべてのメンバーがセットに含まれます。 2 番目のパラメーターが NULL の場合、最初のパラメーターで指定されたメンバーから同じレベルの最後のメンバー (最後のメンバーを含む) までのすべてのメンバーがセットに含まれます。  
  
 MDX にこのセット演算子と等価な関数はありません。  
  
## <a name="examples"></a>使用例  
 この演算子の使用例を以下に示します。  
  
```  
-- This query returns the freight cost per user  
-- for products, averaged by month, for the first quarter.  
With Member [Measures].[Freight Per Customer] as  
 (  
     [Measures].[Internet Freight Cost]  
     /   
     [Measures].[Customer Count]  
)  
  
SELECT   
    {[Ship Date].[Calendar].[Month].&[2004]&[1] : [Ship Date].[Calendar].[Month].&[2004]&[3]} ON 0,  
    [Product].[Category].[Category].Members ON 1  
FROM  
    [Adventure Works]  
WHERE  
    ([Measures].[Freight Per Customer])  
```  
  
## <a name="see-also"></a>参照  
 [MDX 演算子リファレンス & #40 です。MDX と #41 です。](../mdx/mdx-operator-reference-mdx.md)  
  
  
