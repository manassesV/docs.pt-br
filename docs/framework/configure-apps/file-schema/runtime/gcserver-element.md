---
title: '&lt;gcServer&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 207aeb1f9faf9be6ac547d8dd8acc80e8a4cb42f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltgcservergt-element"></a>&lt;gcServer&gt; elemento
Especifica se o Common Language Runtime executa a coleta de lixo do servidor.  
  
 \<configuration>  
\<tempo de execução >  
\<gcServer >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`enabled`|Atributo obrigatório.<br /><br /> Especifica se o tempo de execução executa a coleta de lixo do servidor.|  
  
## <a name="enabled-attribute"></a>Atributo habilitado  
  
|Valor|Descrição|  
|-----------|-----------------|  
|`false`|Não é executada a coleta de lixo do servidor. Esse é o padrão.|  
|`true`|Executa a coleta de lixo do servidor.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|`configuration`|O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.|  
|`runtime`|Contém informações sobre associação do assembly e coleta de lixo.|  
  
## <a name="remarks"></a>Comentários  
 O common language runtime (CLR) dá suporte a dois tipos de coleta de lixo: coleta de lixo da estação de trabalho, que está disponível em todos os sistemas, e coleta de lixo do servidor, que está disponível em sistemas com vários processadores. Você usa o `<gcServer>` elemento para controlar o tipo de coleta de lixo CLR executa. Use o <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> propriedade para determinar se a coleta de lixo do servidor está habilitada.  
  
 Para computadores com processador único, a coleta de lixo de estação de trabalho padrão deve ser a opção mais rápida. Estação de trabalho ou servidor pode ser usado para o processador de dois computadores. Coleta de lixo do servidor deve ser a opção mais rápida para mais de dois processadores.  
  
 Esse elemento pode ser usado apenas no arquivo de configuração do aplicativo; ele será ignorado se for no arquivo de configuração da máquina.  
  
> [!NOTE]
>  No .NET Framework 4 e versões anteriores, coleta de lixo simultânea não está disponível quando a coleta de lixo do servidor está habilitada. Começando com o [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], coleta de lixo do servidor é simultânea. Para usar a coleta de lixo não simultânea server, defina a `<gcServer>` elemento `true` e [ \<gcConcurrent > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) para `false`.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir habilita a coleta de lixo de servidor.  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>  
 [Esquema de configurações do tempo de execução](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de arquivos de configuração](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Como: desabilitar a coleta de lixo simultânea](http://msdn.microsoft.com/en-us/ba2c6c67-5778-497c-9fac-5f793b5500c7)
