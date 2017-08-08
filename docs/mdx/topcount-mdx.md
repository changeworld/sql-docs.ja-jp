---
title: "TopCount (MDX) |Microsoft ドキュメント"
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
- TOPCOUNT
dev_langs:
- kbMDX
helpviewer_keywords:
- TopCount function
ms.assetid: 15026a8f-35c5-4307-8856-348f5c44bfd5
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 09b3d169600622822b2d3e5a78ad72c3164efcb9
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="topcount-mdx"></a>TopCount (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  セットを降順に並べ替え、値の大きい方から指定された数の要素を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
TopCount(Set_Expression,Count [ ,Numeric_Expression ] )  
```  
  
## <a name="arguments"></a>引数  
 *Set_Expression*  
 セットを返す有効な多次元式 (MDX) です。  
  
 *Count*  
 返す組の数を指定する有効な数値式です。  
  
 *Numeric_Expression*  
 有効な数値式です。通常は、数値を返すセル座標の多次元式 (MDX) 式です。  
  
## <a name="remarks"></a>解説  
 数値式が指定されている場合、 **TopCount**関数、順序、指定されたセットに対して評価された数値式で指定された値に従って、指定されたセットで指定されたセット内の組を降順で並べ替えます。 セットの並べ替えの後に、 **TopCount**関数では、指定した数の組の最も大きい値を返します。  
  
> [!IMPORTANT]  
>  同様に、 [BottomCount](../mdx/bottomcount-mdx.md) 、関数、 **TopCount**関数が常に階層を解除します。  
  
 数値式が指定されていない場合、関数のセットを返しますメンバー、自然な順序で、並べ替えを行わずと同様の動作、 [Head (MDX)](../mdx/head-mdx.md)関数。  
  
## <a name="examples"></a>使用例  
 次の例では、Internet Sales Amount の上位 10 日を返します。  
  
 `SELECT [Measures].[Internet Sales Amount] ON 0,`  
  
 `TOPCOUNT([Date].[Date].[Date].MEMBERS, 10, [Measures].[Internet Sales Amount])`  
  
 `ON 1`  
  
 `FROM [Adventure Works]`  
  
 次の例では、Bike カテゴリについて、Geography ディメンションの Geography 階層にある City レベルのメンバーのすべての組み合わせと Date ディメンションの Fiscal 階層のすべての会計年度を含んでいるセットを、Reseller Sales Amount メジャーで (最も売上が多いメンバーが 1 番目になるように) 並べ替えて、最初の 5 つのメンバーを返します。  
  
```  
SELECT [Measures].[Reseller Sales Amount] ON 0,  
TopCount  
   ({[Geography].[Geography].[City].Members   
      *[Date].[Fiscal].[Fiscal Year].Members}  
   , 5  
   , [Measures].[Reseller Sales Amount]  
   ) ON 1  
FROM [Adventure Works]  
WHERE([Product].[Product Categories].Bikes)  
```  
  
## <a name="see-also"></a>参照  
 [MDX 関数リファレンス & #40 です。MDX と #41 です。](../mdx/mdx-function-reference-mdx.md)  
  
  
