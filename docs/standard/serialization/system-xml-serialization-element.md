---
title: '&lt;system.xml.serialization&gt;-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: e26a12facb92147d7660ae266ea5e1b090d7e198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583772"
---
# <a name="ltsystemxmlserializationgt-element"></a>&lt;system.xml.serialization&gt;-Element
Das Element der obersten Ebene zur Steuerung der XML-Serialisierung. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<dateTimeSerialization>-Element](../../../docs/standard/serialization/datetimeserialization-element.md)|Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.|  
|[\<schemaImporterExtensions>-Element](../../../docs/standard/serialization/schemaimporterextensions-element.md)|Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse zum Zuordnen von XSD-Typen zu .NET Framework-Typen verwendet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration> Element](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie der Serialisierungsmodus eines <xref:System.DateTime>-Objekts und das Hinzufügen von Typen, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, beim Zuordnen von XSD-Typen zu .NET Framework-Typen festgelegt werden.  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<dateTimeSerialization>-Element](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [\<schemaImporterExtensions>-Element](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [\<add>-Element für \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
