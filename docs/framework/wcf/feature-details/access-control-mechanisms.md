---
title: Mecanismos de controle de acesso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f43de08a81afcf9ff6ab29b862f22c2935eca55f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="access-control-mechanisms"></a><span data-ttu-id="716be-102">Mecanismos de controle de acesso</span><span class="sxs-lookup"><span data-stu-id="716be-102">Access Control Mechanisms</span></span>
<span data-ttu-id="716be-103">Você pode controlar o acesso de forma várias com [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="716be-103">You can control access in several way with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="716be-104">Este tópico discute os vários mecanismos rapidamente e fornece sugestões sobre quando usar cada uma delas; destina-se a ajudá-lo a selecionar o mecanismo correto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="716be-104">This topic briefly discusses the various mechanisms and provides suggestions on when to use each; it is intended to help you select the correct mechanism to use.</span></span> <span data-ttu-id="716be-105">As tecnologias de acesso são listadas em ordem de complexidade.</span><span class="sxs-lookup"><span data-stu-id="716be-105">The access technologies are listed in order of complexity.</span></span> <span data-ttu-id="716be-106">É mais simples de <xref:System.Security.Permissions.PrincipalPermissionAttribute>; as mais complexas são o modelo de identidade.</span><span class="sxs-lookup"><span data-stu-id="716be-106">The simplest is the <xref:System.Security.Permissions.PrincipalPermissionAttribute>; the most complex is the Identity Model.</span></span>  
  
 <span data-ttu-id="716be-107">Além desses mecanismos, representação e delegação com [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] é explicado em [delegação e representação](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="716be-107">In addition to these mechanisms, impersonation and delegation with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is explained in [Delegation and Impersonation](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span></span>  
  
## <a name="principalpermissionattribute"></a><span data-ttu-id="716be-108">PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="716be-108">PrincipalPermissionAttribute</span></span>  
 <span data-ttu-id="716be-109">O <xref:System.Security.Permissions.PrincipalPermissionAttribute> é usado para restringir o acesso a um método de serviço.</span><span class="sxs-lookup"><span data-stu-id="716be-109">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is used to restrict access to a service method.</span></span> <span data-ttu-id="716be-110">Quando o atributo é aplicado a um método, ele pode ser usado para solicitar a identidade de um chamador específico ou associação em um grupo do Windows ou [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] função.</span><span class="sxs-lookup"><span data-stu-id="716be-110">When the attribute is applied to a method, it can be used to demand a specific caller's identity or membership in a Windows group or [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span> <span data-ttu-id="716be-111">Se o cliente é autenticado usando um certificado x. 509, ele recebe uma identidade primária consiste do nome da entidade e a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="716be-111">If the client is authenticated using an X.509 certificate, it is given a primary identity that consists of the subject name plus the thumbprint of the certificate.</span></span>  
  
 <span data-ttu-id="716be-112">Use o <xref:System.Security.Permissions.PrincipalPermissionAttribute> para controlar o acesso aos recursos no computador em que o serviço está em execução, e se os usuários do serviço sempre fará parte do mesmo domínio do Windows que o serviço está em execução.</span><span class="sxs-lookup"><span data-stu-id="716be-112">Use the <xref:System.Security.Permissions.PrincipalPermissionAttribute> to control access to resources on the computer that the service is running on, and if the users of the service will always be part of the same Windows domain that the service is running on.</span></span> <span data-ttu-id="716be-113">Você pode facilmente criar grupos do Windows que especificou níveis de acesso (como none, somente leitura ou leitura e gravação).</span><span class="sxs-lookup"><span data-stu-id="716be-113">You can easily create Windows groups that have specified levels of access (such as none, read-only, or read and write).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-114">usando o atributo, consulte [como: restringir o acesso com a PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="716be-114"> using the attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-115">identidade, consulte [autenticação e identidade de serviço](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="716be-115"> identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="aspnet-membership-provider"></a><span data-ttu-id="716be-116">Provedor de associação ASP.NET</span><span class="sxs-lookup"><span data-stu-id="716be-116">ASP.NET Membership Provider</span></span>  
 <span data-ttu-id="716be-117">Um recurso do [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] é o provedor de associação.</span><span class="sxs-lookup"><span data-stu-id="716be-117">A feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] is the membership provider.</span></span> <span data-ttu-id="716be-118">Mesmo que o provedor de associação não seja tecnicamente um mecanismo de controle de acesso, ele permite controlar o acesso ao serviço, limitando o conjunto de identidades possíveis que podem acessar o ponto de extremidade do serviço.</span><span class="sxs-lookup"><span data-stu-id="716be-118">Even though the membership provider is not technically an access control mechanism, it allows controlling access to the service by limiting the set of possible identities that can access the service's endpoint.</span></span> <span data-ttu-id="716be-119">O recurso de associação inclui um banco de dados que pode ser preenchido com combinações de nome e senha do usuário que permitem aos usuários de um site da Web estabelecer contas com o site.</span><span class="sxs-lookup"><span data-stu-id="716be-119">The membership feature includes a database that can be populated with user name/password combinations that enable users of a Web site to establish accounts with the site.</span></span> <span data-ttu-id="716be-120">Para acessar um serviço que usa o provedor de associação, um usuário faça logon com seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="716be-120">To access a service that uses the membership provider, a user must log on with his or her user name and password.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="716be-121">Você primeiro deve preencher o banco de dados usando o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] recurso antes de um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviço pode usá-lo para fins de autorização.</span><span class="sxs-lookup"><span data-stu-id="716be-121">You must first populate the database using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] feature before a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can use it for authorization purposes.</span></span>  
  
 <span data-ttu-id="716be-122">Você também pode usar o recurso de associação, se você já tiver um banco de dados de associação de uma já existente [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] site da Web e você deseja habilitar os mesmos usuários usar o serviço autorizado com os mesmos nomes de usuário e senhas.</span><span class="sxs-lookup"><span data-stu-id="716be-122">You can also use the membership feature if you already have a membership database from an existing [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web site and you want to enable the same users to use your service, authorized with the same user names and passwords.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-123">usando o recurso de associação em um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de serviço, consulte [como: usar o provedor de associação ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="716be-123"> using the membership feature in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
## <a name="aspnet-role-provider"></a><span data-ttu-id="716be-124">Provedor de função do ASP.NET</span><span class="sxs-lookup"><span data-stu-id="716be-124">ASP.NET Role Provider</span></span>  
 <span data-ttu-id="716be-125">Outro recurso do [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] é a capacidade de gerenciar o uso de funções de autorização.</span><span class="sxs-lookup"><span data-stu-id="716be-125">Another feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] is the ability to manage authorization using roles.</span></span> <span data-ttu-id="716be-126">O [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provedor de função permite que um desenvolvedor para criar funções para usuários e atribua a cada usuário a uma função ou funções.</span><span class="sxs-lookup"><span data-stu-id="716be-126">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider enables a developer to create roles for users and to assign each user to a role or roles.</span></span> <span data-ttu-id="716be-127">Como com o provedor de associação, as funções e atribuições são armazenadas em um banco de dados e pode ser preenchidas usando as ferramentas fornecidas por uma implementação específica do [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provedor de função.</span><span class="sxs-lookup"><span data-stu-id="716be-127">As with the membership provider, the roles and assignments are stored in a database, and can be populated using tools provided by a particular implementation of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider.</span></span> <span data-ttu-id="716be-128">Assim como acontece com o recurso de associação, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] os desenvolvedores podem usar as informações no banco de dados para autorizar usuários do serviço de funções.</span><span class="sxs-lookup"><span data-stu-id="716be-128">As with the membership feature, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] developers can use the information in the database to authorize service users by roles.</span></span> <span data-ttu-id="716be-129">Por exemplo, eles podem usar o provedor de função em combinação com o `PrincipalPermissionAttribute` descrito acima do mecanismo de controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="716be-129">They can, for example, use the role provider in combination with the `PrincipalPermissionAttribute` access control mechanism described above.</span></span>  
  
 <span data-ttu-id="716be-130">Você também pode usar o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provedor de função, se você tiver uma [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] banco de dados de provedor de função e desejar usar o mesmo conjunto de regras e as atribuições de usuário no seu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviço.</span><span class="sxs-lookup"><span data-stu-id="716be-130">You can also use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider if you have an existing [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider database and want to use the same set of rules and user assignments in your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-131">usando o recurso de provedor de função, consulte [como: usar o provedor de função ASP.NET com um serviço](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="716be-131"> using the role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
## <a name="authorization-manager"></a><span data-ttu-id="716be-132">Gerenciador de autorização</span><span class="sxs-lookup"><span data-stu-id="716be-132">Authorization Manager</span></span>  
 <span data-ttu-id="716be-133">Outro recurso combina o Gerenciador de autorização (AzMan) com o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provedor de função para autorizar clientes.</span><span class="sxs-lookup"><span data-stu-id="716be-133">Another feature combines the Authorization Manager (AzMan) with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider to authorize clients.</span></span> <span data-ttu-id="716be-134">Quando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda um serviço Web, AzMan pode ser integrado no aplicativo para que a autorização para o serviço é feita por meio do AzMan.</span><span class="sxs-lookup"><span data-stu-id="716be-134">When [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hosts a Web service, AzMan can be integrated into the application so that authorization to the service is done through AzMan.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="716be-135">Gerenciador de função fornece uma API que permite gerenciar funções de aplicativo, adicionar e remover usuários das funções e verificar a associação de função, mas não permite consultar se um usuário está autorizado a executar uma tarefa nomeada ou a operação.</span><span class="sxs-lookup"><span data-stu-id="716be-135"> role manager provides an API that enables you to manage application roles, add and remove users from roles, and check role membership, but it does not allow you to query whether a user is authorized to perform a named task or operation.</span></span> <span data-ttu-id="716be-136">AzMan permite definir as operações individuais e combiná-los em tarefas.</span><span class="sxs-lookup"><span data-stu-id="716be-136">AzMan allows you to define individual operations and combine them into tasks.</span></span> <span data-ttu-id="716be-137">Com o AZMan, além de verificações de função, você também pode verificar se um usuário pode executar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="716be-137">With AZMan, in addition to role checks, you can also check whether a user can perform a task.</span></span> <span data-ttu-id="716be-138">Autorização de atribuição e tarefa de função pode ser configurada fora do aplicativo ou por meio de programação executada dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="716be-138">Role assignment and task authorization can be configured outside of the application or performed programmatically within the application.</span></span> <span data-ttu-id="716be-139">A administração de AzMan snap-in do Console de gerenciamento Microsoft (MMC) permite que os administradores para alterar as tarefas que pode executar uma função em tempo de execução e para gerenciar a associação de cada usuário de funções.</span><span class="sxs-lookup"><span data-stu-id="716be-139">The AzMan administration Microsoft Management Console (MMC) snap-in allows administrators to change the tasks a role can perform at run time and to manage each user's membership of roles.</span></span>  
  
 <span data-ttu-id="716be-140">Você também pode usar o AzMan e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provedor de função, se você já tiver acesso a uma instalação existente do AzMan e deseja autorizar seus usuários de serviço usando os recursos da combinação de provedor AzMan/função.</span><span class="sxs-lookup"><span data-stu-id="716be-140">You can also use AzMan and the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider if you already have access to an existing AzMan installation and want to authorize your service users using the features of the AzMan/role provider combination.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-141">AzMan e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provedor de função, consulte [como: Use o Gerenciador de autorização (AzMan) com o ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=88951).</span><span class="sxs-lookup"><span data-stu-id="716be-141"> AzMan and the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider, see [How To: Use Authorization Manager (AzMan) with ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=88951).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-142">usando o provedor de função para e de AzMan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviços, consulte [como: usar o provedor de função do Gerenciador de autorização ASP.NET com um serviço](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="716be-142"> using AzMan and the role provider for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, see [How to: Use the ASP.NET Authorization Manager Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).</span></span>  
  
## <a name="identity-model"></a><span data-ttu-id="716be-143">Modelo de identidade</span><span class="sxs-lookup"><span data-stu-id="716be-143">Identity Model</span></span>  
 <span data-ttu-id="716be-144">O modelo de identidade é um conjunto de APIs que permitem gerenciar políticas e declarações para autorizar clientes.</span><span class="sxs-lookup"><span data-stu-id="716be-144">The Identity Model is a set of APIs that enable you to manage claims and policies to authorize clients.</span></span> <span data-ttu-id="716be-145">Com o modelo de identidade, você pode examinar cada declaração contida nas credenciais que o chamador usado para autenticar para o serviço, compare as declarações para o conjunto de políticas para o serviço e conceder ou negar acesso com base na comparação.</span><span class="sxs-lookup"><span data-stu-id="716be-145">With the Identity Model, you can examine every claim contained in credentials that the caller used to authenticate itself to the service, compare the claims to the set of policies for the service, and grant or deny access based on the comparison.</span></span>  
  
 <span data-ttu-id="716be-146">Use o modelo de identidade se você precisa excelente controle e a capacidade de definir os critérios específicos antes de conceder acesso.</span><span class="sxs-lookup"><span data-stu-id="716be-146">Use the Identity Model if you need fine control and the ability to set specific criteria before granting access.</span></span> <span data-ttu-id="716be-147">Por exemplo, ao usar o <xref:System.Security.Permissions.PrincipalPermissionAttribute>, o critério é que a identidade do usuário é autenticada e pertence a uma função específica.</span><span class="sxs-lookup"><span data-stu-id="716be-147">For example, when using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, the criterion is simply that the identity of the user is authenticated and belongs to a specific role.</span></span> <span data-ttu-id="716be-148">Por outro lado, usando o modelo de identidade, você pode criar uma diretiva que informa o usuário deve ser mais de 18 anos de idade e possui de motorista uma válido carteira antes de terem permissão para exibir um documento.</span><span class="sxs-lookup"><span data-stu-id="716be-148">In contrast, using the Identity Model, you can create a policy that states the user must be over 18 years of age and possesses a valid driver's license before being allowed to view a document.</span></span>  
  
 <span data-ttu-id="716be-149">Um exemplo onde você pode aproveitar o controle de acesso baseado em declaração de modelo de identidade é ao usar credenciais de federação no cenário do token emitido.</span><span class="sxs-lookup"><span data-stu-id="716be-149">One example where you can benefit from the Identity Model claim-based access control is when using federation credentials in the issued token scenario.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-150">Federação e tokens emitidos, consulte [federação e Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="716be-150"> federation and issued tokens, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="716be-151">o modelo de identidade, consulte [Gerenciando reivindicações e autorização com o modelo de identidade](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="716be-151"> the Identity Model, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716be-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="716be-152">See Also</span></span>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <span data-ttu-id="716be-153">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md) (Como restringir o acesso com a classe PrincipalPermissionAttribute)</span><span class="sxs-lookup"><span data-stu-id="716be-153">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)</span></span>  
 [<span data-ttu-id="716be-154">Como: usar o provedor de função ASP.NET com um serviço</span><span class="sxs-lookup"><span data-stu-id="716be-154">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="716be-155">Como: usar o provedor de função do Gerenciador de autorização ASP.NET com um serviço</span><span class="sxs-lookup"><span data-stu-id="716be-155">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [<span data-ttu-id="716be-156">Gerenciando reivindicações e autorização com o modelo de identidade</span><span class="sxs-lookup"><span data-stu-id="716be-156">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="716be-157">Delegação e representação</span><span class="sxs-lookup"><span data-stu-id="716be-157">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)