---
title: 'Endpunkte: Adressen, Bindungen und Verträge'
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: 0909d1d10ab8932f27f7ca6cba6207d57fa4f4cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493747"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Endpunkte: Adressen, Bindungen und Verträge
Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Diensts. Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die von einem WCF-Dienst angeboten wird.  
  
 Jeder Endpunkt verfügt über vier Eigenschaften:  
  
-   Eine Adresse, die angibt, wo der Endpunkt zu finden ist.  
  
-   Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.  
  
-   Ein Vertrag, der die verfügbaren Vorgänge identifiziert.  
  
-   Eine Gruppe von Verhaltensweisen, die lokale Implementierungsdetails des Endpunkts angeben.  
  
 In diesem Thema wird diese endpunktstruktur erläutert, und es wird erläutert, wie er im WCF-Objektmodell dargestellt wird.  
  
## <a name="the-structure-of-an-endpoint"></a>Die Struktur eines Endpunkts  
 Jeder Endpunkt besteht aus Folgendem:  
  
-   Adresse: Die Adresse gewährleistet eine eindeutige Identifizierung des Endpunkts und teilt potenziellen Consumern des Diensts den Standort des Diensts mit. Es wird dargestellt, in dem WCF-Objektmodell durch die <xref:System.ServiceModel.EndpointAddress> Klasse. Eine <xref:System.ServiceModel.EndpointAddress>-Klasse enthält:  
  
    -   Eine <xref:System.ServiceModel.EndpointAddress.Uri%2A>-Eigenschaft, die die Adresse des Diensts darstellt.  
  
    -   Eine <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft, die die Sicherheits-ID des Diensts und eine Auflistung optionaler Nachrichtenheader darstellt. Die optionalen Nachrichtenheader werden verwendet, um zusätzliche und ausführlichere Adressinformationen bereitzustellen, um den Endpunkt zu identifizieren oder damit zu interagieren.  
  
     Weitere Informationen finden Sie unter [angeben einer Endpunktadresse](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   Bindung: Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet. Dies umfasst Folgendes:  
  
    -   Das Transportprotokoll, das verwendet werden soll (z.&#160;B. TCP oder HTTP).  
  
    -   Die Codierung, die für die Nachrichten verwendet werden soll (z.&#160;B. Text oder binär).  
  
    -   Die erforderlichen Sicherheitsanforderungen (z.&#160;B. SSL- oder SOAP-Nachrichtensicherheit).  
  
     Weitere Informationen finden Sie unter [WCF-Bindungsübersicht](../../../../docs/framework/wcf/bindings-overview.md). Eine Bindung wird in der WCF-Objektmodell dargestellt, durch die abstrakte Basisklasse <xref:System.ServiceModel.Channels.Binding>. Für die meisten Szenarien können Benutzer eine der vom System bereitgestellten Bindungen verwenden. Weitere Informationen finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
-   Verträge: Der Dienstvertrag zeigt, welche Funktionen der Endpunkt dem Client zur Verfügung stellt. Ein Vertrag gibt Folgendes an:  
  
    -   Welche Vorgänge von einem Client aufgerufen werden können.  
  
    -   Die Form der Nachricht.  
  
    -   Der Typ der Eingabeparameter oder Daten, die zum Aufrufen des Vorgangs erforderlich sind.  
  
    -   Den Typ der Verarbeitung oder der Antwortnachricht, den der Client erwarten kann.  
  
     Weitere Informationen zum Definieren eines Vertrags finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
-   Verhaltensweisen: Sie können das lokale Verhalten des Dienstendpunkts mithilfe von Endpunktverhaltensweisen anpassen. Endpunktverhaltensweisen erreichen dies, indem Sie im Prozess der Erstellung einer WCFruntime an. Ein Beispiel für ein Endpunktverhalten ist die <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>-Eigenschaft, mit der Sie eine andere Listeningadresse als die SOAP- oder die WSDL-Adresse (WSDL = Web Services Description Language) angeben können. Weitere Informationen finden Sie unter [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## <a name="defining-endpoints"></a>Definieren von Endpunkten  
 Sie können den Endpunkt für einen Dienst entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angeben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) und [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 In diesem Abschnitt wird der Zweck von Bindungen, Endpunkten und Adressen erläutert. Darüber hinaus wird gezeigt, wie Sie eine Bindung und einen Endpunkt konfigurieren und wie Sie das `ClientVia`-Verhalten und die `ListenUri`-Eigenschaft verwenden.  
  
 [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Beschreibt, wie Endpunkte in WCF behoben werden.  
  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Beschreibt, wie mit Bindungen Transport, Codierung und Protokolldetails angegeben werden, die für die Kommunikation zwischen Clients und Diensten erforderlich sind.  
  
 [Verträge](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Beschreibt, wie Verträge die Methoden eines Diensts definieren.  
  
 [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Beschreibt, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.  
  
 [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Beschreibt, wie Sie einen Dienstendpunkt im Code erstellen.  
  
 [Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Beschreibt, wie zum Erkennen von Fehlern in dienstimplementierungen und Konfigurationen, ohne zu hosten, den Dienst mithilfe der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md)  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)
