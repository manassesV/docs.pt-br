---
title: "Funções de data e hora"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 559d6c8bf6abb0dd021784046b3161c799b58df4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="date-and-time-functions"></a>Funções de data e hora
O provedor de dados. NET Framework para SQL Server (SqlClient) fornece funções de data e hora que executam operações em uma entrada de `System.DateTime` avalia e retorna um resultado de `string`, numérico, ou de `System.DateTime` de valor. Essas funções estão no namespace SqlServer, que está disponível quando você usa o SqlClient. A propriedade de namespace de um provedor permite que Entity Framework descobrir que prefixo é usado por esse provedor para compilações específicas, como tipos e funções. A tabela a seguir mostra as funções de data e hora SqlClient.  
  
|Função|Descrição|  
|--------------|-----------------|  
|`DATEADD(` `datepart`, `number`, `date``)`|Retorna um novo valor de `DateTime` que é baseado em adicionar um intervalo para a data especificada.<br /><br /> **Argumentos**<br /><br /> `datepart`: `String` que representa a parte de data para retornar um novo valor.<br /><br /> `number`: `Int32`, `Int64`, `Decimal`, ou valor de `Double` usado para incrementar `datepart`.<br /><br /> `date:`Uma expressão que retorna um `DateTime`, ou `DateTimeOffset`, ou `Time` com precisão = [0-7], ou uma cadeia de caracteres em um formato de data.<br /><br /> **Valor retornado**<br /><br /> Novo `DateTime`, ou `DateTimeOffset`, ou valor de `Time` com precisão = [] 0-7.<br /><br /> **Exemplo**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(` `datepart`, `startdate`, `enddate``)`|Retorna o número de limites de data e hora cruzados entre duas datas especificado.<br /><br /> **Argumentos**<br /><br /> `datepart`: `String` que representa a parte de data para calcular a diferença.<br /><br /> `startdate`: Uma data de início para o cálculo é uma expressão que retorna `DateTime`, ou `DateTimeOffset`, ou valor de `Time` com precisão = [] 0-7, ou uma cadeia de caracteres em um formato de data.<br /><br /> `enddate:`Uma data de término para o cálculo é uma expressão que retorna um `DateTime`, ou `DateTimeOffset`, ou `Time` valor com precisão = [0-7], ou uma cadeia de caracteres em um formato de data.<br /><br /> **Valor retornado**<br /><br /> Um `Int32`.<br /><br /> **Exemplo**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(` `datepart`, `date``)`|Retorna uma cadeia de caracteres que representa o datepart especificado de data especificada.<br /><br /> **Argumentos**<br /><br /> `datepart`: `String` que representa a parte de data para retornar um novo valor.<br /><br /> `date`: Uma expressão que retorna `DateTime,` ou `DateTimeOffset`, ou valor de `Time` com precisão = [] 0-7, ou uma cadeia de caracteres em um formato de data.<br /><br /> **Valor retornado**<br /><br /> A cadeia de caracteres que representa o datepart especificado de data especificada.<br /><br /> **Exemplo**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(` `datepart`, `date``)`|Retorna um inteiro que representa o datepart especificado de data especificada.<br /><br /> **Argumentos**<br /><br /> `datepart`: `String` que representa a parte de data para retornar um novo valor.<br /><br /> `date`: Uma expressão que retorna `DateTime,` ou `DateTimeOffset,` ou valor de `Time` com precisão = [] 0-7, ou uma cadeia de caracteres em um formato de data.<br /><br /> **Valor retornado**<br /><br /> O datepart especificado de data especificada, como `Int32`.<br /><br /> **Exemplo**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(``date``)`|Rreturns o dia de data especificada como um número inteiro.<br /><br /> **Argumentos**<br /><br /> `date`: Uma expressão de tipo `DateTime` ou `DateTimeOffset` com precisão = 0-7.<br /><br /> **Valor retornado**<br /><br /> O dia de data especificada como `Int32`.<br /><br /> **Exemplo**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|Gerencia a data e hora no formato interno do SQL Server para valores de datetime.<br /><br /> **Valor retornado**<br /><br /> A data e hora atuais do sistema como `DateTime` com uma precisão de 3.<br /><br /> **Exemplo**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|Gerencia o valor datetime no formato UTC (Tempo Universal Coordenado ou o horário de Greenwich) atuais.<br /><br /> **Valor retornado**<br /><br /> O valor de `DateTime` com uma precisão de 3 no formato UTC.<br /><br /> **Exemplo**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(``date``)`|Retorna o mês de data especificada como um número inteiro.<br /><br /> **Argumentos**<br /><br /> `date`: Uma expressão de tipo `DateTime` ou `DateTimeOffset` com precisão = 0-7.<br /><br /> **Valor retornado**<br /><br /> O mês de data especificada como `Int32`.<br /><br /> **Exemplo**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(``date``)`|Retorna o ano de data especificada como um número inteiro.<br /><br /> **Argumentos**<br /><br /> `date`: Uma expressão de tipo `DateTime` ou `DateTimeOffset` com precisão = 0-7.<br /><br /> **Valor retornado**<br /><br /> O ano de data especificada como `Int32`.<br /><br /> **Exemplo**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|Retorna um valor de `DateTime` com uma precisão de 7.<br /><br /> **Valor retornado**<br /><br /> Um valor de `DateTime` com uma precisão de 7.<br /><br /> **Exemplo**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|Gerencia o valor datetime no formato UTC (Tempo Universal Coordenado ou o horário de Greenwich) atuais.<br /><br /> **Valor retornado**<br /><br /> O valor de `DateTime` com precisão = 7 no formato UTC.<br /><br /> **Exemplo**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|Retorna `DateTimeOffset` com uma precisão de 7.<br /><br /> **Valor retornado**<br /><br /> Um valor de `DateTimeOffset` com precisão de 7 no formato UTC.<br /><br /> **Exemplo**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 Para obter mais informações sobre funções de data e hora que suporta SqlClient, consulte a documentação para a versão do SQL Server que você especificou no manifesto do provedor SqlClient:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Funções de data e hora (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115908)|[Funções de data e hora (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115909)|[Funções de data e hora (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=98360)|  
  
## <a name="see-also"></a>Consulte também  
 [SqlClient para funções de Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
