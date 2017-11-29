---
title: ICLRRuntimeHost::Stop-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3798c4fc451b78257373c0ac47a5e7e7c27dd048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="17670-102">ICLRRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="17670-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="17670-103">Beendet die Ausführung von Code von der common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="17670-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="17670-104">Diese Methode nicht zum Freigeben von Ressourcen auf dem Host, Anwendungsdomänen zu entladen oder Zerstören von Threads.</span><span class="sxs-lookup"><span data-stu-id="17670-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="17670-105">Sie müssen den Vorgang, um diese Ressourcen freizugeben beenden.</span><span class="sxs-lookup"><span data-stu-id="17670-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17670-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="17670-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="17670-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17670-107">Return Value</span></span>  
  
|<span data-ttu-id="17670-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17670-108">HRESULT</span></span>|<span data-ttu-id="17670-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17670-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17670-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="17670-110">S_OK</span></span>|<span data-ttu-id="17670-111">`Stop`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="17670-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="17670-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="17670-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17670-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="17670-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17670-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17670-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17670-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17670-115">The call timed out.</span></span>|  
|<span data-ttu-id="17670-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17670-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17670-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="17670-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17670-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17670-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17670-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="17670-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17670-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17670-120">E_FAIL</span></span>|<span data-ttu-id="17670-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="17670-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17670-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="17670-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17670-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="17670-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17670-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17670-124">Requirements</span></span>  
 <span data-ttu-id="17670-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17670-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17670-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="17670-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17670-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="17670-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17670-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17670-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17670-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17670-129">See Also</span></span>  
 [<span data-ttu-id="17670-130">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17670-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)