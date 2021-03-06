---
title: Microsoft JDBC Driver for SQL Server の機能の依存関係 | Microsoft Docs
ms.custom: ''
ms.date: 07/31/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 939a8773-2583-49a4-bf00-6b892fbe39dc
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 01388e48e12a01e18b837cac8e663bf2f52ebe40
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "52502627"
---
# <a name="feature-dependencies-of-the-microsoft-jdbc-driver-for-sql-server"></a>Microsoft JDBC Driver for SQL Server の機能の依存関係

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

この記事では、Microsoft JDBC Driver for SQL Server が依存するライブラリを一覧表示します。 プロジェクトには、次の依存関係が含まれます。

## <a name="compile-time"></a>コンパイル時間

- `azure-keyvault`: (省略可能) 常に暗号化された Azure Key Vault 機能 azure の Key Vault Provider
- `adal4j`: Azure の Active Directory Library for Java を、Azure Active Directory 認証機能と、Azure Key Vault 機能 (省略可能)

## <a name="test-time"></a>テスト時間

上述した機能のいずれかを必要とする特定のプロジェクトは、POM ファイルにそれぞれの依存関係を明示的に宣言する必要があります。

**例:** を再宣言する必要があります、Azure Active Directory 認証機能を使用しているときに、`adal4j`プロジェクトの POM ファイルに依存関係。 次のスニペットを参照してください。

```xml
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>7.0.0.jre10</version>
    <scope>compile</scope>
</dependency>

<dependency>
    <groupId>com.microsoft.azure</groupId>
    <artifactId>adal4j</artifactId>
    <version>1.6.0</version>
</dependency>
```

**例:** Azure Key Vault 機能を使用している場合は、再宣言する必要があります。、`azure-keyvault`依存関係と`adal4j`プロジェクトの POM ファイルに依存関係。 次のスニペットを参照してください。

```xml
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>7.0.0.jre10</version>
    <scope>compile</scope>
</dependency>

<dependency>
    <groupId>com.microsoft.azure</groupId>
    <artifactId>adal4j</artifactId>
    <version>1.6.0</version>
</dependency>

<dependency>
    <groupId>com.microsoft.azure</groupId>
    <artifactId>azure-keyvault</artifactId>
    <version>1.0.0</version>
</dependency>
```

## <a name="dependency-requirements-for-the-jdbc-driver"></a>JDBC Driver の依存関係の要件

### <a name="working-with-the-azure-key-vault-provider"></a>Azure Key Vault プロバイダーの操作。

- JDBC Driver バージョン 7.0.0 - 依存関係のバージョン: Azure-keyvault (バージョン 1.0.0)、Adal4j (バージョン 1.6.0) とその依存関係 ([サンプル アプリケーション](../../connect/jdbc/azure-key-vault-sample-version-7-0-0.md))
- JDBC Driver version 6.4.0 - 依存関係のバージョン: Azure-keyvault (バージョン 1.0.0)、Adal4j (バージョン 1.4.0) とその依存関係 ([サンプル アプリケーション](../../connect/jdbc/azure-key-vault-sample-version-6.2.2.md))
- JDBC Driver version 6.2.2 - 依存関係のバージョン: Azure-keyvault (バージョン 1.0.0)、Adal4j (バージョン 1.4.0) とその依存関係 ([サンプル アプリケーション](../../connect/jdbc/azure-key-vault-sample-version-6.2.2.md))
- JDBC Driver version 6.0.0 - 依存関係のバージョン: Azure-keyvault (バージョン 0.9.7)、Adal4j (バージョン 1.3.0) とその依存関係 ([サンプル アプリケーション](../../connect/jdbc/azure-key-vault-sample-version-6.0.0.md))

> [!NOTE]
> 6.2.2 と 6.4.0 ドライバーのバージョンでは、バージョン 1.0.0 に azure key vault-java 依存関係が更新されました。 ただし、新しいバージョンでは、(0.9.7) 以前のバージョンと互換性がないと、ドライバーに既存の実装を中断します。 ドライバーの新しい実装には、さらに、Azure Key Vault プロバイダーを使用するクライアント プログラムを中断する API の変更が必要です。
>
> この問題は、最新バージョンのドライバー (7.0.0) に解決されます。 認証コールバックのメカニズムを使用する削除されたコンス トラクターは、旧バージョンとの互換性のための Azure Key Vault Provider に追加されます。

### <a name="working-with-azure-active-directory-authentication"></a>Azure Active Directory 認証の操作:

- JDBC Driver バージョン 7.0.0 - 依存関係のバージョン: Ada4j (バージョン 1.6.0) とその依存関係
- JDBC Driver version 6.4.0 - 依存関係のバージョン: Adal4j (バージョン 1.4.0) とその依存関係
- JDBC Driver version 6.2.2 - 依存関係のバージョン: Adal4j (バージョン 1.4.0) とその依存関係
- JDBC Driver version 6.0.0 - 依存関係のバージョン: Adal4j (バージョン 1.3.0) とその依存関係。 このバージョンのドライバーを使用して接続できる_ActiveDirectoryIntegrated_ sqljdbc_auth.dll と Active Directory 認証ライブラリの SQL Server (を使用して Windows オペレーティング システムにのみ、認証モードADALSQL します。DLL) です。

ドライバーのバージョン 6.4.0 から以降、アプリケーションとは限りませんを必要としない ADALSQL を使用します。Windows オペレーティング システムの DLL です。 *非 Windows オペレーティング システム*ドライバーが ActiveDirectoryIntegrated 認証を使用する Kerberos チケットが必要です。 Kerberos を使用して Active Directory に接続する方法の詳細については、次を参照してください。 [Windows、Linux、Mac 上の設定の Kerberos チケット](https://docs.microsoft.com/sql/connect/jdbc/connecting-using-azure-active-directory-authentication#set-kerberos-ticket-on-windows-linux-and-mac)します。

*Windows オペレーティング システム*ドライバーは、既定で sqljdbc_auth.dll の外観し、Kerberos チケットのセットアップや Azure ライブラリの依存関係は必要ありません。 Sqljdbc_auth.dll を使用できない場合、ドライバーは、その他のオペレーティング システムとして Active Directory への認証用の Kerberos チケットを探します。

取得することができます、[サンプル アプリケーション](../../connect/jdbc/connecting-using-azure-active-directory-authentication.md)この機能を使用します。

## <a name="see-also"></a>参照

[JDBC ドライバーの GitHub リポジトリ](https://github.com/microsoft/mssql-jdbc)  
 [JDBC Driver API リファレンス](../../connect/jdbc/reference/jdbc-driver-api-reference.md)
