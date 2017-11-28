---
title: '&lt;gcAllowVeryLargeObjects&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49046c343ef749e597402f7e19a08fe1f2c98ca0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltgcallowverylargeobjectsgt-element"></a><span data-ttu-id="d653e-102">&lt;gcAllowVeryLargeObjects&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d653e-102">&lt;gcAllowVeryLargeObjects&gt; Element</span></span>
<span data-ttu-id="d653e-103">Em plataformas de 64 bits, habilita matrizes com mais de 2 gigabytes (GB) de tamanho total.</span><span class="sxs-lookup"><span data-stu-id="d653e-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="d653e-104">\<Configuração > elemento</span><span class="sxs-lookup"><span data-stu-id="d653e-104">\<configuration> Element</span></span>  
<span data-ttu-id="d653e-105">\<tempo de execução > elemento</span><span class="sxs-lookup"><span data-stu-id="d653e-105">\<runtime> Element</span></span>  
<span data-ttu-id="d653e-106">\<gcAllowVeryLargeObjects > elemento</span><span class="sxs-lookup"><span data-stu-id="d653e-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d653e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d653e-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d653e-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d653e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d653e-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="d653e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d653e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d653e-110">Attributes</span></span>  
  
|<span data-ttu-id="d653e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d653e-111">Attribute</span></span>|<span data-ttu-id="d653e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="d653e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d653e-113">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d653e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d653e-114">Especifica se as matrizes que são maiores que 2 GB de tamanho total estão habilitadas em plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d653e-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d653e-115">Atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="d653e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d653e-116">Valor</span><span class="sxs-lookup"><span data-stu-id="d653e-116">Value</span></span>|<span data-ttu-id="d653e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="d653e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d653e-118">Matrizes com mais de 2 GB de tamanho total não estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="d653e-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="d653e-119">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="d653e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d653e-120">Maiores que 2 GB de tamanho total de matrizes são habilitados em plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d653e-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d653e-121">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d653e-121">Child Elements</span></span>  
 <span data-ttu-id="d653e-122">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d653e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d653e-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d653e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d653e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d653e-124">Element</span></span>|<span data-ttu-id="d653e-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="d653e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d653e-126">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d653e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d653e-127">Contém informações sobre opções de inicialização do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d653e-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d653e-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="d653e-128">Remarks</span></span>  
 <span data-ttu-id="d653e-129">Usar esse elemento no arquivo de configuração de aplicativo permite que as matrizes que são maiores do que 2 GB de tamanho, mas não alterar outros limites de tamanho do objeto ou o tamanho da matriz:</span><span class="sxs-lookup"><span data-stu-id="d653e-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
-   <span data-ttu-id="d653e-130">O número máximo de elementos em uma matriz é <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d653e-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="d653e-131">O índice máximo em uma única dimensão é 2,147,483,591 (0x7FFFFFC7) para matrizes de bytes e matrizes de estruturas de byte único e 2,146,435,071 (0X7FEFFFFF) para outros tipos.</span><span class="sxs-lookup"><span data-stu-id="d653e-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
-   <span data-ttu-id="d653e-132">O tamanho máximo de cadeias de caracteres e outros objetos de matriz não é alterado.</span><span class="sxs-lookup"><span data-stu-id="d653e-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d653e-133">Antes de habilitar esse recurso, certifique-se de que seu aplicativo não incluir o código não seguro que pressupõe que todas as matrizes são menores que 2 GB de tamanho.</span><span class="sxs-lookup"><span data-stu-id="d653e-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="d653e-134">Por exemplo, o código não seguro que usa matrizes como buffers pode ser suscetível a saturações de buffer se ele está escrito na suposição de que matrizes não deve exceder 2 GB.</span><span class="sxs-lookup"><span data-stu-id="d653e-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d653e-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d653e-135">Example</span></span>  
 <span data-ttu-id="d653e-136">O exemplo a seguir mostra como habilitar esse recurso para um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d653e-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d653e-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d653e-137">See Also</span></span>  
 [<span data-ttu-id="d653e-138">Esquema de configurações do tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d653e-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d653e-139">Esquema de arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="d653e-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)