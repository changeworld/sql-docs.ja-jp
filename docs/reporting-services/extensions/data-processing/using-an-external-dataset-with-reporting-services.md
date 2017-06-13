---
title: "Reporting Services で、外部データセットの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DataSet objects [Reporting Services]
- data processing extensions [Reporting Services], custom DataSet objects
- custom DataSet objects [Reporting Services]
- external DataSet objects [Reporting Services]
ms.assetid: 11daa013-ec17-4760-80e3-6d84cd8d5722
caps.latest.revision: 49
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 1521035e49494a2e183ea35a6ad981a710ff52ff
ms.contentlocale: ja-jp
ms.lasthandoff: 06/13/2017

---
# <a name="using-an-external-dataset-with-reporting-services"></a>Reporting Services での外部データセットの使用
  **データセット**切断されると、オブジェクトがサポートするサーバーの全体の分散データ シナリオを[!INCLUDE[vstecado](../../../includes/vstecado-md.md)]です。 **データセット**オブジェクトは、データ ソースに関係なく一貫したリレーショナル プログラミング モデルを提供するデータのメモリ常駐型の表現。 また、複数の異なるデータ ソースや XML データで使用でき、アプリケーションのデータをローカルに管理することも可能です。 **データセット**オブジェクトが関連するテーブル、制約、およびテーブル間のリレーションシップを含む、データの完全なセットを表します。 ため、**データセット**を格納し、データのデータを公開するオブジェクトの用途のためには多くの場合、処理およびに変換する**データセット**オブジェクトに関するレポートをそのデータの発生前にします。  
  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]データ処理拡張機能を統合でき、任意のカスタム**データセット**外部アプリケーションによって作成されるオブジェクト。 カスタム データ処理拡張機能を作成するためには、[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]間の仲介役となる、**データセット**オブジェクトとレポート サーバー。 これを処理するためのコードのほとんど**データセット**にオブジェクトが含まれている、 **DataReader**を作成するクラス。  
  
 公開するには、まず、**データセット**、レポート サーバーにオブジェクトが、プロバイダー固有のメソッドを実装するには、 **DataReader**読み込むことができるクラス、**データセット**オブジェクト。 次の例は、静的データを読み込む方法を示しています、**データセット**オブジェクト プロバイダーに固有のメソッドを使用して、 **DataReader**クラスです。  
  
```vb  
'Private members of the DataReader class  
Private m_dataSet As System.Data.DataSet  
Private m_currentRow As Integer  
  
'Method to create a dataset  
Friend Sub CreateDataSet()  
   ' Create a dataset.  
   Dim ds As New System.Data.DataSet("myDataSet")  
   ' Create a data table.   
   Dim dt As New System.Data.DataTable("myTable")  
   ' Create a data column and set various properties.   
   Dim dc As New System.Data.DataColumn()  
   dc.DataType = System.Type.GetType("System.Decimal")  
   dc.AllowDBNull = False  
   dc.Caption = "Number"  
   dc.ColumnName = "Number"  
   dc.DefaultValue = 25  
   ' Add the column to the table.   
   dt.Columns.Add(dc)  
   ' Add 10 rows and set values.   
   Dim dr As System.Data.DataRow  
   Dim i As Integer  
   For i = 0 To 9  
      dr = dt.NewRow()  
      dr("Number") = i + 1  
      ' Be sure to add the new row to the DataRowCollection.   
      dt.Rows.Add(dr)  
   Next i  
  
   ' Fill the dataset.  
   ds.Tables.Add(dt)  
  
   ' Use a private variable to store the dataset in your  
   ' DataReader.  
   m_dataSet = ds  
  
   ' Set the current row to -1.  
   m_currentRow = - 1  
End Sub 'CreateDataSet  
```  
  
```csharp  
// Private members of the DataReader class  
private System.Data.DataSet m_dataSet;  
private int m_currentRow;  
  
// Method to create a dataset  
internal void CreateDataSet()  
{  
   // Create a dataset.  
   System.Data.DataSet ds = new System.Data.DataSet("myDataSet");  
   // Create a data table.   
   System.Data.DataTable dt = new System.Data.DataTable("myTable");  
   // Create a data column and set various properties.   
   System.Data.DataColumn dc = new System.Data.DataColumn();   
   dc.DataType = System.Type.GetType("System.Decimal");   
   dc.AllowDBNull = false;   
   dc.Caption = "Number";   
   dc.ColumnName = "Number";   
   dc.DefaultValue = 25;   
   // Add the column to the table.   
   dt.Columns.Add(dc);   
   // Add 10 rows and set values.   
   System.Data.DataRow dr;   
   for(int i = 0; i < 10; i++)  
   {   
      dr = dt.NewRow();   
      dr["Number"] = i + 1;   
      // Be sure to add the new row to the DataRowCollection.   
      dt.Rows.Add(dr);  
   }  
  
   // Fill the dataset.  
   ds.Tables.Add(dt);  
  
   // Use a private variable to store the dataset in your  
   // DataReader.  
   m_dataSet = ds;  
  
   // Set the current row to -1.  
   m_currentRow = -1;  
}  
```  
  
```csharp  
public bool Read()  
{  
   m_currentRow++;  
   if (m_currentRow >= m_dataSet.Tables[0].Rows.Count)   
   {  
      return (false);  
   }   
   else   
   {  
      return (true);  
   }  
}  
  
public int FieldCount  
{  
   // Return the count of the number of columns, which in  
   // this case is the size of the column metadata  
   // array.  
   get { return m_dataSet.Tables[0].Columns.Count; }  
}  
  
public string GetName(int i)  
{  
   return m_dataSet.Tables[0].Columns[i].ColumnName;  
}  
  
public Type GetFieldType(int i)  
{  
   // Return the actual Type class for the data type.  
   return m_dataSet.Tables[0].Columns[i].DataType;  
}  
  
public Object GetValue(int i)  
{  
   return m_dataSet.Tables[0].Rows[m_currentRow][i];  
}  
  
public int GetOrdinal(string name)  
{  
   // Look for the ordinal of the column with the same name and return it.  
   // Returns -1 if not found.  
   return m_dataSet.Tables[0].Columns[name].Ordinal;  
}  
```  
  
 を作成するか、データセットを取得するを使用して、**データセット**の実装にオブジェクト、**読み取り**、 **GetValue**、 **GetName**、 **GetOrdinal**、 **GetFieldType**、および**FieldCount**のメンバー、 **DataReader**クラスです。  
  
## <a name="see-also"></a>参照  
 [Reporting Services 拡張機能](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [データ処理拡張機能の実装](../../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)   
 [Reporting Services 拡張機能ライブラリ](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  