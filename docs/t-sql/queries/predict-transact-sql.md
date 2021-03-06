---
title: PREDICT (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 11/06/2018
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: ''
ms.topic: language-reference
f1_keywords:
- PREDICT
- PREDICT_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- PREDICT clause
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: '>=sql-server-2017||=azuresqldb-current||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: b95f966b27db3638aae6455dc5e7819f07d0ebae
ms.sourcegitcommit: 50b60ea99551b688caf0aa2d897029b95e5c01f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51695460"
---
# <a name="predict-transact-sql"></a>PREDICT (Transact-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-asdb-xxxx-xxx-md.md)]

格納されているモデルに基づいて予測値やスコアを生成します。  

## <a name="syntax"></a>構文

```
PREDICT  
(  
  MODEL = @model | model_literal,  
  DATA = object AS <table_alias>  
)  
WITH ( <result_set_definition> )  

<result_set_definition> ::=  
  {  
    { column_name  
      data_type  
      [ COLLATE collation_name ]  
      [ NULL | NOT NULL ]  
    }  
      [,...n ]  
  }  

MODEL = @model | model_literal  
```

### <a name="arguments"></a>引数

**model**

`MODEL` パラメーターは、スコア付けまたは予測に使用するモデルを指定するために使用されます。 モデルは、変数、リテラル、またはスカラー式として指定されます。

モデル オブジェクトは、R、Python または他のツールを使用して作成できます。

**data**

DATA パラメーターは、スコア付けまたは予測に使用するモデルを指定するために使用されます。 データは、クエリ内でテーブル ソースの形式で指定されます。 テーブル ソースには、テーブル、テーブルの別名、CTE の別名、ビュー、またはテーブル値関数のいずれかを指定できます。

**parameters**

PARAMETERS パラメーターは、スコア付けまたは予測に使用される省略可能なユーザー定義のパラメーターを指定するために使用されます。

各パラメーターの名前は、モデルの種類に固有です。 たとえば、RevoScaleR の [rxPredict](https://docs.microsoft.com/machine-learning-server/r-reference/revoscaler/rxpredict) 関数は、パラメーター `@computeResiduals` をサポートしています。これは、ロジスティック回帰モデルのスコア付け時に残差を計算するかどうかを示します。 互換性のあるモデルを呼び出している場合、そのパラメーター名と TRUE または FALSE 値を `PREDICT` 関数に渡すことができます。

**WITH ( <result_set_definition> )**

WITH 句は、`PREDICT` 関数によって返される出力のスキーマを指定するのに使用されます。

`PREDICT` 関数自体から返される列に加え、データ入力の一部であるすべての列がクエリで使用できます。

### <a name="return-values"></a>戻り値

定義済みのスキーマは使用できません。SQL Server では、モデルのコンテンツも返された列の値も検証しません。

- `PREDICT` 関数は入力として列を通過します。
- `PREDICT` 関数では、新しい列も生成されますが、列の数とそのデータ型は、予測に使用されたモデルの種類に依存します。

データ、モデル、または列形式に関連するすべてのエラー メッセージは、モデルに関連付けられている基になる予測関数から返されます。

- RevoScaleR の場合、同等の関数は [rxPredict](https://docs.microsoft.com/machine-learning-server/r-reference/revoscaler/rxpredict)  
- MicrosoftML の場合、同等の関数は [rxPredict.mlModel](https://docs.microsoft.com/machine-learning-server/r-reference/microsoftml/rxpredict)  

`PREDICT` を使用してモデルの内部構造を表示することはできません。 モデル自体のコンテンツを理解するには、モデル オブジェクトを読み込み、逆シリアル化し、適切な R コードを使用してモデルを解析する必要があります。

## <a name="remarks"></a>Remarks

`PREDICT` 関数は、SQL Server 2017 以降のすべてのエディションでサポートされています。 このサポートには、SQL Server 2017 on Linux が含まれます。 `PREDICT` は、クラウドの Azure SQL Database でもサポートされます。 これらのサポートはすべて、他の機械学習機能が有効になっているかどうかに関係なく機能します。

`PREDICT` 関数を使用するサーバーに、R、Python、または別の機械学習言語をインストールする必要はありません。 別の環境でモデルをトレーニングし、`PREDICT` で使用するためにそれを SQL Server テーブルに保存することも、保存されたモデルがある SQL Server の別のインスタンスからモデルを呼び出すこともできます。

### <a name="supported-algorithms"></a>サポートされているアルゴリズム

使用するモデルは、RevoScaleR パッケージからサポートされているアルゴリズムのいずれかを使用して作成されている必要があります。 現在サポートされているモデルの一覧は、「[リアルタイム スコアリング](../../advanced-analytics/real-time-scoring.md)」を参照してください。

### <a name="permissions"></a>アクセス許可

`PREDICT` にはアクセス許可は必要ありませんが、ユーザーは、データベースに対する `EXECUTE` アクセス許可と、入力として使用される任意のデータをクエリするためのアクセス許可が必要です。 モデルがテーブルに格納されている場合、ユーザーはテーブルからモデルを読み込める必要もあります。

## <a name="examples"></a>使用例

次の例は、`PREDICT` を呼び出す構文を示しています。

### <a name="call-a-stored-model-and-use-it-for-prediction"></a>格納されているモデルを呼び出し、それを予測に使用する

この例では、テーブル [models_table] に格納されている既存のロジスティック回帰モデルを呼び出します。 SELECT ステートメントを使用して、最新のトレーニング済みモデル取得してから、バイナリ モデルを PREDICT 関数に渡します。 入力値は機能を表します。出力は、モデルによって割り当てられた分類を表します。

```sql
DECLARE @logit_model varbinary(max) = "SELECT TOP 1 [model_binary] from [models_table] ORDER BY [trained_date] DESC";
DECLARE @input_qry = "SELECT ID, [Gender], [Income] from NewCustomers";

SELECT PREDICT [class]
FROM PREDICT( MODEL = @logit_model,  DATA = @input_qry)
WITH (class string);
```

### <a name="using-predict-in-a-from-clause"></a>FROM 句で PREDICT を使用する

この例では、`SELECT` ステートメントの `FROM` 句内の `PREDICT` 関数を参照します。

```sql
SELECT d.*, p.Score
FROM PREDICT(MODEL = @logit_model, 
  DATA = dbo.mytable AS d) WITH (Score float) AS p;
```

`DATA` パラメーターでテーブル ソースに指定された別名 **d** は、dbo.mytable に属する列を参照するために使用されます。 **PREDICT** 関数に指定された別名 **p** は、PREDICT 関数によって返される列を参照するために使用されます。

### <a name="combining-predict-with-an-insert-statement"></a>PREDICT を INSERT ステートメントと結合する

予測の一般的なユース ケースの 1 つは、入力データ用のスコアを生成してから、予測された値をテーブルに挿入することです。 次の例では、呼び出し元のアプリケーションがストアド プロシージャを使用して予測値を含む行をテーブルに挿入することを前提としています。

```sql
CREATE PROCEDURE InsertLoanApplication
(@p1 varchar(100), @p2 varchar(200), @p3 money, @p4 int)
AS
BEGIN
  DECLARE @model varbinary(max) = (select model
  FROM scoring_model
  WHERE model_name = 'ScoringModelV1');
  WITH d as ( SELECT * FROM (values(@p1, @p2, @p3, @p4)) as t(c1, c2, c3, c4) )

  INSERT INTO loan_applications (c1, c2, c3, c4, score)
  SELECT d.c1, d.c2, d.c3, d.c4, p.score
  FROM PREDICT(MODEL = @model, DATA = d) WITH(score float) as p;
END;
```

プロシージャが、テーブル値パラメーターを通じて複数の行を受け取る場合、次のように記述できます。

```sql
CREATE PROCEDURE InsertLoanApplications (@new_applications dbo.loan_application_type)
AS
BEGIN
  DECLARE @model varbinary(max) = (SELECT model_bin FROM scoring_models WHERE model_name = 'ScoringModelV1');
  INSERT INTO loan_applications (c1, c2, c3, c4, score)
  SELECT d.c1, d.c2, d.c3, d.c4, p.score
  FROM PREDICT(MODEL = @model, DATA = @new_applications as d)
  WITH (score float) as p;
END;
```

### <a name="creating-an-r-model-and-generating-scores-using-optional-model-parameters"></a>省略可能なモデル パラメーターを使用して、R モデルを作成しスコアを生成する

この例では、次のような RevoScaleR への呼び出しを使用して、共分散マトリックスと一致するロジスティック回帰モデルを作成していることを前提としています。

```R
logitObj <- rxLogit(Kyphosis ~ Age + Start + Number, data = kyphosis, covCoef = TRUE)
```

モデルをバイナリ形式で SQL Server に格納する場合は、PREDICT 関数を使用して、予測だけでなく、モデルの種類でサポートされている、エラーや信頼区間などの追加の情報も生成することができます。

次のコードは、R から [rxPredict](https://docs.microsoft.com/machine-learning-server/r-reference/revoscaler/rxpredict) への同等の呼び出しです。

```R
rxPredict(logitObj, data = new_kyphosis_data, computeStdErr = TRUE, interval = "confidence")
```

`PREDICT` 関数を使用した同等の呼び出しでは、スコア (予測値)、エラー、および信頼区間も提供されます。

```sql
SELECT d.Age, d.Start, d.Number, p.pred AS Kyphosis_Pred, p.stdErr, p.pred_lower, p.pred_higher
FROM PREDICT( MODEL = @logitObj,  DATA = new_kyphosis_data AS d,
  PARAMETERS = N'computeStdErr bit, interval varchar(30)',
  computeStdErr = 1, interval = 'confidence')
WITH (pred float, stdErr float, pred_lower float, pred_higher float) AS p;
```
