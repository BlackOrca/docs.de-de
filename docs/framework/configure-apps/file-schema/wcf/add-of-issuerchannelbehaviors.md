---
title: '&lt;add&gt; von &lt;issuerChannelBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 75531e8ed50ae89f379db23d228804612f4bfccb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752454"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;add&gt; von &lt;issuerChannelBehaviors&gt;
Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.  
  
> [!NOTE]
>  Wenn alle Endpunktverhalten enthält eine [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element, eine Ausnahme ausgelöst.  
  
 \<system.ServiceModel>  
\<behaviors>  
EndpointBehaviors-Abschnitt  
\<Verhalten >  
\<clientCredentials>  
\<IssuedToken >  
\<IssuerChannelBehaviors >-Element  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|issuerAddress|Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.|  
|behaviorConfiguration|Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IssuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Enthält eine Auflistung von Windows Communication Foundation (WCF)-Client-Endpunktverhalten bei der Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden.|  
  
## <a name="remarks"></a>Hinweise  
 `issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte. `behaviorConfiguration` verweist auf ein Endpunktverhalten, die die Anwendung in Kanäle erstellt vom Windows Communication Foundation (WCF) verwendet werden, um die ausgestellten Token aus den Sicherheitstokendiensten abzurufen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [\<IssuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
