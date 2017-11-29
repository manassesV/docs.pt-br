---
title: Interface ICorProfilerObjectEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum
helpviewer_keywords: ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b46f33485a63404f11dc0606e420ec9c3c43f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerobjectenum-interface"></a><span data-ttu-id="e9cff-102">Interface ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="e9cff-102">ICorProfilerObjectEnum Interface</span></span>
<span data-ttu-id="e9cff-103">Fornece métodos para iterar em sequência por meio de uma coleção de objetos congeladas gerados pelo [Ngen.exe (gerador de imagem nativa)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="e9cff-103">Provides methods to sequentially iterate through a collection of frozen objects that are generated by the [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9cff-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e9cff-104">Methods</span></span>  
  
|<span data-ttu-id="e9cff-105">Método</span><span class="sxs-lookup"><span data-stu-id="e9cff-105">Method</span></span>|<span data-ttu-id="e9cff-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9cff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9cff-107">Método clone</span><span class="sxs-lookup"><span data-stu-id="e9cff-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|<span data-ttu-id="e9cff-108">Obtém um ponteiro de interface para uma cópia deste `ICorProfilerObjectEnum` interface.</span><span class="sxs-lookup"><span data-stu-id="e9cff-108">Gets an interface pointer to a copy of this `ICorProfilerObjectEnum` interface.</span></span>|  
|[<span data-ttu-id="e9cff-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="e9cff-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|<span data-ttu-id="e9cff-110">Obtém o número total de objetos congelados na coleção.</span><span class="sxs-lookup"><span data-stu-id="e9cff-110">Gets the total number of frozen objects in the collection.</span></span>|  
|[<span data-ttu-id="e9cff-111">Próximo método</span><span class="sxs-lookup"><span data-stu-id="e9cff-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|<span data-ttu-id="e9cff-112">Obtém o número especificado de contíguos objetos de uma coleção sequencial de objetos, a posição atual do enumerador na sequência.</span><span class="sxs-lookup"><span data-stu-id="e9cff-112">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="e9cff-113">Método Reset</span><span class="sxs-lookup"><span data-stu-id="e9cff-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|<span data-ttu-id="e9cff-114">Move o cursor deste enumerador para a posição inicial da sequência.</span><span class="sxs-lookup"><span data-stu-id="e9cff-114">Moves this enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="e9cff-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="e9cff-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|<span data-ttu-id="e9cff-116">Avança o cursor deste enumerador de sua posição atual para que o número especificado de elementos será ignorado.</span><span class="sxs-lookup"><span data-stu-id="e9cff-116">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9cff-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="e9cff-117">Remarks</span></span>  
 <span data-ttu-id="e9cff-118">O `ICorProfilerObjectEnum` interface é um enumerador.</span><span class="sxs-lookup"><span data-stu-id="e9cff-118">The `ICorProfilerObjectEnum` interface is an enumerator.</span></span> <span data-ttu-id="e9cff-119">Ele permite que o destinatário de uma matriz para elementos de pull do remetente a uma taxa que é apropriado para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e9cff-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="e9cff-120">Em outras palavras, o destinatário é capaz de controlar explicitamente o fluxo de elementos da matriz, evitando, assim, os problemas relacionados ao passar matrizes grandes como parâmetros de método.</span><span class="sxs-lookup"><span data-stu-id="e9cff-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems related to passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="e9cff-121">Use [ICorProfilerInfo2::EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) para obter um ponteiro para o `ICorProfilerObjectEnum` interface.</span><span class="sxs-lookup"><span data-stu-id="e9cff-121">Use [ICorProfilerInfo2::EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) to obtain a pointer to the `ICorProfilerObjectEnum` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9cff-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9cff-122">Requirements</span></span>  
 <span data-ttu-id="e9cff-123">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9cff-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9cff-124">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9cff-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9cff-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9cff-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9cff-126">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9cff-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cff-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e9cff-127">See Also</span></span>  
 [<span data-ttu-id="e9cff-128">Interfaces de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="e9cff-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="e9cff-129">Método EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="e9cff-129">EnumModuleFrozenObjects Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)