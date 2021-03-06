---
title: Zuordnen von XML-Datentypen zu CLR-Typen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: cabdfcad-f359-479b-b71c-8b2fad42ca49
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d06876b91c72b939768d480e40631a8e85170bc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568541"
---
# <a name="mapping-xml-data-types-to-clr-types"></a>Zuordnen von XML-Datentypen zu CLR-Typen
In der folgenden Tabelle wird die Zuordnung zwischen XML-Datentypen und CLR-Typen (Common Language Runtime) beschrieben.  
  
## <a name="the-following-table-describes-the-default-mappings-of-an-xml-data-type-to-a-clr-type"></a>In der folgenden Tabelle werden die Standardzuordnungen eines XML-Datentyps zu einem CLR-Typ beschrieben.  
  
> [!NOTE]
>  Die Präfixe `xs` und `xdt` sind den Namespace-URIs http://www.w3.org/2001/XMLSchema bzw. http://www.w3.org/2003/05/xpath-datatypes zugeordnet.  
  
|XML-Typ|CLR-Typ|  
|--------------|--------------|  
|`xs:anyURI`|<xref:System.Uri>|  
|`xs:base64Binary`|`Byte[]`|  
|`xs:boolean`|<xref:System.Boolean>|  
|`xs:byte`|<xref:System.SByte>|  
|`xs:date`|<xref:System.DateTime>|  
|`xs:dateTime`|<xref:System.DateTime>|  
|`xs:decimal`|<xref:System.Decimal>|  
|`xs:double`|<xref:System.Double>|  
|`xs:duration`|<xref:System.TimeSpan>|  
|`xs:ENTITIES`|`String[]`|  
|`xs:ENTITY`|<xref:System.String>|  
|`xs:float`|<xref:System.Single>|  
|`xs:gDay`|<xref:System.DateTime>|  
|`xs:gMonthDay`|<xref:System.DateTime>|  
|`xs:gYear`|<xref:System.DateTime>|  
|`xs:gYearMonth`|<xref:System.DateTime>|  
|`xs:hexBinary`|`Byte[]`|  
|`xs:ID`|<xref:System.String>|  
|`xs:IDREF`|<xref:System.String>|  
|`xs:IDREFS`|`String[]`|  
|`xs:int`|<xref:System.Int32>|  
|`xs:integer`|<xref:System.Decimal>|  
|`xs:language`|<xref:System.String>|  
|`xs:long`|<xref:System.Int64>|  
|`xs:gMmonth`|<xref:System.DateTime>|  
|`xs:Name`|<xref:System.String>|  
|`xs:NCName`|<xref:System.String>|  
|`xs:negativeInteger`|<xref:System.Decimal>|  
|`xs:NMTOKEN`|<xref:System.String>|  
|`xs:NMTOKENS`|`String[]`|  
|`xs:nonNegativeInteger`|<xref:System.Decimal>|  
|`xs:nonPositiveInteger`|<xref:System.Decimal>|  
|`xs:normalizedString`|<xref:System.String>|  
|`xs:NOTATION`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:positiveInteger`|<xref:System.Decimal>|  
|`xs:QName`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:short`|<xref:System.Int16>|  
|`xs:string`|<xref:System.String>|  
|`xs:time`|<xref:System.DateTime>|  
|`xs:token`|<xref:System.String>|  
|`xs:unsignedByte`|<xref:System.Byte>|  
|`xs:unsignedInt`|<xref:System.UInt32>|  
|`xs:unsignedLong`|<xref:System.UInt64>|  
|`xs:unsignedShort`|<xref:System.UInt16>|  
|`xdt:dayTimeDuration`|<xref:System.TimeSpan>|  
|`xdt:yearMonthDuration`|<xref:System.TimeSpan>|  
|`xdt:untypedAtomic`|<xref:System.String>|  
|`xdt:anyAtomicType`|<xref:System.Object>|  
|`xs:anySimpleType`|<xref:System.String>|  
|Dokumentknoten|<xref:System.Xml.XPath.XPathNavigator>|  
|Elementknoten|<xref:System.Xml.XPath.XPathNavigator>|  
|Attributknoten|<xref:System.Xml.XPath.XPathNavigator>|  
|Namespaceknoten|<xref:System.Xml.XPath.XPathNavigator>|  
|Textknoten|<xref:System.Xml.XPath.XPathNavigator>|  
|Kommentarknoten|<xref:System.Xml.XPath.XPathNavigator>|  
|Verarbeitungsanweisungsknoten|<xref:System.Xml.XPath.XPathNavigator>|  
  
## <a name="see-also"></a>Siehe auch  
 [Type Support in the System.Xml Classes (Typenunterstützung in den System.Xml-Klassen)](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
