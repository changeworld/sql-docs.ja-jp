---
title: 分散スキーマ行セット内のクエリのサポート |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
caps.latest.revision: 28
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b640761d4c88f5a6a93772e12a2249f9f88f28f5
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37419761"
---
# <a name="distributed-query-support-in-schema-rowsets"></a>スキーマ行セットでの分散クエリのサポート
  サポートするために[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]分散クエリ、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダー **IDBSchemaRowset**インターフェイスは、リンク サーバー上のメタデータを返します。  
  
 DBPROPSET_SQLSERVERSESSION の SSPROP_QUOTEDCATALOGNAMES プロパティが VARIANT_TRUE の場合、カタログ名には引用符で囲んだ識別子 ("my.catalog" など) を指定できます。 カタログ、スキーマ行セットの出力を制限する場合、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーは、リンク サーバーとカタログの名前を含む 2 つの部分名を認識します。 次の表に、スキーマ行セットとして 2 つの部分のカタログ名を指定する*linked_server ***.*** カタログ*名前付きのリンク サーバーの適切なカタログへの出力を制限します。  
  
|スキーマ行セット|カタログの制限|  
|-------------------|-------------------------|  
|DBSCHEMA_CATALOGS|CATALOG_NAME|  
|DBSCHEMA_COLUMNS|TABLE_CATALOG|  
|DBSCHEMA_PRIMARY_KEYS|TABLE_CATALOG|  
|DBSCHEMA_TABLES|TABLE_CATALOG|  
|DBSCHEMA_FOREIGN_KEYS|PK_TABLE_CATALOG FK_TABLE_CATALOG|  
|DBSCHEMA_INDEXES|TABLE_CATALOG|  
|DBSCHEMA_COLUMN_PRIVILEGES|TABLE_CATALOG|  
|DBSCHEMA_TABLE_PRIVILEGES|TABLE_CATALOG|  
  
> [!NOTE]  
>  リンク サーバーから、すべてのカタログにスキーマ行セットを制限、構文を使用して、 *linked_server* (ピリオドを区切り文字は名前を指定の一部です)。 この構文は、カタログ名の制限で NULL を指定する場合と同じで、カタログをサポートしないデータ ソースをリンク サーバーが示している場合にも使用されます。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーは、リンク サーバーとして登録されている OLE DB データ ソースの一覧を返す、LINKEDSERVERS スキーマ行セットを定義します。  
  
## <a name="see-also"></a>参照  
 [スキーマ行セットのサポート&#40;OLE DB&#41;](schema-rowset-support-ole-db.md)   
 [LINKEDSERVERS 行セット&#40;OLE DB&#41;](schema-rowsets-linkedservers-rowset.md)  
  
  