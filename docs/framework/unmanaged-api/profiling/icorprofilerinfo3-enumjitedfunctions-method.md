---
title: ICorProfilerInfo3::EnumJITedFunctions-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.EnumJITedFunctions Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c367ae29cc0daa406356a245f3dc16a671d3c54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="9e53a-102">ICorProfilerInfo3::EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="9e53a-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="9e53a-103">Gibt einen Enumerator für alle Funktionen, die zuvor mit JIT-kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="9e53a-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e53a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e53a-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e53a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e53a-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9e53a-106">[out] Ein Zeiger auf die [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Enumerator.</span><span class="sxs-lookup"><span data-stu-id="9e53a-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e53a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e53a-107">Remarks</span></span>  
 <span data-ttu-id="9e53a-108">Diese Methode möglicherweise überschneiden sich mit `JITCompilation` Rückrufe, z. B. die [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9e53a-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="9e53a-109">Der Enumerator, der von dieser Methode zurückgegebene umfasst nicht die Funktionen, die aus mit Ngen.exe generierten systemeigenen Images geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9e53a-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e53a-110">Die zurückgegebene Enumeration enthält nur "0" für den Wert der `COR_PRF_FUNCTION::reJitId` Feld.</span><span class="sxs-lookup"><span data-stu-id="9e53a-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="9e53a-111">Wenn Sie gültige benötigen `COR_PRF_FUNCTION::reJitId` verwenden Sie die Werte, die [icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9e53a-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e53a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e53a-112">Requirements</span></span>  
 <span data-ttu-id="9e53a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e53a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e53a-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e53a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e53a-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e53a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e53a-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e53a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e53a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e53a-117">See Also</span></span>  
 [<span data-ttu-id="9e53a-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e53a-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="9e53a-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9e53a-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="9e53a-120">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="9e53a-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)