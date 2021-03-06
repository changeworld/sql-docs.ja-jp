---
title: CAB は、SQL Server の累積的更新プログラムのダウンロード |マイクロソフトのドキュメント
description: SQL Server 2017 Machine Learning Services と SQL Server 2016 R Services の CAB のダウンロード。
ms.prod: sql
ms.technology: machine-learning
ms.date: 10/01/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: 25568dc5a76283b18affd10ef0419f83515f6403
ms.sourcegitcommit: 615f8b5063aed679495d92a04ffbe00451d34a11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48232606"
---
# <a name="cab-downloads-for-cumulative-updates-of-sql-server-in-database-analytics-instances"></a>インスタンスの SQL Server データベース内分析の累積的更新プログラム用 CAB のダウンロードします。

データベース内分析が構成されている SQL Server インスタンスには、R と Python の機能が含まれます。 これらの機能を出荷を CAB ファイル、インストールされているし、SQL Server セットアップでサービスを提供します。 インターネットに接続されたデバイスで、通常は Windows Update を通じてに CAB の更新が適用されます。 切断されたサーバーは、CAB ファイルをダウンロードして手動で適用する必要があります。 

この記事では、各累積更新プログラム用の CAB ファイルのダウンロード リンクを提供します。 SQL Server 2017 Machine Learning サービス (R および Python) と SQL Server 2016 R Services の両方のリンクを示します。 オフライン インストールの詳細については、次を参照してください。 [SQL Server をインストールした機械学習のインターネット アクセスなしでコンポーネントを](sql-ml-component-install-without-internet-access.md#apply-cu)します。

## <a name="prerequisites"></a>前提条件

ベースライン インストールで開始します。

+ SQL Server 2017 Machine Learning Services では、最初のリリースは、基準インストールです。 
+ SQL Server 2016 R Services では、最初のリリース、SP1、または sp2 が適用を開始できます。 

スタンドアロン サーバーに累積的更新プログラムを適用することもできます。

## <a name="sql-server-2017-cabs"></a>SQL Server 2017 の cab ファイル

CAB ファイルは、逆時系列順に表示されます。 CAB ファイルをダウンロードしたり、ターゲット コンピューターに転送すると、フォルダーに配置する便利ななど**ダウンロード**またはセットアップのユーザーの %temp% フォルダー。

リリース  |ダウンロード リンク  | 解決された問題 | 
---------|---------------|-------|
**[SQL Server 2017 CU10](https://support.microsoft.com/help/4342123)-[CU11](https://support.microsoft.com/help/4462262)** |  |  |
Microsoft R Open     | [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)| 以前のバージョンから変更はありません。 |
R Server      |[SRS_9.2.0.1000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=2006287&clcid=1033)| 小さな修正。|
Microsoft Python のオープン     | [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)| 以前のバージョンから変更はありません。 |
Python のサーバー    |[SPS_9.2.0.1000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=2006805&clcid=1033)| Python rx_data_step では、重複が削除されたときに、行の順序が失われます。 <br/>速度では、クラスター化列ストア インデックスのデータ型の検出が失敗します。 <br/>列には、すべての null 値が含まれている場合は、空のテーブルを返します。 |
**[SQL Server 2017 CU8](https://support.microsoft.com/help/4338363)-[CU9](https://support.microsoft.com/help/4341265)** |  |  |
Microsoft R Open     | [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)| 以前のバージョンから変更はありません。 |
R Server      |[SRS_9.2.0.800_1033.cab](https://go.microsoft.com/fwlink/?LinkId=874708&clcid=1033)|
Microsoft Python のオープン     | [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)| 以前のバージョンから変更はありません。 |
Python のサーバー    |[SPS_9.2.0.800_1033.cab](https://go.microsoft.com/fwlink/?LinkId=874707&clcid=1033)|
**[SQL Server 2017 CU6](https://support.microsoft.com/help/4101464)-[cu7 以降](https://support.microsoft.com/help/4229789)** |  |  |
Microsoft R Open     | [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)| 以前のバージョンから変更はありません。 |
R Server      |[SRS_9.2.0.600_1033.cab](https://go.microsoft.com/fwlink/?LinkId=871074&clcid=1033)|
Microsoft Python のオープン     | [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)| 以前のバージョンから変更はありません。 |
Python のサーバー    |[SPS_9.2.0.600_1033.cab](https://go.microsoft.com/fwlink/?LinkId=871073&clcid=1033)| SPEES クエリでの DateTime データ型。<br/>microsoftml のエラー メッセージは、事前トレーニング済みモデルが存在しない場合に向上します。<br/> Revoscalepy に修正プログラムは、関数および変数を変換します。|
**[SQL Server 2017 CU5](https://support.microsoft.com/help/4092643)** |  |  |
Microsoft R Open     | [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)| 以前のバージョンから変更はありません。 |
R Server      |[SRS_9.2.0.500_1033.cab](https://go.microsoft.com/fwlink/?LinkId=869052&clcid=1033)| RxInstallPackages で時間の長いパスに関連するエラー。<br/>RxExec のループバックに接続します。
Microsoft Python のオープン    | 以前のバージョンから変更はありません。 |
Python のサーバー    |[SPS_9.2.0.500_1033.cab](https://go.microsoft.com/fwlink/?LinkId=869053&clcid=1033)| <br/>Rx_exec のループバックに接続します。
**[SQL Server 2017 CU4](https://support.microsoft.com/help/4056498)** |  |   |
Microsoft R Open     | [SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)| 以前のバージョンから変更はありません。 |
R Server      |[SRS_9.2.0.400_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866212&clcid=1033)|
Microsoft Python のオープン     |[SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)| 以前のバージョンから変更はありません。 |
 Python のサーバー    |[SPS_9.2.0.400_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866213&clcid=1033)|
**[SQL Server 2017 CU3](https://support.microsoft.com/help/4052987)** |  |  |
Microsoft R Open     |[SRO_3.3.3.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863894)|
R Server      |[SRS_9.2.0.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863893)|
Microsoft Python のオープン     |[SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)| 以前のバージョンから変更はありません。 |
Python のサーバー    |[SPS_9.2.0.300_1033.cab](https://go.microsoft.com/fwlink/?LinkId=863892)| Python モデルの revoscalepy でのシリアル化を使用して、 [rx_serialize_model 関数](https://docs.microsoft.com/machine-learning-server/python-reference/revoscalepy/rx-serialize-model)します。<br/>[ネイティブ スコアリング](../sql-native-scoring.md)サポート、plus の機能強化[リアルタイム スコアリング](../real-time-scoring.md)します。 
**SQL Server 2017 [CU1](https://support.microsoft.com/help/4038634)-[CU2](https://support.microsoft.com/help/4052574)** |  |  |
Microsoft R Open     | [SRO_3.3.3.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851496)| 以前のバージョンから変更はありません。 |
R Server      |[SRS_9.2.0.100_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851501)|
Microsoft Python のオープン     | [SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502)| 以前のバージョンから変更はありません。 | 
Python のサーバー    |[SPS_9.2.0.100_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851500) | スキーマ情報を返す rx_create_col_info を追加します。 <br/>機能強化[rx_exec](https://docs.microsoft.com/machine-learning-server/python-reference/revoscalepy/rx-exec)を使用して並列のシナリオをサポートするために、`RxLocalParallel`コンピューティング コンテキスト。|
**最初のリリース** |  |  |
Microsoft R Open     |[SRO_3.3.3.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851496)|
R Server      |[SRS_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851507)|
Microsoft Python のオープン     |[SPO_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851502) |
Python のサーバー    |[SPS_9.2.0.24_1033.cab](https://go.microsoft.com/fwlink/?LinkId=851508) |


<a name="bkmk_2016Installers"></a>

## <a name="sql-server-2016-cabs"></a>SQL Server 2016 の cab ファイル

SQL Server 2016 R Services では、ベースライン リリースは、RTM バージョンまたは service pack のバージョンです。

リリース  |ダウンロード リンク  |
---------|---------------|
**SQL Server 2016 SP2 CU1-CU2**     |
Microsoft R Open     |[SRO_3.2.2.20000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866039)|
Microsoft R Server    |[SRS_8.0.3.20000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=866038)|
**SQL Server 2016 SP1 CU4-CU10**     |
Microsoft R Open     |[SRO_3.2.2.16000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=836819)|
Microsoft R Server    |[SRS_8.0.3.17000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=850317)
**SQL Server 2016 SP1 CU1-CU3**     |
Microsoft R Open     |[SRO_3.2.2.16000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=836819)|
Microsoft R Server    |[SRS_8.0.3.16000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=836818)|
**SQL Server 2016 SP1**     |
Microsoft R Open     |[SRO_3.2.2.15000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=824879)
Microsoft R Server     |[SRS_8.0.3.15000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=824881)
**SQL Server 2016 CU4-CU9**     |
Microsoft R Open     |[SRO_3.2.2.13000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=831785)|
Microsoft R Server     |[SRS_8.0.3.13000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=831676)|
**SQL Server 2016 CU2-CU3**     |
Microsoft R Open     |[SRO_3.2.2.12000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=827398)
Microsoft R Server     |[SRS_8.0.3.12000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=827399)
**SQL Server 2016 CU1**     |
Microsoft R Open     |[SRO_3.2.2.10000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=808803)
Microsoft R Server     |[SRS_8.0.3.10000_1033.cab](https://go.microsoft.com/fwlink/?LinkId=808805)
**SQL Server 2016 RTM**     |
Microsoft R Open     |[SRO_3.2.2.803_1033.cab](https://go.microsoft.com/fwlink/?LinkId=761266)
Microsoft R Server     |[SRS_8.0.3.0_1033.cab](https://go.microsoft.com/fwlink/?LinkId=735051)

> [!NOTE]
> 
> SQL Server 2016 SP1 CU4、または SP1 CU5 のオフライン インストール、SRO_3.2.2.16000_1033.cab をダウンロードします。 FWLINK 831785 から、[設定] ダイアログ ボックスに記載されている SRO_3.2.2.13000_1033.cab をダウンロードした場合は、累積更新プログラムをインストールする前に SRO_3.2.2.16000_1033.cab としてファイルを変更します。

.Tar 形式のアーカイブとしてダウンロードできますが、Microsoft R のソース コードを表示する場合は、: [R Server のダウンロードのインストーラー](https://docs.microsoft.com/machine-learning-server/install/r-server-install-windows#download)

## <a name="see-also"></a>関連項目

[インターネットにアクセスできないコンピューターでの累積的更新プログラムを適用します。](sql-ml-component-install-without-internet-access.md#apply-cu)

[インターネットに接続しているコンピューターでの累積的更新プログラムを適用します。](sql-ml-component-install-without-internet-access.md#apply-cu)

[スタンドアロン サーバーに累積的更新プログラムを適用します。](sql-machine-learning-standalone-windows-install.md#apply-cu)
