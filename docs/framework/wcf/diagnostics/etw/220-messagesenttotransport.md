---
title: 220 - MessageSentToTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a84aa9ccbb51f2390376fc549660ca5e027969c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="08edf-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="08edf-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="08edf-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="08edf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08edf-104">Id</span><span class="sxs-lookup"><span data-stu-id="08edf-104">Id</span></span>|<span data-ttu-id="08edf-105">220</span><span class="sxs-lookup"><span data-stu-id="08edf-105">220</span></span>|  
|<span data-ttu-id="08edf-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="08edf-106">Keywords</span></span>|<span data-ttu-id="08edf-107">EndToEndMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08edf-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="08edf-108">Nível</span><span class="sxs-lookup"><span data-stu-id="08edf-108">Level</span></span>|<span data-ttu-id="08edf-109">Informações</span><span class="sxs-lookup"><span data-stu-id="08edf-109">Information</span></span>|  
|<span data-ttu-id="08edf-110">Canal</span><span class="sxs-lookup"><span data-stu-id="08edf-110">Channel</span></span>|<span data-ttu-id="08edf-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="08edf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="08edf-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="08edf-112">Description</span></span>  
 <span data-ttu-id="08edf-113">Esse evento é emitido quando o modelo de serviço envia uma mensagem para o transporte.</span><span class="sxs-lookup"><span data-stu-id="08edf-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08edf-114">Esse evento não será emitido para transportes unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="08edf-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="08edf-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="08edf-115">Message</span></span>  
 <span data-ttu-id="08edf-116">O Dispatcher enviou uma mensagem para o transporte.</span><span class="sxs-lookup"><span data-stu-id="08edf-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="08edf-117">ID de correlação = = '%1'.</span><span class="sxs-lookup"><span data-stu-id="08edf-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="08edf-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="08edf-118">Details</span></span>  
  
|<span data-ttu-id="08edf-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="08edf-119">Data Item Name</span></span>|<span data-ttu-id="08edf-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="08edf-120">Data Item Type</span></span>|<span data-ttu-id="08edf-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="08edf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="08edf-122">ID de correlação</span><span class="sxs-lookup"><span data-stu-id="08edf-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="08edf-123">A atividade de ID usada para correlacionar uma `MessageSentToTransport` evento em um serviço ou cliente correspondente `MessageReceivedFromTransport` na outra extremidade.</span><span class="sxs-lookup"><span data-stu-id="08edf-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="08edf-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="08edf-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="08edf-125">Para serviços hospedados na Web, este campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="08edf-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="08edf-126">O formato é definido como ' caminho Virtual do aplicativo de nome de Site da Web &#124; Caminho Virtual do serviço &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="08edf-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="08edf-127">Exemplo: ' Default Web Site/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="08edf-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="08edf-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="08edf-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="08edf-129">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="08edf-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|