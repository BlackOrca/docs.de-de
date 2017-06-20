---
title: "Verwenden der NetHttpBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Verwenden der NetHttpBinding
<xref:System.ServiceModel.NetHttpBinding> ist eine für die Nutzung von HTTP\- oder WebSocket\-Diensten entwickelte Bindung, die standardmäßig die binäre Codierung verwendet.  <xref:System.ServiceModel.NetHttpBinding> erkennt, ob sie mit einem Anforderung\-Antwort\-Vertrag oder einem Duplexvertrag verwendet wird, und ändert das Verhalten entsprechend, indem HTTP für Anforderung\-Antwort\-Verträge und WebSockets für Duplexverträge verwendet wird.  Dieses Verhalten kann mit der <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A>\-Einstellung überschrieben werden:  
  
1.  Always: Erzwingt die Verwendung von WebSockets sogar für Anforderung\-Antwort\-Verträge.  
  
2.  Never: Verhindert die Verwendung von WebSockets.  Der Versuch, einen Duplexvertrag mit dieser Einstellung zu verwenden, löst eine Ausnahme aus.  
  
3.  WhenDuplex: Dies ist der Standardwert, der das oben beschriebene Verhalten aufweist.  
  
 <xref:System.ServiceModel.NetHttpBinding> unterstützt zuverlässige Sitzungen im HTTP\-Modus und WebSocket\-Modus.  Im WebSocket\-Modus werden Sitzungen vom Transport bereitgestellt.  
  
> [!WARNING]
>  Wenn <xref:System.ServiceModel.NetHttpBinding> verwendet wird und **TransferMode** für die Bindung auf **TransferMode.Streamed** festgelegt ist, verursachen große Datenströme ein Deadlock und der Aufruf ein Timeout.  Um dieses Problem zu umgehen, senden Sie kleinere Nachrichten oder verwenden **TransferMode.Buffered**.  
  
## Konfigurieren eines Diensts für die Verwendung von "NetHttpBinding"  
 <xref:System.ServiceModel.NetHttpBinding> kann wie jede andere Bindung konfiguriert werden.  Der folgende Konfigurationsausschnitt veranschaulicht, wie ein WCF\-Dienst mit <xref:System.ServiceModel.NetHttpBinding> konfiguriert wird.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    <!- ... -->   
  </system.serviceModel>  
```  
  
 Der folgende Codeausschnitt veranschaulicht, wie <xref:System.ServiceModel.NetHtttpBinding> im Code hinzugefügt wird.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## Siehe auch  
 [Konfigurieren von Bindungen für Dienste](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)   
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)   
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)   
 [Duplexdienste](../../../../docs/framework/wcf/feature-details/duplex-services.md)