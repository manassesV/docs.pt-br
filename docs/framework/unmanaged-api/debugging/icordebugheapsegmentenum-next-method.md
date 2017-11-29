---
title: "Método ICorDebugHeapSegmentEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 655bc404003c4af3aa2ba934ee192b378caf2f2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="dbbdf-102">Método ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="dbbdf-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="dbbdf-103">Obtém o número especificado de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instâncias que contêm informações sobre regiões de memória de heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbbdf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dbbdf-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbbdf-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dbbdf-105">Parameters</span></span>  
 <span data-ttu-id="dbbdf-106">celt</span><span class="sxs-lookup"><span data-stu-id="dbbdf-106">celt</span></span>  
 <span data-ttu-id="dbbdf-107">[in] O número de segmentos a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="dbbdf-108">segmentos</span><span class="sxs-lookup"><span data-stu-id="dbbdf-108">segments</span></span>  
 <span data-ttu-id="dbbdf-109">[out] Uma matriz de ponteiros, cada qual apontando para um [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objeto que fornece informações sobre uma região de memória no heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="dbbdf-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="dbbdf-110">pceltFetched</span></span>  
 <span data-ttu-id="dbbdf-111">[out] Um ponteiro para o número de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos retornados na verdade em `segments`.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="dbbdf-112">Esse valor pode ser `null` se `celt` é 1.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbbdf-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="dbbdf-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbbdf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbbdf-114">Requirements</span></span>  
 <span data-ttu-id="dbbdf-115">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbbdf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbbdf-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbbdf-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbbdf-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbbdf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbbdf-118">**Versões do .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbbdf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbbdf-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dbbdf-119">See Also</span></span>  
 [<span data-ttu-id="dbbdf-120">Interface ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="dbbdf-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 [<span data-ttu-id="dbbdf-121">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="dbbdf-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)