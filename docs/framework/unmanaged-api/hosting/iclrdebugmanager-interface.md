---
title: ICLRDebugManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d123177bf9f1b5eee1a2ba4d9b7f2042ddc07aa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434938"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager-Schnittstelle
Enthält Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner und einen Anzeigenamen zuordnen können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Wird eine neue Verbindung zwischen dem Host und den Debugger, einen Bezeichner und einen Anzeigenamen Aufgaben zugeordnet werden soll.|  
|[EndConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einen Bezeichner und einen Anzeigenamen ein.|  
|[GetDacl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Diese Methode ist nicht implementiert.|  
|[IsDebuggerAttached-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.|  
|[SetConnectionTasks-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Ordnet eine Liste der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanzen einen Bezeichner und einen Anzeigenamen ein.|  
|[SetDacl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Diese Methode ist nicht implementiert.|  
|[SetSymbolReadingPolicy-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Legt die Richtlinie zum Lesen der Programmdatenbankdateien (PDB). Die Richtlinie bestimmt, ob Informationen zu Zeilennummern und Dateien in Aufruflisten enthalten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Debugszenarios beschrieben, kann ein Host zum Gruppieren von Aufgaben gemäß seiner eigenen Programmierlogik möchte. Eine Gruppierung erlauben zum Beispiel ein Entwickler sehen nur die Aufgaben der Entwickler-APIs anstelle jede Aufgabe, die im Prozess ausgeführt. `ICLRDebugManager` ermöglicht dem Host, um diese Art der Gruppierung zu implementieren.  
  
> [!IMPORTANT]
>  Drei `ICLRDebugManager` Methoden `BeginConnection`, `SetConnectionTasks` und `EndConnection`, voneinander abhängig sind. Sie müssen in der angegebenen Reihenfolge erwartungsgemäßen aufgerufen werden.  
  
 Haben die Gruppierung und die Bezeichner und den Anzeigenamen, die mit der Gruppierung der Host weist keine Bedeutung für die common Language Runtime (CLR). Die CLR übergibt lediglich die Informationen an dem Debugger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
