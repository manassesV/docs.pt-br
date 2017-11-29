---
title: "Segurança de transporte com autenticação do Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 68550646f806b30f072b4270a336698011db54d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="5574d-102">Segurança de transporte com autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="5574d-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="5574d-103">O cenário a seguir mostra um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] cliente e serviço protegidos pela segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="5574d-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured by Windows security.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5574d-104">programação, consulte [como: proteger um serviço com as credenciais do Windows](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="5574d-104"> programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="5574d-105">Um serviço Web de intranet exibe informações de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="5574d-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="5574d-106">O cliente é um aplicativo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="5574d-106">The client is a Windows Form application.</span></span> <span data-ttu-id="5574d-107">O aplicativo é implantado em um domínio com um controlador de Kerberos, protegendo o domínio.</span><span class="sxs-lookup"><span data-stu-id="5574d-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 <span data-ttu-id="5574d-108">![Segurança com autenticação do Windows de transporte](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span><span class="sxs-lookup"><span data-stu-id="5574d-108">![Transport security with Windows authentication](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span></span>  
  
|<span data-ttu-id="5574d-109">Característica</span><span class="sxs-lookup"><span data-stu-id="5574d-109">Characteristic</span></span>|<span data-ttu-id="5574d-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="5574d-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5574d-111">Modo de segurança</span><span class="sxs-lookup"><span data-stu-id="5574d-111">Security Mode</span></span>|<span data-ttu-id="5574d-112">Transporte</span><span class="sxs-lookup"><span data-stu-id="5574d-112">Transport</span></span>|  
|<span data-ttu-id="5574d-113">Interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="5574d-113">Interoperability</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5574d-114">somente</span><span class="sxs-lookup"><span data-stu-id="5574d-114"> only</span></span>|  
|<span data-ttu-id="5574d-115">Autenticação (servidor)</span><span class="sxs-lookup"><span data-stu-id="5574d-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="5574d-116">Autenticação (cliente)</span><span class="sxs-lookup"><span data-stu-id="5574d-116">Authentication (Client)</span></span>|<span data-ttu-id="5574d-117">Sim (usando a autenticação integrada do Windows)</span><span class="sxs-lookup"><span data-stu-id="5574d-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="5574d-118">Sim (usando a autenticação integrada do Windows)</span><span class="sxs-lookup"><span data-stu-id="5574d-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="5574d-119">Integridade</span><span class="sxs-lookup"><span data-stu-id="5574d-119">Integrity</span></span>|<span data-ttu-id="5574d-120">Sim</span><span class="sxs-lookup"><span data-stu-id="5574d-120">Yes</span></span>|  
|<span data-ttu-id="5574d-121">Confidencialidade</span><span class="sxs-lookup"><span data-stu-id="5574d-121">Confidentiality</span></span>|<span data-ttu-id="5574d-122">Sim</span><span class="sxs-lookup"><span data-stu-id="5574d-122">Yes</span></span>|  
|<span data-ttu-id="5574d-123">Transporte</span><span class="sxs-lookup"><span data-stu-id="5574d-123">Transport</span></span>|<span data-ttu-id="5574d-124">NET. TCP</span><span class="sxs-lookup"><span data-stu-id="5574d-124">NET.TCP</span></span>|  
|<span data-ttu-id="5574d-125">Associação</span><span class="sxs-lookup"><span data-stu-id="5574d-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="5574d-126">Serviço</span><span class="sxs-lookup"><span data-stu-id="5574d-126">Service</span></span>  
 <span data-ttu-id="5574d-127">O código e a configuração a seguir destinam-se para executar de forma independente.</span><span class="sxs-lookup"><span data-stu-id="5574d-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5574d-128">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5574d-128">Do one of the following:</span></span>  
  
-   <span data-ttu-id="5574d-129">Crie um serviço autônomo usando o código sem nenhuma configuração.</span><span class="sxs-lookup"><span data-stu-id="5574d-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="5574d-130">Criar um serviço usando a configuração fornecida, mas não pode definir pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5574d-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5574d-131">Código</span><span class="sxs-lookup"><span data-stu-id="5574d-131">Code</span></span>  
 <span data-ttu-id="5574d-132">O código a seguir mostra como criar um ponto de extremidade de serviço que usa a segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="5574d-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="5574d-133">Configuração</span><span class="sxs-lookup"><span data-stu-id="5574d-133">Configuration</span></span>  
 <span data-ttu-id="5574d-134">A configuração a seguir pode ser usada em vez do código para configurar o ponto de extremidade de serviço:</span><span class="sxs-lookup"><span data-stu-id="5574d-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"   
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="5574d-135">Cliente</span><span class="sxs-lookup"><span data-stu-id="5574d-135">Client</span></span>  
 <span data-ttu-id="5574d-136">O código e a configuração a seguir destinam-se para executar de forma independente.</span><span class="sxs-lookup"><span data-stu-id="5574d-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5574d-137">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5574d-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="5574d-138">Crie um cliente autônomo usando o código (e o código do cliente).</span><span class="sxs-lookup"><span data-stu-id="5574d-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="5574d-139">Crie um cliente que não define os endereços de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5574d-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="5574d-140">Em vez disso, use o construtor de cliente que usa o nome da configuração como um argumento.</span><span class="sxs-lookup"><span data-stu-id="5574d-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="5574d-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5574d-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="5574d-142">Código</span><span class="sxs-lookup"><span data-stu-id="5574d-142">Code</span></span>  
 <span data-ttu-id="5574d-143">O código a seguir cria o cliente.</span><span class="sxs-lookup"><span data-stu-id="5574d-143">The following code creates the client.</span></span> <span data-ttu-id="5574d-144">A associação está configurada para usar a segurança de modo de transporte, com o transporte TCP, com o tipo de credencial de cliente definido como Windows.</span><span class="sxs-lookup"><span data-stu-id="5574d-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="5574d-145">Configuração</span><span class="sxs-lookup"><span data-stu-id="5574d-145">Configuration</span></span>  
 <span data-ttu-id="5574d-146">A configuração a seguir pode ser usada em vez do código para criar o cliente.</span><span class="sxs-lookup"><span data-stu-id="5574d-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"   
                binding="netTcpBinding"            
                bindingConfiguration="NetTcpBinding_ICalculator"   
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5574d-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5574d-147">See Also</span></span>  
 [<span data-ttu-id="5574d-148">Visão geral de segurança</span><span class="sxs-lookup"><span data-stu-id="5574d-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="5574d-149">[How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md) (Como proteger um serviço com credenciais Windows)</span><span class="sxs-lookup"><span data-stu-id="5574d-149">[How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)</span></span>  
 [<span data-ttu-id="5574d-150">Modelo de segurança para o Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="5574d-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)