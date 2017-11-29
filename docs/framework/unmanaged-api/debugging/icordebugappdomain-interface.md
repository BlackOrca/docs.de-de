---
title: ICorDebugAppDomain Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain
helpviewer_keywords: ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19cf38920ed818dfbba9cd83bd64fdc408281e0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain-interface1"></a><span data-ttu-id="95790-102">ICorDebugAppDomain Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="95790-102">ICorDebugAppDomain Interface1</span></span>
<span data-ttu-id="95790-103">Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="95790-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="95790-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="95790-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95790-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="95790-105">Methods</span></span>  
  
|<span data-ttu-id="95790-106">Methode</span><span class="sxs-lookup"><span data-stu-id="95790-106">Method</span></span>|<span data-ttu-id="95790-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95790-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95790-108">Attach-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="95790-109">Fügt der Debugger an die Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="95790-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="95790-110">EnumerateAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="95790-111">Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="95790-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="95790-112">EnumerateBreakpoints-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="95790-113">Ruft einen Enumerator für alle aktiven Haltepunkte in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="95790-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="95790-114">EnumerateSteppers-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="95790-115">Ruft einen Enumerator für alle aktiven Stepper in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="95790-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="95790-116">GetId-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="95790-117">Ruft die eindeutige ID der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="95790-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="95790-118">GetModuleFromMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="95790-119">Ruft die ICorDebugModule-Objekt mit der angegebenen Metadaten-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="95790-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="95790-120">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="95790-121">Ruft den Namen der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="95790-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="95790-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="95790-123">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR) Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="95790-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="95790-124">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="95790-125">Ruft den Prozess ab, die die Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="95790-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="95790-126">IsAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="95790-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="95790-127">Bestimmt, ob der Debugger an die Anwendungsdomäne angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="95790-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95790-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95790-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95790-129">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="95790-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95790-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95790-130">Requirements</span></span>  
 <span data-ttu-id="95790-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95790-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95790-132">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95790-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95790-133">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95790-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95790-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95790-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95790-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95790-135">See Also</span></span>  
 [<span data-ttu-id="95790-136">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="95790-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)