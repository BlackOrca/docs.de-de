---
title: Sicherheitsberechtigung für die Umleitung der Assemblybindung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ef9295028aeb7bfcc6df88e9c8bb7f80e2a31368
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-binding-redirection-security-permission"></a>Sicherheitsberechtigung für die Umleitung der Assemblybindung
Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich. Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern. Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>. Verwaltete Assemblys verfügen standardmäßig über keine Berechtigungen.  
  
 Die Sicherheitsberechtigung erhält Anwendungen, die in der Zone "Vertrauenswürdige" (lokaler Computer) und der Intranetzone ausgeführt. Anwendungen, die in der Internetzone ausgeführt strikt untersagt, Umleitung der Assemblybindung ausführen.  
  
 Die Berechtigung ist nicht erforderlich, wenn Assemblyumleitungen durchgeführt wird, in eine Herausgeberrichtliniendatei, die vom Komponentenherausgeber gesteuert wird, oder in die Konfigurationsdatei des Computers, die vom Administrator gesteuert wird. Die Berechtigung ist jedoch erforderlich, damit eine Anwendung explizit ignorieren Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy gelten = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Anwendungskonfigurationsdatei.  
  
 Die folgende Tabelle zeigt die Sicherheitseinstellungen für die **BindingRedirects** Flag.  
  
|Zone|BindingRedirects-Flags|  
|----------|-----------------------------------|  
|Vertrauenswürdige Zone (lokaler Computer)|**ON**|  
|Intranet-Zone|**ON**|  
|Internetzone|**OFF**|  
|Nicht vertrauenswürdige Zonen|**OFF**|  
  
 Ein Administrator kann diese Sicherheitseinstellungen zum unterstützen oder Einschränken von spezifischen Szenarien auf einem bestimmten Computer ändern. Es sind keine Tools zum Ändern der **BindingRedirects** Flag festlegen, die von der Standardeinstellung; ein Administrator muss die Security.config-Datei auf dem Computer eines Benutzers manuell bearbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Herausgeberrichtliniendateien und Seite-an-Seite-Ausführung](http://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [Parallele Ausführung](../../../docs/framework/deployment/side-by-side-execution.md)
