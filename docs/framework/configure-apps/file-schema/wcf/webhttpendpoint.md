---
title: '&lt;webHttpEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5c8d75c457c4f8ec427480afd0e4d3e7335ff981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="07516-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="07516-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="07516-103">Este elemento de configuração define um ponto de extremidade padrão fixa [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associação que automaticamente adiciona o [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="07516-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="07516-104">Use esse ponto de extremidade ao escrever um serviço REST.</span><span class="sxs-lookup"><span data-stu-id="07516-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="07516-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="07516-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="07516-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="07516-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07516-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="07516-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07516-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="07516-108">Attributes and Elements</span></span>  
 <span data-ttu-id="07516-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="07516-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07516-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="07516-110">Attributes</span></span>  
  
|<span data-ttu-id="07516-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="07516-111">Attribute</span></span>|<span data-ttu-id="07516-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="07516-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07516-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="07516-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="07516-114">Um valor booliano que indica se a seleção automática de formato é habilitada.</span><span class="sxs-lookup"><span data-stu-id="07516-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="07516-115">Quando a seleção automática de formato estiver habilitada, a infraestrutura analisa o `Accept` cabeçalho da mensagem de solicitação e determina o formato de resposta mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="07516-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="07516-116">Se o `Accept` cabeçalho não especifica um formato de resposta adequado, usa a infraestrutura de `Content-Type` de mensagem de solicitação ou o formato de resposta padrão da operação.</span><span class="sxs-lookup"><span data-stu-id="07516-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="07516-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="07516-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="07516-118">Um atributo que especifica o formato de resposta de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="07516-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="07516-119">Esse atributo é do <xref:System.ServiceModel.Web.WebMessageFormat> tipo</span><span class="sxs-lookup"><span data-stu-id="07516-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="07516-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="07516-120">helpEnabled</span></span>|<span data-ttu-id="07516-121">Um valor booliano que indica se a página de ajuda HTTP está habilitada para o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="07516-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="07516-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="07516-122">webEndpointType</span></span>|<span data-ttu-id="07516-123">Uma cadeia de caracteres que especifica o tipo do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="07516-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07516-124">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="07516-124">Child Elements</span></span>  
 <span data-ttu-id="07516-125">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="07516-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07516-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="07516-126">Parent Elements</span></span>  
  
|<span data-ttu-id="07516-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="07516-127">Element</span></span>|<span data-ttu-id="07516-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="07516-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07516-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="07516-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="07516-130">Uma coleção de pontos de extremidade padrão que são predefinidas pontos de extremidade com um ou mais de suas propriedades (endereço, associação, contrato) fixo.</span><span class="sxs-lookup"><span data-stu-id="07516-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07516-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="07516-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>