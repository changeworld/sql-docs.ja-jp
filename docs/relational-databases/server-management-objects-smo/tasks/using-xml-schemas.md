---
title: "XML スキーマを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
caps.latest.revision: "41"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c80fad3483460d6b0cbb6472c86549bf83219c39
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2017
---
# <a name="using-xml-schemas"></a>XML スキーマの使用方法
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]SMO での XML プログラミングでは、XML データ型、XML 名前空間と XML データ型の列の簡易インデックス作成を提供することに制限されます。  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] XML ドキュメント インスタンスのネイティブ ストレージを提供します。 XML スキーマを使用すると、複雑な XML データ型を定義することができます。これを使用して、XML ドキュメントを検証し、データの整合性を確保することができます。 XML スキーマは、<xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> オブジェクトで定義します。  
  
## <a name="example"></a>例  
 提供されているコード例を使用するには、アプリケーションを作成するプログラミング環境、プログラミング テンプレート、およびプログラミング言語を選択する必要があります。 詳細については、次を参照してください[Visual C &#35; を作成する。Visual Studio .NET での SMO プロジェクト](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md)です。  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a>Visual Basic での XML スキーマの作成  
 このコード例では、<xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> オブジェクトを使用して XML スキーマを作成する方法を示します。 XML スキーマ コレクションを定義する <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> プロパティは、複数の二重引用符記号を格納しています。 これらは `chr(34)` 文字列に置き換えられます。  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server()
'Reference the AdventureWorks2012 2008R2 database.
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Define an XmlSchemaCollection object by supplying the parent database and name arguments in the constructor.
Dim xsc As XmlSchemaCollection
xsc = New XmlSchemaCollection(db, "MySampleCollection")
xsc.Text = "\<schema xmlns=" + Chr(34) + "http://www.w3.org/2001/XMLSchema" + Chr(34) + "  xmlns:ns=" + Chr(34) + "http://ns" + Chr(34) + ">\<element name=" + Chr(34) + "e" + Chr(34) + " type=" + Chr(34) + "dateTime" + Chr(34) + "/></schema>"
'Create the XML schema collection on the instance of SQL Server.
xsc.Create()
```
  
## <a name="creating-an-xml-schema-in-visual-c"></a>Visual C# での XML スキーマの作成  
 このコード例では、<xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> オブジェクトを使用して XML スキーマを作成する方法を示します。 XML スキーマ コレクションを定義する <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> プロパティは、複数の二重引用符記号を格納しています。 これらは `chr(34)` 文字列に置き換えられます。  
  
```csharp  
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "\<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + ">\<element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a>PowerShell での XML スキーマの作成  
 このコード例では、<xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> オブジェクトを使用して XML スキーマを作成する方法を示します。 XML スキーマ コレクションを定義する <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> プロパティは、複数の二重引用符記号を格納しています。 これらは `chr(34)` 文字列に置き換えられます。  
  
```powershell   
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = get-item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
  
  