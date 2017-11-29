---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a258b315b5a8537de87a603b5d1ec0c18387ddbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="8e9d6-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="8e9d6-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="8e9d6-103">Falha ao receber uma mensagem por um canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e9d6-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8e9d6-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e9d6-104">Description</span></span>  
 <span data-ttu-id="8e9d6-105">Este rastreamento pode ser emitido como um aviso ou erro.</span><span class="sxs-lookup"><span data-stu-id="8e9d6-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="8e9d6-106">Em ambos os casos, o rastreamento é emitido quando um ouvinte compatível não foi encontrado para uma solicitação HTTP de entrada e a solicitação HTTP é descartada.</span><span class="sxs-lookup"><span data-stu-id="8e9d6-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="8e9d6-107">Isso pode acontecer porque o verbo HTTP da solicitação não foi reconhecido por qualquer ouvinte HTTP, ou porque nenhum ouvinte foi escutando no endereço a solicitação foi direcionada para.</span><span class="sxs-lookup"><span data-stu-id="8e9d6-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="8e9d6-108">O rastreamento é emitido como um aviso no caso de auto-hospedado e como um erro quando o serviço é hospedado no IIS.</span><span class="sxs-lookup"><span data-stu-id="8e9d6-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9d6-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8e9d6-109">See Also</span></span>  
 [<span data-ttu-id="8e9d6-110">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="8e9d6-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8e9d6-111">Usando o rastreamento para solucionar problemas de seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="8e9d6-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 <span data-ttu-id="8e9d6-112">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md) (Administração e diagnósticos)</span><span class="sxs-lookup"><span data-stu-id="8e9d6-112">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md)</span></span>