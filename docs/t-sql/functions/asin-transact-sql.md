---
title: "ASIN (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ASIN_TSQL
- ASIN
dev_langs:
- TSQL
helpviewer_keywords:
- ASIN function
- sine
- arcsine
ms.assetid: 6256dd7d-83d5-486e-a933-1d59afc7e417
caps.latest.revision: 35
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 1ddfa04e926b4fd0e99455ea91774c31d34b0601
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="asin-transact-sql"></a>ASIN (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

ラジアンでサインの値は、指定された角度を返します**float**式。 これは、アークサイン (逆正弦) とも呼ばれます。
  
![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>構文  
  
```sql
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
ASIN ( float_expression )  
```  
  
## <a name="arguments"></a>引数  
*float_expression*  
[式](../../t-sql/language-elements/expressions-transact-sql.md)型の**float**または float、-1 ~ 1 の値に暗黙的に変換できる型です。 この範囲外の値を指定すると、NULL が返され、ドメイン エラーが発生します。
  
## <a name="return-types"></a>戻り値の型
**float**
  
## <a name="examples"></a>使用例  
次の例は、 **float**式と、指定された角度の ASIN を返します。
  
```sql
/* The first value will be -1.01. This fails because the value is   
outside the range.*/  
DECLARE @angle float  
SET @angle = -1.01  
SELECT 'The ASIN of the angle is: ' + CONVERT(varchar, ASIN(@angle))  
GO  
  
-- The next value is -1.00.  
DECLARE @angle float  
SET @angle = -1.00  
SELECT 'The ASIN of the angle is: ' + CONVERT(varchar, ASIN(@angle))  
GO  
  
-- The next value is 0.1472738.  
DECLARE @angle float  
SET @angle = 0.1472738  
SELECT 'The ASIN of the angle is: ' + CONVERT(varchar, ASIN(@angle))  
GO  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
-------------------------  
.Net SqlClient Data Provider: Msg 3622, Level 16, State 1, Line 3  
A domain error occurred.  
  
---------------------------------   
The ASIN of the angle is: -1.5708                          
  
(1 row(s) affected)  
  
----------------------------------   
The ASIN of the angle is: 0.147811                         
  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>例:[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]と[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
次の例では、1.00 の逆正弦を返します。
  
```sql
SELECT ASIN(1.00) AS asinCalc;  
```  
  
次の例は、許容範囲外の値のアークサインを要求するために、エラーを返します。
  
```sql
SELECT ASIN(1.1472738) AS asinCalc;  
```  
  
## <a name="see-also"></a>参照
[CEILING & #40 です。TRANSACT-SQL と #41 です。](../../t-sql/functions/ceiling-transact-sql.md)  
[数学関数と #40 です。TRANSACT-SQL と #41 です。](../../t-sql/functions/mathematical-functions-transact-sql.md)  
[SET ARITHIGNORE & #40 です。TRANSACT-SQL と #41 です。](../../t-sql/statements/set-arithignore-transact-sql.md)  
[SET ARITHABORT & #40 です。TRANSACT-SQL と #41 です。](../../t-sql/statements/set-arithabort-transact-sql.md)
  
  

