---
title: Serialisierungskonzepte
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
caps.latest.revision: 4
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 82349611fe127da46bed8998ac883c10c5164cd3
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="serialization-concepts"></a>Serialisierungskonzepte
Warum ist es sinnvoll, die Serialisierung zu verwenden? Die beiden wichtigsten Gründe bestehen darin, dass der Objektstatus auf einem Speichermedium dauerhaft gespeichert werden soll, damit zu einem späteren Zeitpunkt eine genaue Kopie angefertigt werden kann, und dass das Objekt als Wert von einer Anwendungsdomäne zu einer anderen Anwendungsdomäne übertragen werden soll. Die Serialisierung wird beispielsweise eingesetzt, um den Sitzungsstatus in ASP.NET zu speichern und Objekte in die Zwischenablage von Windows&#160;Forms zu kopieren. Sie wird auch vom Remotingsystem verwendet, um Objekte als Wert von einer Anwendungsdomäne an eine andere zu übergeben.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="persistent-storage"></a>Dauerhafte Speicherung
Es ist häufig notwendig, die Werte der Felder eines Objekts auf einem Datenträger zu speichern und diese Daten später abzurufen. Dies lässt sich zwar auch ohne die Serialisierung erreichen, aber dieser Ansatz ist häufig mühsam und fehleranfällig und wird zunehmend komplex, wenn eine Hierarchie von Objekten verfolgt werden muss. Stellen Sie sich vor, Sie programmieren eine große Geschäftsanwendung mit Tausenden von Objekten und müssen Code schreiben, mit dem die Felder und Eigenschaften der einzelnen Objekte auf dem Datenträger gespeichert und von diesem wieder abgerufen und in den jeweiligen Objekten wiederhergestellt werden. Die Serialisierung stellt einen zweckmäßigen Mechanismus zur Erreichung dieses Ziels bereit.

Die Common Language Runtime verwaltet, wie Objekte im Speicher gespeichert werden und stellt einen automatischen Serialisierungsmechanismus bereit, der sich auf die [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md) stützt. Wenn ein Objekt serialisiert wird, werden der Name der Klasse, die Assembly und alle Datenmember der Klasseninstanz auf das Speichermedium geschrieben. Objekte speichern oft in Membervariablen Verweise auf andere Instanzen. Beim Serialisieren der Klasse verfolgt das Serialisierungsmodul Objekte, auf die verwiesen wird und die bereits serialsiert sind, um sicherzustellen, dass ein Objekt nicht zweimal serialisiert wird. Die mit dem [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] bereitgestellte Serialisierungsarchitektur behandelt Objektdiagramme und Zirkelverweise automatisch richtig. Objektdiagramme müssen nur die Anforderung erfüllen, dass alle Objekte, auf die das serialisierte Objekt verweist, auch als `Serializable` markiert sein müssen (weitere Informationen finden Sie unter [Einfache Serialisierung](basic-serialization.md)). Ist dies nicht der Fall, wird eine Ausnahme ausgelöst, wenn versucht wird, das nicht markierte Objekt zu serialisieren.

Wenn die serialisierte Klasse deserialisiert wird, wird sie neu erstellt, und die Werte aller Datenmember werden automatisch wiederhergestellt.

## <a name="marshal-by-value"></a>Marshal als Wert
Objekte sind in nur der Anwendungsdomäne gültig, in der sie erstellt werden. Jeder Versuch, das Objekt als Parameter zu übergeben oder es als Ergebnis zurückzugeben, schlägt fehl, sofern das Objekt nicht von `MarshalByRefObject` abgeleitet wurde oder mit dem Attribut `Serializable` markiert ist. Wenn das Objekt als `Serializable` markiert ist, wird das Objekt automatisch serialisiert, von einer Anwendungsdomäne in die andere transportiert und dann deserialisiert, um in der zweiten Anwendungsdomäne eine genaue Kopie des Objekts zu erstellen. Dieser Vorgang wird in der Regel "Mashallen als Wert" genannt.
 
Wenn ein Objekt von `MarshalByRefObject` abgeleitet ist, wird statt des Objekts ein Objektverweis von einer Anwendungsdomäne einer anderen Anwendungsdomäne übergeben. Sie können auch ein Objekt, das von `MarshalByRefObject` abgeleitet ist, als `Serializable` kennzeichnen. Wenn dieses Objekt in Verbindung mit Remoting verwendet wird, übernimmt das für die Serialisierung zuständige Formatierungsprogramm, das mit einem Ersatzselektor (`SurrogateSelector`) vorkonfiguriert wurde, die Steuerung des Serialisierungsvorgangs und ersetzt alle von `MarshalByRefObject` abgeleiteten Objekte durch einen Proxy. Wenn kein `SurrogateSelector` gegeben ist, hält sich die Serialisierungsarchitektur an die Standardregeln für die Serialisierung, die unter [Schritte im Serialisierungsprozess](steps-in-the-serialization-process.md) beschrieben sind.  

## <a name="related-sections"></a>Verwandte Abschnitte  
 [Binäre Serialisierung](../../../docs/standard/serialization/binary-serialization.md)  
 Beschreibt den binären Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.  
  
 [Remoteobjekte](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)  
 Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET&#160;Framework für die Remotekommunikation zur Verfügung stehen.  
  
 [XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 Beschreibt den XML- und SOAP-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.
