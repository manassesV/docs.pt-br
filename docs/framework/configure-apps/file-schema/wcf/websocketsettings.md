---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ee0f555fc1e3412032e0a7dda3a747bbfef6f4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
Um elemento de configuração usado para especificar configurações de soquete da Web.  
  
\<sistema. ServiceModel >  
\<associações >  
\<netHttpBinding >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|createNotificationOnConnection|Especifica se uma notificação será enviada após a conexão.|  
|disablePayloadMasking|Especifica se o mascaramento de soquete da Web está desabilitado.|  
|keepAliveInterval|Especifica o intervalo de keep alive.|  
|maxPendingConnections|Especifica o número máximo de conexões que estão aguardando envio no serviço.|  
|receiveBufferSize|Especifica o tamanho do buffer de recepção.|  
|sendBufferSize|Especifica o tamanho do buffer de envio.|  
|subprotocolo|Especifica o subprotocolo de soquete da Web.|  
|transportUsage|Especifica quando usar soquetes da Web.|  
  
## <a name="transportusage-attribute"></a>transportUsage atributo  
  
|Valor|Descrição|  
|-----------|-----------------|  
|WhenDuplex|Use o protocolo de soquete da Web quando o contrato é duplex.|  
|Sempre|Sempre use o protocolo de soquete da Web, independentemente do contrato.|  
|Nunca|Nunca use o protocolo de soquete da Web.|  
  
### <a name="child-elements"></a>Elementos filho  
 Nenhum  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|\<netHttpBinding >|Especifica o NetHttpBinding|  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir mostra como usar o \<webSocketSettings > elemento.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Associações](../../../../../docs/framework/wcf/bindings.md)  
 [Configurando associações fornecidas pelo sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Usando associações para configurar clientes e serviços do Windows Communication Foundation](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<associação >](../../../../../docs/framework/misc/binding.md)
