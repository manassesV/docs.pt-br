---
title: "Funções espaciais"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c482c2f79c6416a4e748599c896280b426d31ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="spatial-functions"></a>Funções espaciais
Não há nenhum formato literal para tipos espaciais. Entretanto, você pode usar funções canônicas do Entity Framework que você chama usando cadeias de caracteres no formato de texto bem conhecido. Por exemplo, a chamada de função a seguir cria um ponto geométrico:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 O [SpatialEdmFunctions métodos](http://msdn.microsoft.com/library/hh749531.aspx) página lista todos os métodos Entity Framework canônicos espaciais. Clique em um método de interesse ver quais parâmetros devem ser passados para uma função.
