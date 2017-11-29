---
title: "&lt;schemeSettings&gt; (configurações de Uri) do elemento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4cf1d2013a51985f9d7772ac0ef86e5dbb120be9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="a046a-102">&lt;schemeSettings&gt; (configurações de Uri) do elemento</span><span class="sxs-lookup"><span data-stu-id="a046a-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="a046a-103">Especifica como um <xref:System.Uri> será analisado quanto a esquemas específicos.</span><span class="sxs-lookup"><span data-stu-id="a046a-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="a046a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a046a-104">\<configuration></span></span>  
<span data-ttu-id="a046a-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="a046a-105">\<uri></span></span>  
<span data-ttu-id="a046a-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="a046a-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a046a-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a046a-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a046a-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a046a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a046a-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="a046a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a046a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a046a-110">Attributes</span></span>  
 <span data-ttu-id="a046a-111">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a046a-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a046a-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a046a-112">Child Elements</span></span>  
  
|<span data-ttu-id="a046a-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a046a-113">**Element**</span></span>|<span data-ttu-id="a046a-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a046a-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a046a-115">add</span><span class="sxs-lookup"><span data-stu-id="a046a-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a046a-116">Adiciona uma configuração de esquema para um nome de esquema.</span><span class="sxs-lookup"><span data-stu-id="a046a-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="a046a-117">clear</span><span class="sxs-lookup"><span data-stu-id="a046a-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a046a-118">Limpa todas as configurações existentes do esquema.</span><span class="sxs-lookup"><span data-stu-id="a046a-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="a046a-119">remove</span><span class="sxs-lookup"><span data-stu-id="a046a-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a046a-120">Remove uma configuração de esquema para um nome de esquema.</span><span class="sxs-lookup"><span data-stu-id="a046a-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a046a-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a046a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a046a-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a046a-122">**Element**</span></span>|<span data-ttu-id="a046a-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a046a-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a046a-124">URI</span><span class="sxs-lookup"><span data-stu-id="a046a-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="a046a-125">Contém configurações que especificam como o .NET Framework controla endereços da web expressados usando identificadores de recurso uniformes (URIs).</span><span class="sxs-lookup"><span data-stu-id="a046a-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a046a-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="a046a-126">Remarks</span></span>  
 <span data-ttu-id="a046a-127">Por padrão, o <xref:System.Uri?displayProperty=nameWithType> por cento de escapa Cancelar classe codificado delimitadores de caminho antes de executar a compactação de caminho.</span><span class="sxs-lookup"><span data-stu-id="a046a-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="a046a-128">Isso foi implementado como um mecanismo de segurança contra ataques semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="a046a-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a046a-129">Se esse URI é passado para módulos não tratamento % caracteres codificados corretamente, isso poderia resultar no comando a seguir, que está sendo executado pelo servidor:</span><span class="sxs-lookup"><span data-stu-id="a046a-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="a046a-130">Por esse motivo, <xref:System.Uri?displayProperty=nameWithType> classe delimitadores de caminho escapes cancelar primeiro e, em seguida, aplica-se a compactação de caminho.</span><span class="sxs-lookup"><span data-stu-id="a046a-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="a046a-131">O resultado de passar a URL mal-intencionada acima para <xref:System.Uri?displayProperty=nameWithType> classe resultados construtor no seguinte URI:</span><span class="sxs-lookup"><span data-stu-id="a046a-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a046a-132">Esse comportamento padrão pode ser modificado para não cancelar escape porcentagem codificado delimitadores de caminho usando a opção de configuração schemeSettings para um esquema específico.</span><span class="sxs-lookup"><span data-stu-id="a046a-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a046a-133">Arquivos de Configuração</span><span class="sxs-lookup"><span data-stu-id="a046a-133">Configuration Files</span></span>  
 <span data-ttu-id="a046a-134">Esse elemento pode ser usado no arquivo de configuração do aplicativo ou o arquivo de configuração de máquina (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="a046a-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a046a-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a046a-135">Example</span></span>  
 <span data-ttu-id="a046a-136">O exemplo a seguir mostra uma configuração usada pela <xref:System.Uri> classe para dar suporte a saída não delimitadores de caminho codificados por percentual para o esquema http.</span><span class="sxs-lookup"><span data-stu-id="a046a-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="a046a-137">Informações do elemento</span><span class="sxs-lookup"><span data-stu-id="a046a-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="a046a-138">Namespace</span><span class="sxs-lookup"><span data-stu-id="a046a-138">Namespace</span></span>|<span data-ttu-id="a046a-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="a046a-139">System</span></span>|  
|<span data-ttu-id="a046a-140">Nome do esquema</span><span class="sxs-lookup"><span data-stu-id="a046a-140">Schema Name</span></span>||  
|<span data-ttu-id="a046a-141">Arquivo de validação</span><span class="sxs-lookup"><span data-stu-id="a046a-141">Validation File</span></span>||  
|<span data-ttu-id="a046a-142">Pode ser vazio</span><span class="sxs-lookup"><span data-stu-id="a046a-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a046a-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a046a-143">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="a046a-144">Esquema de configurações de rede</span><span class="sxs-lookup"><span data-stu-id="a046a-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)