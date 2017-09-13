---
title: "DBCC USEROPTIONS (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC USEROPTIONS
- DBCC_USEROPTIONS_TSQL
- USEROPTIONS_TSQL
- USEROPTIONS
dev_langs:
- TSQL
helpviewer_keywords:
- DBCC USEROPTIONS statement
- active SET options
- SET statement, active SET options
ms.assetid: 565ab112-7af1-4c18-a579-07cdb332f539
caps.latest.revision: 41
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a94a29317bef21f784d2b0b927577627434ce7d9
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-useroptions-transact-sql"></a>DBCC USEROPTIONS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

現在の接続でアクティブになっている (設定されている) SET オプションを返します。
  
![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>構文  
  
```sql
DBCC USEROPTIONS  
[ WITH NO_INFOMSGS ]  
```  
  
## <a name="arguments"></a>引数  
NO_INFOMSGS  
重大度レベル 0 から 10 のすべての情報メッセージを表示しないようにします。
  
## <a name="result-sets"></a>結果セット  
DBCC USEROPTIONS は、SET オプションの名前の列とオプションの値の列を返します (値とエントリは状況に応じて異なります)。

```sql

| `Set Option                   Value`  
 `---------------------------- ---------------------------`  
 `textsize                     64512`  
 `language                     us_english`  
 `dateformat                   mdy`  
 `datefirst                    7`  
 `lock_timeout                 -1`  
 `quoted_identifier            SET`  
 `arithabort                   SET`  
 `ansi_null_dflt_on            SET`  
 `ansi_warnings                SET`  
 `ansi_padding                 SET`  
 `ansi_nulls                   SET`  
 `concat_null_yields_null      SET`  
 `isolation level              read committed`  
 `(13 row(s) affected)`  
 `DBCC execution completed. If DBCC printed error messages, contact your system administrator.`
 ```  
  
## <a name="remarks"></a>解説  
READ_COMMITTED_SNAPSHOT データベース オプションが ON に設定され、トランザクション分離レベルが "READ COMMITTED" に設定されている場合、DBCC USEROPTIONS は、"READ COMMITTED スナップショット" の分離レベルを報告します。 実際の分離レベルは READ COMMITTED です。
  
## <a name="permissions"></a>Permissions  
ロール **public** のメンバーシップが必要です。
  
## <a name="examples"></a>使用例  
次の例は、現在の接続のアクティブな SET オプションを返します。
  
```sql  
DBCC USEROPTIONS;  
```  
  
## <a name="see-also"></a>参照  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[SET ステートメント &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
[SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md)
  
  
