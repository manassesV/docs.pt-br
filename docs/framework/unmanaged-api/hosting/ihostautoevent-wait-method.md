---
title: "Método IHostAutoEvent::Wait"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAutoEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4646e0bd04d69e7fe0125740c9c6e0c1b014071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostautoeventwait-method"></a>Método IHostAutoEvent::Wait
Faz com que o atual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instância para aguardar até que ele é de propriedade ou um período de tempo especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `dwMilliseconds`  
 [in] O número de milissegundos atual `IHostAutoEvent` instância deve esperar antes de retornar se nenhum thread ou fibra assume a propriedade.  
  
 `option`  
 [in] Uma da [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, especificar a ação que o host deve executar se este blocos de operação.  
  
## <a name="return-value"></a>Valor de retorno  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|`Wait`retornou com êxito.|  
|HOST_E_CLRNOTAVAILABLE|O common language runtime (CLR) não foi carregado em um processo ou o CLR está em um estado em que ele não pode executar código gerenciado ou processar a chamada com êxito.|  
|HOST_E_TIMEOUT|A chamada foi atingido.|  
|HOST_E_NOT_OWNER|O chamador não possui o bloqueio.|  
|HOST_E_ABANDONED|Um evento foi cancelado durante um thread bloqueado ou fibra estava aguardando nele.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Quando um método retornará E_FAIL, o CLR não será mais utilizável dentro do processo. As chamadas subsequentes para hospedagem métodos retornam HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_DEADLOCK|O host detectou um deadlock durante o intervalo de espera e escolher o evento representado por atual `IHostAutoEvent` instância como vítima de deadlock.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Interface ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interface IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [Interface IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [Interface IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
