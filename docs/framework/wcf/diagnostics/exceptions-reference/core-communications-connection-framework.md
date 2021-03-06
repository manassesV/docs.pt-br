---
title: "Comunicações principais: estrutura de conexão"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713788f8938e43f3516edd95646fc6dc653a56c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="core-communications-connection-framework"></a>Comunicações principais: estrutura de conexão
Este tópico lista todas as exceções geradas pelo [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Framework de Conexão.  
  
## <a name="exception-list"></a>Lista de exceções  
  
|Código do recurso|Cadeia de caracteres de recurso|  
|-------------------|---------------------|  
|CloseTimedOut|O método Close atingiu o tempo limite após o período especificado. Aumente o valor de tempo limite que é passado para a chamada para fechar ou aumente o valor de CloseTimeout na associação. O tempo determinado para essa operação pode ter sido uma parte de um tempo limite maior.|  
|ContentTypeMismatch|O tipo de conteúdo especificado foi enviado a um serviço que estava esperando especificado. As associações de cliente e serviço talvez não sejam compatíveis.|  
|DuplexChannelAbortedDuringOpen|O canal duplex para especificado foi finalizado durante o processo de abertura.|  
|FramingValueNotAvailable|O valor não pode ser acessado porque ele não é totalmente decodificado.|  
|OperationAbortedDuringConnectionEstablishment|A operação foi encerrada ao estabelecer uma conexão especificado.|  
|ReceiveTimedOut2|A operação de recebimento expirou após o período especificado. O tempo determinado para essa operação pode ter sido uma parte de um tempo limite maior.|  
|SendCannotBeCalledAfterCloseOutputSession|Você não pode enviar mensagens em um canal após CloseOutputSession ter sido chamado.|
