---
title: "&lt;segurança&gt; de &lt;ws2007HttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 78a87add1ed71786dd0e4181c7eeb70e3b63cec1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="a69ac-102">&lt;segurança&gt; de &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a69ac-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="a69ac-103">Representa as configurações de segurança usadas com o [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="a69ac-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="a69ac-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a69ac-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a69ac-105">\<associações ></span><span class="sxs-lookup"><span data-stu-id="a69ac-105">\<bindings></span></span>  
<span data-ttu-id="a69ac-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a69ac-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="a69ac-107">\<associação ></span><span class="sxs-lookup"><span data-stu-id="a69ac-107">\<binding></span></span>  
<span data-ttu-id="a69ac-108">\<segurança ></span><span class="sxs-lookup"><span data-stu-id="a69ac-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69ac-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a69ac-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a69ac-110">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a69ac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a69ac-111">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="a69ac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a69ac-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a69ac-112">Attributes</span></span>  
  
|<span data-ttu-id="a69ac-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a69ac-113">Attribute</span></span>|<span data-ttu-id="a69ac-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="a69ac-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="a69ac-115">-Opcional.</span><span class="sxs-lookup"><span data-stu-id="a69ac-115">-   Optional.</span></span> <span data-ttu-id="a69ac-116">Especifica o tipo de segurança que é aplicada.</span><span class="sxs-lookup"><span data-stu-id="a69ac-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a69ac-117">O padrão é `Message`.</span><span class="sxs-lookup"><span data-stu-id="a69ac-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="a69ac-118">Esse atributo é do tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a69ac-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a69ac-119">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="a69ac-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="a69ac-120">Valor</span><span class="sxs-lookup"><span data-stu-id="a69ac-120">Value</span></span>|<span data-ttu-id="a69ac-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="a69ac-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="a69ac-122">A segurança é desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a69ac-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="a69ac-123">A proteção é fornecida usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a69ac-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="a69ac-124">O serviço deve ser configurado com certificados Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="a69ac-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="a69ac-125">A mensagem é totalmente protegida usando HTTPS e o serviço é autenticado pelo cliente usando o certificado SSL do serviço.</span><span class="sxs-lookup"><span data-stu-id="a69ac-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="a69ac-126">A autenticação do cliente é controlada por meio de `ClientCredentials` atributo do [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="a69ac-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="a69ac-127">A segurança é fornecida usando a segurança de mensagem SOAP.</span><span class="sxs-lookup"><span data-stu-id="a69ac-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a69ac-128">Por padrão, o corpo SOAP é criptografado e assinado.</span><span class="sxs-lookup"><span data-stu-id="a69ac-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="a69ac-129">Esse modo oferece uma variedade de recursos, como se as credenciais de serviço estão disponíveis no cliente fora da banda, o conjunto de algoritmos para usar e o nível de proteção para aplicar ao corpo da mensagem por meio de <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="a69ac-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="a69ac-130">Autenticação de cliente é executada uma vez para cada sessão e os resultados de autenticação são armazenados em cache para a duração da sessão.</span><span class="sxs-lookup"><span data-stu-id="a69ac-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="a69ac-131">Nesse modo, HTTPS fornece autenticação de servidor, integridade e confidencialidade e segurança de mensagens SOAP fornece autenticação de cliente.</span><span class="sxs-lookup"><span data-stu-id="a69ac-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="a69ac-132">Por padrão, autenticação de cliente é executada uma vez para cada sessão e os resultados de autenticação são armazenados em cache para a duração da sessão.</span><span class="sxs-lookup"><span data-stu-id="a69ac-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a69ac-133">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a69ac-133">Child Elements</span></span>  
  
|<span data-ttu-id="a69ac-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="a69ac-134">Element</span></span>|<span data-ttu-id="a69ac-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="a69ac-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a69ac-136">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="a69ac-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="a69ac-137">Define as configurações de segurança de transporte.</span><span class="sxs-lookup"><span data-stu-id="a69ac-137">Defines the transport security settings.</span></span> <span data-ttu-id="a69ac-138">Esse elemento corresponde ao <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> tipo.</span><span class="sxs-lookup"><span data-stu-id="a69ac-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="a69ac-139">Essas configurações são aplicadas somente quando o modo é definido como transporte.</span><span class="sxs-lookup"><span data-stu-id="a69ac-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="a69ac-140">\<mensagem ></span><span class="sxs-lookup"><span data-stu-id="a69ac-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="a69ac-141">Define as configurações de segurança para a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a69ac-141">Defines the security settings for the message.</span></span> <span data-ttu-id="a69ac-142">Esse elemento corresponde ao <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> tipo.</span><span class="sxs-lookup"><span data-stu-id="a69ac-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="a69ac-143">Essas configurações não são aplicadas quando o modo é definido como transporte.</span><span class="sxs-lookup"><span data-stu-id="a69ac-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a69ac-144">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a69ac-144">Parent Elements</span></span>  
  
|<span data-ttu-id="a69ac-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="a69ac-145">Element</span></span>|<span data-ttu-id="a69ac-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="a69ac-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a69ac-147">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a69ac-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="a69ac-148">Uma associação de segurança para aplicativos de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="a69ac-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a69ac-149">Comentários</span><span class="sxs-lookup"><span data-stu-id="a69ac-149">Remarks</span></span>  
 <span data-ttu-id="a69ac-150">Esse elemento se destina a interoperação com os serviços que implementam o WS-* especificações.</span><span class="sxs-lookup"><span data-stu-id="a69ac-150">This element is designed for interoperation with services that implement WS-* specifications.</span></span> <span data-ttu-id="a69ac-151">A segurança de transporte para essa associação é o protocolo (SSL) via HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a69ac-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69ac-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a69ac-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="a69ac-153">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="a69ac-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="a69ac-154">[Bindings](../../../../../docs/framework/wcf/bindings.md) (Associações)</span><span class="sxs-lookup"><span data-stu-id="a69ac-154">[Bindings](../../../../../docs/framework/wcf/bindings.md)</span></span>  
 [<span data-ttu-id="a69ac-155">Configurando associações fornecidas pelo sistema</span><span class="sxs-lookup"><span data-stu-id="a69ac-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a69ac-156">Usando associações para configurar clientes e serviços do Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a69ac-156">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a69ac-157">\<associação ></span><span class="sxs-lookup"><span data-stu-id="a69ac-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)