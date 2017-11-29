---
title: ICorDebugStepper Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper
helpviewer_keywords: ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 83d394669270eb26b33e084b20a621e18b5b14aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="59543-102">ICorDebugStepper Interface1</span><span class="sxs-lookup"><span data-stu-id="59543-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="59543-103">Representa uma etapa na execução do código que é realizada por um depurador, serve como um identificador entre a emissão e a conclusão de um comando e fornece uma maneira de cancelar uma etapa.</span><span class="sxs-lookup"><span data-stu-id="59543-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59543-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="59543-104">Methods</span></span>  
  
|<span data-ttu-id="59543-105">Método</span><span class="sxs-lookup"><span data-stu-id="59543-105">Method</span></span>|<span data-ttu-id="59543-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="59543-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59543-107">Método Deactivate</span><span class="sxs-lookup"><span data-stu-id="59543-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="59543-108">Faz com que essa `ICorDebugStepper` para cancelar o último comando de etapa recebido.</span><span class="sxs-lookup"><span data-stu-id="59543-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="59543-109">Método IsActive</span><span class="sxs-lookup"><span data-stu-id="59543-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="59543-110">Obtém um valor que indica se este `ICorDebugStepper` está executando uma etapa.</span><span class="sxs-lookup"><span data-stu-id="59543-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="59543-111">Método SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="59543-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="59543-112">Define um valor de CorDebugIntercept que especifica os tipos de código que são entrado em.</span><span class="sxs-lookup"><span data-stu-id="59543-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="59543-113">Método SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="59543-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="59543-114">Define um valor que indica se chamadas para [: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passar valores de argumento em relação ao código nativo ou em código do Microsoft intermediate language (MSIL) do método que está sendo percorrido.</span><span class="sxs-lookup"><span data-stu-id="59543-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="59543-115">Método SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="59543-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="59543-116">Define um valor de CorDebugUnmappedStop que especifica o tipo de código não mapeado no qual a execução será interrompida.</span><span class="sxs-lookup"><span data-stu-id="59543-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="59543-117">Método Step</span><span class="sxs-lookup"><span data-stu-id="59543-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="59543-118">Faz com que essa `ICorDebugStepper` para percorrer por meio de seu recipiente thread e, opcionalmente, para continuar a depuração único por meio das funções que são chamadas de dentro do thread.</span><span class="sxs-lookup"><span data-stu-id="59543-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="59543-119">Método StepOut</span><span class="sxs-lookup"><span data-stu-id="59543-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="59543-120">Faz com que essa `ICorDebugStepper` para percorrer por meio de seu recipiente thread e concluído quando o quadro atual retorna o controle para o quadro de chamada.</span><span class="sxs-lookup"><span data-stu-id="59543-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="59543-121">Método StepRange</span><span class="sxs-lookup"><span data-stu-id="59543-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="59543-122">Faz com que essa `ICorDebugStepper` para percorrer por meio de seu recipiente thread e para retornar quando atingir código além do último dos intervalos especificados.</span><span class="sxs-lookup"><span data-stu-id="59543-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59543-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="59543-123">Remarks</span></span>  
 <span data-ttu-id="59543-124">O `ICorDebugStepper` interface tem as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="59543-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="59543-125">Ele atua como um identificador entre um comando de depuração que é emitido e a conclusão desse comando.</span><span class="sxs-lookup"><span data-stu-id="59543-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="59543-126">Ele fornece uma interface central para encapsular todo o passo a passo que pode ser executada.</span><span class="sxs-lookup"><span data-stu-id="59543-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="59543-127">Ele fornece uma maneira de cancelar prematuramente uma operação de revisão.</span><span class="sxs-lookup"><span data-stu-id="59543-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="59543-128">Pode haver mais de um seletor por thread.</span><span class="sxs-lookup"><span data-stu-id="59543-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="59543-129">Por exemplo, um ponto de interrupção pode ser obtido ao passar sobre uma função, e o usuário deseja iniciar uma nova operação de revisão nessa função.</span><span class="sxs-lookup"><span data-stu-id="59543-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="59543-130">Cabe o depurador para determinar como tratar essa situação.</span><span class="sxs-lookup"><span data-stu-id="59543-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="59543-131">O depurador talvez queira cancelar a operação de revisão original ou aninhar as duas operações.</span><span class="sxs-lookup"><span data-stu-id="59543-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="59543-132">O `ICorDebugStepper` interface dá suporte a ambas as opções.</span><span class="sxs-lookup"><span data-stu-id="59543-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="59543-133">Um seletor pode migrar entre threads se o common language runtime (CLR) faz uma chamada de thread cruzado, empacotada.</span><span class="sxs-lookup"><span data-stu-id="59543-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59543-134">Esta interface não dá suporte a que está sendo chamado remotamente, entre computadores ou entre processos.</span><span class="sxs-lookup"><span data-stu-id="59543-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59543-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59543-135">Requirements</span></span>  
 <span data-ttu-id="59543-136">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59543-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59543-137">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59543-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59543-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59543-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59543-139">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59543-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59543-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="59543-140">See Also</span></span>  
 [<span data-ttu-id="59543-141">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="59543-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)