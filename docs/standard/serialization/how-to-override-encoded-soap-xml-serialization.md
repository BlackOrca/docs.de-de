---
title: 'Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung'
ms.date: 03/30/2017
helpviewer_keywords:
- overriding XML serialization
- SOAP, overriding encoded XML serialization
ms.assetid: d0791df8-04e3-46b4-a6be-fe0ed09267e8
ms.openlocfilehash: 1ce2259c482c0e8441b35b41e2303fba5d547416
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585839"
---
# <a name="how-to-override-encoded-soap-xml-serialization"></a>Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung
[Code Example (Codebeispiel)](#tskhowtooverrideencodedsoapxmlserializationanchor1)  
  
 Das Verfahren zum Überschreiben der XML-Serialisierung von Objekten als SOAP-Nachrichten ist mit dem zum Überschreiben der Standard-XML-Serialisierung vergleichbar. Informationen zum Überschreiben der Standard-XML-Serialisierung finden Sie unter [How to: Specify an Alternate Element Name for an XML Stream (Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream)](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md).  
  
### <a name="to-override-serialization-of-objects-as-soap-messages"></a>So überschreiben Sie Serialisierung von Objekten als SOAP-Nachrichten  
  
1.  Erstellen Sie eine Instanz der <xref:System.Xml.Serialization.SoapAttributeOverrides>-Klasse.  
  
2.  Erstellen Sie für jeden Klassenmember, der serialisiert wird, ein `SoapAttributes`-Attribut.  
  
3.  Erstellen Sie für den zu serialisierenden Member eine Instanz eines oder mehrerer der Attribute, die sich auf die XML-Serialisierung auswirken. Weitere Informationen hierzu finden Sie unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP".  
  
4.  Legen Sie die entsprechende Eigenschaft von `SoapAttributes` auf das in Schritt 3 erstellte Attribut fest.  
  
5.  Fügen Sie `SoapAttributes` zu `SoapAttributeOverrides` hinzu.  
  
6.  Erstellen Sie `XmlTypeMapping` mithilfe von `SoapAttributeOverrides`. Verwenden Sie die `SoapReflectionImporter.ImportTypeMapping`-Methode.  
  
7.  Erstellen Sie `XmlSerializer` mithilfe von `XmlTypeMapping`.  
  
8.  Serialisieren oder deserialisieren Sie das Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Datei auf zwei verschiedene Arten serialisiert: Zuerst wird das Verhalten der `XmlSerializer`-Klasse nicht überschrieben und dann wird das Verhalten überschrieben. Das Beispiel enthält eine Klasse namens `Group` mit mehreren Membern. Auf Klassenmember wurden verschiedene Attribute, z.B. `SoapElementAttribute`, angewendet. Wenn die Klasse mit der `SerializeOriginal`-Methode serialisiert wird, steuern die Attribute den Inhalt der SOAP-Nachrichten. Beim Aufrufen der `SerializeOverride`-Methode, wird der Inhalt der `XmlSerializer`-Klasse dadurch überschrieben, dass verschiedene Attribute erstellt und die Eigenschaften eines `SoapAttributes`-Objekts entsprechend auf diese Attribute festgelegt werden.  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
using System.Xml.Schema;  
  
public class Group  
{  
    [SoapAttribute (Namespace = "http://www.cpandl.com")]  
    public string GroupName;  
  
    [SoapAttribute(DataType = "base64Binary")]  
    public Byte [] GroupNumber;  
  
    [SoapAttribute(DataType = "date", AttributeName = "CreationDate")]  
    public DateTime Today;  
    [SoapElement(DataType = "nonNegativeInteger", ElementName = "PosInt")]  
    public string PostitiveInt;  
    // This is ignored when serialized unless it is overridden.  
    [SoapIgnore]   
    public bool IgnoreThis;  
  
    public GroupType Grouptype;  
  
    [SoapInclude(typeof(Car))]  
    public Vehicle myCar(string licNumber)  
    {  
        Vehicle v;  
        if(licNumber == "")  
            {  
                v = new Car();  
            v.licenseNumber = "!!!!!!";  
        }  
        else  
        {  
            v = new Car();  
            v.licenseNumber = licNumber;  
        }  
        return v;  
    }  
}  
  
public abstract class Vehicle  
{  
    public string licenseNumber;  
    public DateTime makeDate;  
}  
  
public class Car: Vehicle  
{  
}  
  
public enum GroupType  
{  
    // These enums can be overridden.  
    small,  
    large  
}  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeOriginal("SoapOriginal.xml");  
        test.SerializeOverride("SoapOverrides.xml");  
        test.DeserializeOriginal("SoapOriginal.xml");  
        test.DeserializeOverride("SoapOverrides.xml");  
  
    }  
    public void SerializeOriginal(string filename)  
    {  
        // Creates an instance of the XmlSerializer class.  
        XmlTypeMapping myMapping =   
        (new SoapReflectionImporter().ImportTypeMapping(  
        typeof(Group)));  
        XmlSerializer mySerializer =    
        new XmlSerializer(myMapping);  
  
        // Writing the file requires a TextWriter.  
        TextWriter writer = new StreamWriter(filename);  
  
        // Creates an instance of the class that will be serialized.  
        Group myGroup = new Group();  
  
        // Sets the object properties.  
        myGroup.GroupName = ".NET";  
  
        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),  
        Convert.ToByte(50)};  
        myGroup.GroupNumber = hexByte;  
  
        DateTime myDate = new DateTime(2002,5,2);  
        myGroup.Today = myDate;  
  
        myGroup.PostitiveInt= "10000";  
        myGroup.IgnoreThis=true;  
        myGroup.Grouptype= GroupType.small;  
        Car thisCar =(Car)  myGroup.myCar("1234566");  
  
        // Prints the license number just to prove the car was created.  
        Console.WriteLine("License#: " + thisCar.licenseNumber + "\n");  
  
        // Serializes the class and closes the TextWriter.  
        mySerializer.Serialize(writer, myGroup);  
        writer.Close();  
    }  
  
    public void SerializeOverride(string filename)  
    {  
        // Creates an instance of the XmlSerializer class  
        // that overrides the serialization.  
        XmlSerializer overRideSerializer = CreateOverrideSerializer();  
  
        // Writing the file requires a TextWriter.  
        TextWriter writer = new StreamWriter(filename);  
  
        // Creates an instance of the class that will be serialized.  
        Group myGroup = new Group();  
  
        // Sets the object properties.  
        myGroup.GroupName = ".NET";  
  
        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),  
        Convert.ToByte(50)};  
        myGroup.GroupNumber = hexByte;  
  
        DateTime myDate = new DateTime(2002,5,2);  
        myGroup.Today = myDate;  
  
        myGroup.PostitiveInt= "10000";  
        myGroup.IgnoreThis=true;  
        myGroup.Grouptype= GroupType.small;  
        Car thisCar =(Car)  myGroup.myCar("1234566");  
  
        // Serializes the class and closes the TextWriter.  
        overRideSerializer.Serialize(writer, myGroup);  
         writer.Close();  
    }  
  
    public void DeserializeOriginal(string filename)  
    {  
        // Creates an instance of the XmlSerializer class.  
        XmlTypeMapping myMapping =   
        (new SoapReflectionImporter().ImportTypeMapping(  
        typeof(Group)));  
        XmlSerializer mySerializer =    
        new XmlSerializer(myMapping);  
  
        TextReader reader = new StreamReader(filename);  
  
        // Deserializes and casts the object.  
        Group myGroup;   
        myGroup = (Group) mySerializer.Deserialize(reader);  
  
        Console.WriteLine(myGroup.GroupName);  
        Console.WriteLine(myGroup.GroupNumber[0]);  
        Console.WriteLine(myGroup.GroupNumber[1]);  
        Console.WriteLine(myGroup.Today);  
        Console.WriteLine(myGroup.PostitiveInt);  
        Console.WriteLine(myGroup.IgnoreThis);  
        Console.WriteLine();  
    }  
  
    public void DeserializeOverride(string filename)  
    {  
        // Creates an instance of the XmlSerializer class.  
        XmlSerializer overRideSerializer = CreateOverrideSerializer();  
        // Reading the file requires a TextReader.  
        TextReader reader = new StreamReader(filename);  
  
        // Deserializes and casts the object.  
        Group myGroup;   
        myGroup = (Group) overRideSerializer.Deserialize(reader);  
  
        Console.WriteLine(myGroup.GroupName);  
        Console.WriteLine(myGroup.GroupNumber[0]);  
        Console.WriteLine(myGroup.GroupNumber[1]);  
        Console.WriteLine(myGroup.Today);  
        Console.WriteLine(myGroup.PostitiveInt);  
        Console.WriteLine(myGroup.IgnoreThis);  
    }  
  
    private XmlSerializer CreateOverrideSerializer()  
    {  
        SoapAttributeOverrides mySoapAttributeOverrides =   
        new SoapAttributeOverrides();  
        SoapAttributes soapAtts = new SoapAttributes();  
  
        SoapElementAttribute mySoapElement = new SoapElementAttribute();  
        mySoapElement.ElementName = "xxxx";  
        soapAtts.SoapElement = mySoapElement;  
        mySoapAttributeOverrides.Add(typeof(Group), "PostitiveInt",   
        soapAtts);  
  
        // Overrides the IgnoreThis property.  
        SoapIgnoreAttribute myIgnore = new SoapIgnoreAttribute();  
        soapAtts = new SoapAttributes();  
        soapAtts.SoapIgnore = false;        
        mySoapAttributeOverrides.Add(typeof(Group), "IgnoreThis",   
        soapAtts);  
  
        // Overrides the GroupType enumeration.  
        soapAtts = new SoapAttributes();  
        SoapEnumAttribute xSoapEnum = new SoapEnumAttribute();  
        xSoapEnum.Name = "Over1000";  
        soapAtts.SoapEnum = xSoapEnum;  
  
        // Adds the SoapAttributes to the   
        // mySoapAttributeOverridesrides.  
        mySoapAttributeOverrides.Add(typeof(GroupType), "large",   
        soapAtts);  
  
        // Creates a second enumeration and adds it.  
        soapAtts = new SoapAttributes();  
        xSoapEnum = new SoapEnumAttribute();  
        xSoapEnum.Name = "ZeroTo1000";  
        soapAtts.SoapEnum = xSoapEnum;  
        mySoapAttributeOverrides.Add(typeof(GroupType), "small",   
        soapAtts);  
  
        // Overrides the Group type.  
        soapAtts = new SoapAttributes();  
        SoapTypeAttribute soapType = new SoapTypeAttribute();  
        soapType.TypeName = "Team";  
        soapAtts.SoapType = soapType;  
        mySoapAttributeOverrides.Add(typeof(Group),soapAtts);  
  
        // Creates an XmlTypeMapping that is used to create an instance   
        // of the XmlSerializer class. Then returns the XmlSerializer.  
        XmlTypeMapping myMapping = (new SoapReflectionImporter(  
        mySoapAttributeOverrides)).ImportTypeMapping(typeof(Group));  
  
        XmlSerializer ser = new XmlSerializer(myMapping);  
        return ser;  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 [XML-Serialisierung mit XML-Webdiensten](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 [Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
