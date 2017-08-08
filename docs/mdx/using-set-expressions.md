---
title: "セット式の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- expressions [MDX], set
- tuples
- set expressions [MDX]
ms.assetid: 88d65872-0cbe-4c95-b36f-e1aa4ac8ed07
caps.latest.revision: 28
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: a8298983c864384254dead4cecd0ef156617db2b
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="using-set-expressions"></a>セット式の使用
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  セットは、0 個以上の組の順序付けされた一覧で構成されます。 組を 1 つも含まないセットは、空のセットと呼ばれます。  
  
 完全なセット式は、中かっこの中に 0 個以上の組を明示的に指定して表します。  
  
 {[{ *Tuple_expression* | *メンバー式*} [、{ *Tuple_expression* | *メンバー式*}]...]}  
  
 セット式の中で指定されたメンバー式は、1 つのメンバーのみの組式に変換されます。  
  
## <a name="example"></a>例  
 次の例では、クエリの COLUMNS 軸と ROWS 軸で使用される 2 つのセット式を示します。  
  
 `SELECT`  
  
 `{[Measures].[Internet Sales Amount], [Measures].[Internet Tax Amount]} ON COLUMNS,`  
  
 `{([Product].[Product Categories].[Category].&[4], [Date].[Calendar].[Calendar Year].&[2004]),`  
  
 `([Product].[Product Categories].[Category].&[1], [Date].[Calendar].[Calendar Year].&[2003]),`  
  
 `([Product].[Product Categories].[Category].&[3], [Date].[Calendar].[Calendar Year].&[2004])}`  
  
 `ON ROWS`  
  
 `FROM [Adventure Works]`  
  
 COLUMNS 軸のセットを次に示します。  
  
 {[Measures].[Internet Sales Amount], [Measures].[Internet Tax Amount]}  
  
 このセットは、Measures ディメンションの 2 つのメンバーで構成されています。 ROWS 軸のセットを次に示します。  
  
 {([Product].[Product Categories].[Category].&[4], [Date].[Calendar].[Calendar Year].&[2004]),  
  
 ([Product].[Product Categories].[Category].&[1], [Date].[Calendar].[Calendar Year].&[2003]),  
  
 ([Product].[Product Categories].[Category].&[3], [Date].[Calendar].[Calendar Year].&[2004])}  
  
 このセットは 3 つの組で構成されており、それぞれの組には、Product ディメンションの Product Categories 階層のメンバーと Date ディメンションの Calendar 階層のメンバーへの、2 つの明示的な参照が含まれています。  
  
 セットを返す関数の例については、次を参照してください[メンバー、組、およびセット &#40; の操作。MDX と #41 です。](../analysis-services/multidimensional-models/mdx/working-with-members-tuples-and-sets-mdx.md).  
  
## <a name="see-also"></a>参照  
 [式 & #40 です。MDX と #41 です。](../mdx/expressions-mdx.md)  
  
  
