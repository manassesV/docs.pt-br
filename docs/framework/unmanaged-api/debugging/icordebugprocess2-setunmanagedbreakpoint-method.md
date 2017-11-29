---
title: "Método ICorDebugProcess2::SetUnmanagedBreakpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd2d6ac2967b4314a57aa30bbb34ff3d354a6365
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="59b62-102">Método ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="59b62-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="59b62-103">Define um ponto de interrupção não gerenciado no deslocamento especificado de imagem nativa.</span><span class="sxs-lookup"><span data-stu-id="59b62-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b62-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59b62-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59b62-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="59b62-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="59b62-106">[in] Um `CORDB_ADDRESS` objeto que especifica o deslocamento de imagem nativa.</span><span class="sxs-lookup"><span data-stu-id="59b62-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="59b62-107">[in] O tamanho, em bytes, do `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="59b62-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="59b62-108">[out] Uma matriz que contém o código de operação que é substituído pelo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="59b62-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="59b62-109">[out] Um ponteiro para o número de bytes retornados a `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="59b62-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59b62-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="59b62-110">Remarks</span></span>  
 <span data-ttu-id="59b62-111">Se o deslocamento de imagem nativa estiver dentro o common language runtime (CLR), o ponto de interrupção será ignorado.</span><span class="sxs-lookup"><span data-stu-id="59b62-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="59b62-112">Isso permite que o CLR evitar a distribuição de um ponto de interrupção de fora da banda, quando o ponto de interrupção é definido pelo depurador.</span><span class="sxs-lookup"><span data-stu-id="59b62-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b62-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59b62-113">Requirements</span></span>  
 <span data-ttu-id="59b62-114">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59b62-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b62-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59b62-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59b62-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59b62-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59b62-117">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b62-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>