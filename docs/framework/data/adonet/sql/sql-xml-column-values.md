---
title: SQL-XML-Spaltenwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 8aa33d2c4558c003d1424e118bdf512d4cafaea9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362736"
---
# <a name="sql-xml-column-values"></a>SQL-XML-Spaltenwerte
SQL Server unterstützt die `xml` -Datentyp, und Entwickler können abrufen, einschließlich dieses Typs mithilfe des Standardverhaltens des Resultsets der <xref:System.Data.SqlClient.SqlCommand> Klasse. Eine `xml`-Spalte kann auf die gleiche Weise abgerufen werden wie jede andere Spalte auch (z. B. in einem <xref:System.Data.SqlClient.SqlDataReader>). Wenn Sie jedoch mit dem Inhalt der Spalte in Form von XML-Daten arbeiten möchten, müssen Sie einen <xref:System.Xml.XmlReader> verwenden.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung wählt zwei Zeilen mit jeweils einer `xml` Spalte aus der **Sales.Store** -Tabelle in der **AdventureWorks** -Datenbank auf eine <xref:System.Data.SqlClient.SqlDataReader> Instanz. Der Wert der `xml`-Spalte für jede Zeile wird mit der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gelesen. Der Wert wird in einem <xref:System.Xml.XmlReader> gespeichert. Wenn Sie den Inhalt als <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Variable festlegen möchten, müssen Sie anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode die <xref:System.Data.SqlTypes.SqlXml>-Methode verwenden, denn <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.  
  
> [!NOTE]
>  Die **AdventureWorks** Beispieldatenbank ist bei der Installation von SQL Server nicht standardmäßig installiert. Sie kann jedoch durch Ausführen des Setups von SQL Server installiert werden.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.SqlTypes.SqlXml>  
 [XML-Daten in SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
