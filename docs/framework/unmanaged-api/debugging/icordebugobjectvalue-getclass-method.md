---
title: ICorDebugObjectValue::GetClass-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee9f110647230e54df527959651dc5b2fb73b3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="e5aa2-102">ICorDebugObjectValue::GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="e5aa2-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="e5aa2-103">Ruft die Klasse für den Wert dieses Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="e5aa2-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5aa2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5aa2-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5aa2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5aa2-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="e5aa2-106">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugClass", das die Klasse des Objektwerts dargestellt, die von diesem Objekt "ICorDebugObjectValue" darstellt.</span><span class="sxs-lookup"><span data-stu-id="e5aa2-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5aa2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5aa2-107">Remarks</span></span>  
 <span data-ttu-id="e5aa2-108">Die `GetClass` und [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) Methoden geben jeweils Informationen über den Typ eines Werts zurückgeben. sie werden sowohl von der Generika-bewusste abgelöst [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="e5aa2-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5aa2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5aa2-109">Requirements</span></span>  
 <span data-ttu-id="e5aa2-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5aa2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5aa2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5aa2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5aa2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5aa2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5aa2-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5aa2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5aa2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5aa2-114">See Also</span></span>  
    
 