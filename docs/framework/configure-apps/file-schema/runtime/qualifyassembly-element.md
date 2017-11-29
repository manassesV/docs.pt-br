---
title: '&lt;qualifyAssembly&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 521bbccd83f224cc824dae41309715d65472454e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="663ff-102">&lt;qualifyAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="663ff-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="663ff-103">Especifica o nome completo do assembly que deve ser carregado dinamicamente quando um nome parcial é usado.</span><span class="sxs-lookup"><span data-stu-id="663ff-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="663ff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="663ff-104">\<configuration></span></span>  
<span data-ttu-id="663ff-105">\<tempo de execução ></span><span class="sxs-lookup"><span data-stu-id="663ff-105">\<runtime></span></span>  
<span data-ttu-id="663ff-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="663ff-106">\<assemblyBinding></span></span>  
<span data-ttu-id="663ff-107">\<qualifyAssembly ></span><span class="sxs-lookup"><span data-stu-id="663ff-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663ff-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="663ff-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="663ff-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="663ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="663ff-110">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="663ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="663ff-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="663ff-111">Attributes</span></span>  
  
|<span data-ttu-id="663ff-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="663ff-112">Attribute</span></span>|<span data-ttu-id="663ff-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="663ff-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="663ff-114">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="663ff-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="663ff-115">Especifica o nome parcial do assembly como ele aparece no código.</span><span class="sxs-lookup"><span data-stu-id="663ff-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="663ff-116">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="663ff-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="663ff-117">Especifica o nome completo do assembly como ele aparece no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="663ff-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="663ff-118">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="663ff-118">Child Elements</span></span>  
 <span data-ttu-id="663ff-119">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="663ff-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="663ff-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="663ff-120">Parent Elements</span></span>  
  
|<span data-ttu-id="663ff-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="663ff-121">Element</span></span>|<span data-ttu-id="663ff-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="663ff-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="663ff-123">Contém informações sobre o redirecionamento de versão e os locais dos assemblies.</span><span class="sxs-lookup"><span data-stu-id="663ff-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="663ff-124">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="663ff-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="663ff-125">Contém informações sobre associação do assembly e coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="663ff-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="663ff-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="663ff-126">Remarks</span></span>  
 <span data-ttu-id="663ff-127">Chamar o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> método usando nomes de assembly parcial faz com que o common language runtime procurar o assembly apenas no diretório base do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="663ff-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="663ff-128">Use o  **\<qualifyAssembly >** elemento no arquivo de configuração de aplicativo para fornecer as informações de assembly completo (nome, versão, token de chave pública e cultura) e fazer com que o common language runtime a ser pesquisado para o assembly no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="663ff-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="663ff-129">O **fullName** atributo deve incluir os quatro campos de identidade de assembly: nome, versão, token de chave pública e cultura.</span><span class="sxs-lookup"><span data-stu-id="663ff-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="663ff-130">O **partialName** atributo parcialmente deve fazer referência a um assembly.</span><span class="sxs-lookup"><span data-stu-id="663ff-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="663ff-131">Você deve especificar pelo menos o nome do assembly texto (o caso mais comum), mas você também pode incluir a versão, token de chave pública, ou cultura (ou qualquer combinação de quatro, mas não todos os quatro).</span><span class="sxs-lookup"><span data-stu-id="663ff-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="663ff-132">O **partialName** deve corresponder ao nome especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="663ff-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="663ff-133">Por exemplo, você não pode especificar `"math"` como o **partialName** atributo em seu arquivo de configuração e a chamada `Assembly.Load("math, Version=3.3.3.3")` em seu código.</span><span class="sxs-lookup"><span data-stu-id="663ff-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="663ff-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="663ff-134">Example</span></span>  
 <span data-ttu-id="663ff-135">O exemplo a seguir ativa logicamente a chamada `Assembly.Load("math")` em `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="663ff-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="663ff-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="663ff-136">See Also</span></span>  
 [<span data-ttu-id="663ff-137">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="663ff-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="663ff-138">Como o tempo de execução localiza assemblies</span><span class="sxs-lookup"><span data-stu-id="663ff-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="663ff-139">NIB: Referências de Assembly parcial</span><span class="sxs-lookup"><span data-stu-id="663ff-139">NIB: Partial Assembly References</span></span>](http://msdn.microsoft.com/en-us/ec90f07a-398c-4306-9401-0fc5ff9cb59f)