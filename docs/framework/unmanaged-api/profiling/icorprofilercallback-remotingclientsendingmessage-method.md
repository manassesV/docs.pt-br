---
title: "Método ICorProfilerCallback::RemotingClientSendingMessage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientSendingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a77acb736cec02da6839335e981016469eeb42b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="8e8f9-102">Método ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="8e8f9-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="8e8f9-103">Notifica o criador de perfil que o cliente está enviando uma solicitação para o servidor.</span><span class="sxs-lookup"><span data-stu-id="8e8f9-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8f9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8e8f9-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e8f9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8e8f9-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="8e8f9-106">[in] Um valor que corresponde com o valor fornecido no [Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) sob estas condições:</span><span class="sxs-lookup"><span data-stu-id="8e8f9-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="8e8f9-107">Cookies GUID de comunicação remota estão ativos.</span><span class="sxs-lookup"><span data-stu-id="8e8f9-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="8e8f9-108">O canal tem sucesso na transmissão de mensagem.</span><span class="sxs-lookup"><span data-stu-id="8e8f9-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="8e8f9-109">Cookies GUID estão ativos no processo do servidor.</span><span class="sxs-lookup"><span data-stu-id="8e8f9-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="8e8f9-110">Isso permite que o emparelhamento fácil de chamadas de comunicação remota e a criação de uma pilha de chamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="8e8f9-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="8e8f9-111">[in] Um valor que é `true` se a chamada for assíncrona; caso contrário, `false`.</span><span class="sxs-lookup"><span data-stu-id="8e8f9-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e8f9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e8f9-112">Requirements</span></span>  
 <span data-ttu-id="8e8f9-113">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e8f9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e8f9-114">**Cabeçalho:** Corprof. idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e8f9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e8f9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e8f9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e8f9-116">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e8f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8f9-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8e8f9-117">See Also</span></span>  
 [<span data-ttu-id="8e8f9-118">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8e8f9-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)