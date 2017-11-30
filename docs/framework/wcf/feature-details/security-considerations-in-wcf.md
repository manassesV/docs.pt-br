---
title: "Considerações de segurança no WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c0af5a5d96f20b2ba5118909a3f0c5ba405bdb11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="security-considerations-in-wcf"></a>Considerações de segurança no WCF
Os tópicos nesta seção listam vários itens relacionados à segurança a serem considerados durante a criação de um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aplicativo.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Divulgação de informações](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 Discute as várias maneiras que informações podem ser divulgadas ou atacadas e como mitigar isso.  
  
 [Elevação de privilégio](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 Discute os efeitos de conceder permissões de autorização um invasor além daquelas concedidas inicialmente e como mitigar isso.  
  
 [Negação de serviço](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 Discute o que acontece quando um sistema não pode processar mensagens adequadamente e como resolvê-la.  
  
 [Violação](../../../../docs/framework/wcf/feature-details/tampering.md)  
 Discute a alteração de mensagens ou a entrega de mensagens e como resolvê-la.  
  
 [Ataques de repetição](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 Discute o que acontece quando um invasor copia um fluxo de mensagens entre duas partes e repete o fluxo para um ou mais partes e como mitigar isso.  
  
 [Considerações sobre segurança para sessões seguras](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 Discute os seguintes itens que afetam a segurança ao implementar sessões seguras.  
  
 [Cenários sem suporte](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 Lista os vários cenários que não oferecem suporte a um aspecto específico de segurança e devem ser evitados ou considerados.  
  
## <a name="reference"></a>Referência  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Orientações de segurança e práticas recomendadas](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Consulte também  
 [Segurança](../../../../docs/framework/wcf/feature-details/security.md)