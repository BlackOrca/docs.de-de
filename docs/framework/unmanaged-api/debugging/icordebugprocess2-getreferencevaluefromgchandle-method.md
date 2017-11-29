---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d40d1799a7c1572e8213fda3a163fb9a84060f92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="6e889-102">ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="6e889-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="6e889-103">Ruft einen Verweiszeiger auf dem angegebenen verwalteten Objekt, das eine Garbagecollection-handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="6e889-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e889-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e889-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e889-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e889-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="6e889-106">[in] Ein Zeiger auf ein verwaltetes Objekt, das eine Garbage Collection-Handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="6e889-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="6e889-107">Dieser Wert ist eine <xref:System.IntPtr> Objekt abgerufen werden können, und wählen Sie die <xref:System.Runtime.InteropServices.GCHandle> für das verwaltete Objekt.</span><span class="sxs-lookup"><span data-stu-id="6e889-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="6e889-108">[out] Ein Zeiger auf die Adresse eines ICorDebugReferenceValue-Objekts, das einen Verweis auf das angegebene verwaltete Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="6e889-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e889-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e889-109">Remarks</span></span>  
 <span data-ttu-id="6e889-110">Verwechseln Sie nicht den Wert der zurückgegebene Verweis mit einer Garbage Collection-Verweiswert.</span><span class="sxs-lookup"><span data-stu-id="6e889-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="6e889-111">Der zurückgegebene Verweis verhält sich wie ein normaler Verweis.</span><span class="sxs-lookup"><span data-stu-id="6e889-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="6e889-112">Es wird deaktiviert, wenn die Ausführung von Code nach einem Haltepunkt fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6e889-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="6e889-113">Die Lebensdauer des Zielobjekts wird von der Lebensdauer der Verweiswert nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="6e889-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e889-114">Die `GetReferenceValueFromGCHandle` Methode wird nicht überprüft, ob das Handle.</span><span class="sxs-lookup"><span data-stu-id="6e889-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="6e889-115">Aus diesem Grund die `GetReferenceValueFromGCHandle` Methode kann möglicherweise beschädigt, des Debuggers und der Code gedebuggt wird, wenn ein ungültiges Handle übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e889-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e889-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e889-116">Requirements</span></span>  
 <span data-ttu-id="6e889-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e889-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e889-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e889-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e889-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e889-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e889-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e889-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>