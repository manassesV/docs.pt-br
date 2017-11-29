---
title: Interface IHostSyncManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="859c7-102">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="859c7-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="859c7-103">Fornece métodos que permitem que o common language runtime (CLR) para criar os primitivos de sincronização chamando o host em vez de usar as funções de sincronização do Win32.</span><span class="sxs-lookup"><span data-stu-id="859c7-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="859c7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="859c7-104">Methods</span></span>  
  
|<span data-ttu-id="859c7-105">Método</span><span class="sxs-lookup"><span data-stu-id="859c7-105">Method</span></span>|<span data-ttu-id="859c7-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="859c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="859c7-107">Método CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="859c7-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="859c7-108">Cria um objeto de evento de redefinição automática.</span><span class="sxs-lookup"><span data-stu-id="859c7-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="859c7-109">Método CreateCrst</span><span class="sxs-lookup"><span data-stu-id="859c7-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="859c7-110">Cria um objeto de seção crítica para sincronização.</span><span class="sxs-lookup"><span data-stu-id="859c7-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="859c7-111">Método CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="859c7-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="859c7-112">Cria um objeto de seção crítica com contagem de rotação para sincronização.</span><span class="sxs-lookup"><span data-stu-id="859c7-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="859c7-113">Método CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="859c7-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="859c7-114">Cria um objeto de evento de redefinição manual.</span><span class="sxs-lookup"><span data-stu-id="859c7-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="859c7-115">Método CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="859c7-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="859c7-116">Cria um objeto de evento de redefinição automática monitorado.</span><span class="sxs-lookup"><span data-stu-id="859c7-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="859c7-117">Método CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="859c7-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="859c7-118">Cria um objeto de evento de redefinição manual para a implementação de um bloqueio de leitor.</span><span class="sxs-lookup"><span data-stu-id="859c7-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="859c7-119">Método CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="859c7-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="859c7-120">Cria um objeto de evento de redefinição automática para a implementação de um bloqueio de gravador.</span><span class="sxs-lookup"><span data-stu-id="859c7-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="859c7-121">Método CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="859c7-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="859c7-122">Cria um [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto para o CLR a ser usado como um sinal para eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="859c7-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="859c7-123">Método SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="859c7-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="859c7-124">Conjuntos de [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instância para associar atual `IHostSyncManager` instância.</span><span class="sxs-lookup"><span data-stu-id="859c7-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="859c7-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="859c7-125">Remarks</span></span>  
 <span data-ttu-id="859c7-126">O CLR detecta a implementação do host de `IHostSyncManager` chamando o [Ihostcontrol](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) método com um `IID` de IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="859c7-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="859c7-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="859c7-127">Requirements</span></span>  
 <span data-ttu-id="859c7-128">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="859c7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="859c7-129">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="859c7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="859c7-130">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="859c7-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="859c7-131">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="859c7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859c7-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="859c7-132">See Also</span></span>  
 [<span data-ttu-id="859c7-133">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="859c7-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="859c7-134">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="859c7-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)