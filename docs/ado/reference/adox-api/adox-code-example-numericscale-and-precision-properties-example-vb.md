---
title: NumericScale および Precision プロパティの例 (VB) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- Precision property [ADOX], Visual Basic example
- NumericScale property [ADOX], Visual Basic example
ms.assetid: ea2ec614-34c8-41b7-8ebd-063798bd56b4
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8d4fece6307ff005031e7ab770b14bd5fbca541d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47828492"
---
# <a name="adox-code-example-numericscale-and-precision-properties-example-vb"></a>ADOX のコード例: NumericScale プロパティと Precision プロパティの例 (VB)
この例では、 [NumericScale](../../../ado/reference/adox-api/numericscale-property-adox.md)と[精度](../../../ado/reference/adox-api/precision-property-adox.md)のプロパティ、[列](../../../ado/reference/adox-api/column-object-adox.md)オブジェクト。 このコードは、その値を表示、 **Order Details**のテーブル、 *Northwind*データベース。  
  
```  
' BeginNumericScalePrecVB  
Sub Main()  
    On Error GoTo NumericScalePrecXError  
  
    Dim cnn As New ADODB.Connection  
    Dim cat As New ADOX.Catalog  
    Dim tblOD As ADOX.Table  
    Dim colLoop As ADOX.Column  
  
    ' Connect the catalog.  
    cnn.Open "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
        "data source='Northwind.mdb';"  
    Set cat.ActiveConnection = cnn  
  
    ' Retrieve the Order Details table  
    Set tblOD = cat.Tables("Order Details")  
  
    ' Display numeric scale and precision of  
    ' small integer fields.  
    For Each colLoop In tblOD.Columns  
        If colLoop.Type = adSmallInt Then  
            MsgBox "Column: " & colLoop.Name & vbCr & _  
                "Numeric scale: " & _  
                colLoop.NumericScale & vbCr & _  
                "Precision: " & colLoop.Precision  
        End If  
    Next colLoop  
  
    'Clean up  
    cnn.Close  
    Set cat = Nothing  
    Set cnn = Nothing  
    Exit Sub  
  
NumericScalePrecXError:  
    Set cat = Nothing  
  
    If Not cnn Is Nothing Then  
        If cnn.State = adStateOpen Then cnn.Close  
    End If  
    Set cnn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndNumericScalePrecVB  
```  
  
## <a name="see-also"></a>参照  
 [列オブジェクト (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)   
 [NumericScale プロパティ (ADOX)](../../../ado/reference/adox-api/numericscale-property-adox.md)   
 [Precision プロパティ (ADOX)](../../../ado/reference/adox-api/precision-property-adox.md)
