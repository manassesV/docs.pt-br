---
title: "Comunicações principais: Suporte de Webhost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8fd3ab00f8a0bf26a463e30556826c09820869f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="core-communications-webhost-support"></a>Comunicações principais: Suporte de Webhost
Este tópico lista todas as exceções geradas pelo suporte de Webhost.  
  
## <a name="exception-list"></a>Lista de exceções  
  
|Código do recurso|Cadeia de caracteres de recurso|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|Esse serviço requer compatibilidade com ASP.NET. Ele também deve ser hospedado no IIS. Hospede o serviço no IIS com compatibilidade com ASP.NET ativada em Web. config ou defina a propriedade AspNetCompatibilityRequirementsAttribute AspNetCompatibilityRequirementsMode para um valor diferente Required.|  
|Hosting_ListenerNotFoundForActivationInRecycling|Nenhum canal ativamente está escutando no endereço especificado. Se a reciclagem de um aplicativo, o serviço está fechado.|  
|Hosting_NonHTTPInCompatibilityMode|Somente os protocolos que têm suporte na compatibilidade com ASP.NET são HTTP e HTTPS. Remova o ponto de extremidade especificado ou desativar a compatibilidade com ASP.NET para o aplicativo.|  
|Hosting_ProcessNotExecutingUnderHostedContext|O processcannot de hospedagem especificado ser chamado dentro do ambiente de hospedagem atual. Esta API exige que o aplicativo de chamada ser hospedados em serviços de informações da Internet ou o serviço de ativação de processos do Windows.|  
|Hosting_ServiceCompatibilityRequire|O serviço não pode ser ativado porque ele requer compatibilidade com ASP.NET. Compatibilidade com ASP.NET não está habilitada para este aplicativo. Habilitar compatibilidade com ASP.NET no arquivo Web. config ou defina o AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
