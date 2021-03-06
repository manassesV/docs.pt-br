---
title: '&lt;issuedToken&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c4090dacdbb55f66bf7c27bdd02adf371049f7b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuedtokengt"></a>&lt;issuedToken&gt;
Especifica um token personalizado usado para autenticar um cliente para um serviço.  
  
 \<sistema. ServiceModel >  
\<comportamentos >  
seção endpointBehaviors  
\<comportamento >  
\<clientCredentials >  
\<issuedToken >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<issuedToken   
   cacheIssuedTokens="Boolean"  
   defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"  
   issuedTokenRenewalThresholdPercentage = "0 to 100"  
   issuerChannelBehaviors="String"  
      localIssuerChannelBehaviors="String"  
   maxIssuedTokenCachingTime="TimeSpan"  
</issuedToken>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`cacheIssuedTokens`|Atributo booleano opcional que especifica se tokens são armazenados em cache. O padrão é `true`.|  
|`defaultKeyEntropyMode`|Atributo de cadeia de caracteres opcional que especifica quais valores aleatórios (entropias) são usados para operações de handshake. Os valores incluem `ClientEntropy`, `ServerEntropy`, e `CombinedEntropy`, o padrão é `CombinedEntropy`. Esse atributo é do tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`issuedTokenRenewalThresholdPercentage`|Atributo inteiro opcional que especifica a porcentagem de um período válido (fornecido pelo emissor de token) que pode decorrer antes que um token seja renovado. Os valores são de 0 a 100. O padrão é 60, que especifica a 60% de tempo passa antes de tentar uma renovação.|  
|`issuerChannelBehaviors`|Atributo opcional que especifica os comportamentos de canal para usar ao se comunicar com o emissor.|  
|`localIssuerChannelBehaviors`|Atributo opcional que especifica os comportamentos de canal para usar ao se comunicar com o emissor local.|  
|`maxIssuedTokenCachingTime`|Atributo Timespan opcional que especifica a duração que tokens emitidos são armazenados em cache quando o emissor do token (um STS) não especificar uma hora. O padrão é "10675199.02:48:05.4775807".|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<localIssuer >](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Especifica o endereço do emissor do token e a associação usada para se comunicar com o ponto de extremidade local.|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Especifica os comportamentos de ponto de extremidade a ser usado ao entrar em contato com um emissor local.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica as credenciais usadas para autenticar um cliente para um serviço.|  
  
## <a name="remarks"></a>Comentários  
 Um token emitido é um tipo de credencial personalizada usado, por exemplo, durante a autenticação com um Token STS (serviço seguro) em um cenário federado. Por padrão, o token é um token SAML. Para obter mais informações, consulte [federação e Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). e [federação e Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Esta seção contém os elementos usados para configurar um emissor local de tokens ou comportamentos usados com um serviço de token de segurança. Para obter instruções sobre como configurar um cliente para usar um emissor local, consulte [como: configurar um emissor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [Comportamentos de segurança](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Protegendo serviços e clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Federação e tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Protegendo clientes](../../../../../docs/framework/wcf/securing-clients.md)  
 [Como criar um cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Como configurar um emissor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Federação e tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
