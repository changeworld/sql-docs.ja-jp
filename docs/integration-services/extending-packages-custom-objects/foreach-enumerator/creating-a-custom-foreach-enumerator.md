---
title: "カスタム Foreach 列挙子の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
caps.latest.revision: 53
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: f2f852ff319554d0b863fd06d790c2e5e9bf2d59
ms.contentlocale: ja-jp
ms.lasthandoff: 08/03/2017

---
# <a name="creating-a-custom-foreach-enumerator"></a>カスタム Foreach 列挙子の作成
  カスタム foreach 列挙子の作成手順は、[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] の他のカスタム オブジェクトの作成手順と同様です。  
  
-   基本クラスを継承する新しいクラスを作成します。 foreach 列挙子用の基本クラスは <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> です。  
  
-   クラスに、オブジェクトの種類を識別する属性を適用します。 foreach 列挙子用の属性は <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> です。  
  
-   基本クラスのメソッドとプロパティの実装をオーバーライドします。 foreach 列挙子で、最も重要なのは、<xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> メソッドです。  
  
-   必要に応じて、カスタム ユーザー インターフェイスを開発します。 その場合、foreach 列挙子では、<xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> インターフェイスを実装するクラスが必要です。  
  
 カスタム列挙子は、<xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> コンテナーによってホストされます。 実行時は、<xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> コンテナーが、カスタム列挙子の <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> メソッドを呼び出します。 カスタム列挙子を実装するオブジェクトを返します、 **IEnumerable**インターフェイスなど、 **ArrayList**です。 次に、<xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> はコレクション内の各要素を繰り返し処理し、ユーザー定義変数を介して現在の要素の値を制御フローに渡し、コンテナーの制御フローを実行します。  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a>カスタム ForEach 列挙子の概要  
  
### <a name="creating-projects-and-classes"></a>プロジェクトおよびクラスの作成  
 すべてのマネージ foreach 列挙子は <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> 基本クラスから派生するため、カスタム foreach 列挙子を作成するには、最初に任意のマネージ プログラミング言語でクラス ライブラリ プロジェクトを作成し、基本クラスを継承するクラスを作成します。 この派生クラスで、基本クラスのメソッドとプロパティをオーバーライドして、カスタム機能を実装します。  
  
 同じソリューション内に、もう 1 つのクラス ライブラリ プロジェクトをカスタム ユーザー インターフェイス用に作成します。 配置を容易にするため、ユーザー インターフェイス用に別個のアセンブリを使用することをお勧めします。そうすれば、foreach 列挙子やそのユーザー インターフェイスの更新や再配置を個別に行うことができます。  
  
 どちらのプロジェクトも、アセンブリに署名するよう構成します。アセンブリは、厳密な名前のキー ファイルを使用して、ビルド時に生成されます。  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a>DtsForEachEnumerator 属性の適用  
 作成したクラスに <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> 属性を適用して、そのクラスが foreach 列挙子として識別されるようにします。 この属性は、foreach 列挙子の名前や説明など、デザイン時の情報を表します。 **名前**の使用可能な列挙子のドロップダウン リストにプロパティが表示されます、**コレクション**のタブ、 **Foreach ループ エディター**  ダイアログ ボックス。  
  
 <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> プロパティを使用して、foreach 列挙子をそのカスタム ユーザー インターフェイスにリンクします。 使用して、このプロパティに必要な公開キー トークンを取得する**sn.exe t**を使用して、ユーザー インターフェイス アセンブリに署名するキー ペア (.snk) ファイルから公開キー トークンを表示します。  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a>カスタム列挙子の作成、配置、およびデバッグ  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] でカスタム foreach 列挙子を作成、配置、およびデバッグする手順は、他の種類のカスタム オブジェクトで必要な手順とほとんど同様です。 詳細については、次を参照してください。[構築, Deploying, and Debugging Custom Objects](../../../integration-services/extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md)です。  
  
## <a name="see-also"></a>参照  
 [カスタム Foreach 列挙子のコーディング](../../../integration-services/extending-packages-custom-objects/foreach-enumerator/coding-a-custom-foreach-enumerator.md)   
 [カスタム ForEach 列挙子用ユーザー インターフェイスの開発](../../../integration-services/extending-packages-custom-objects/foreach-enumerator/developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  