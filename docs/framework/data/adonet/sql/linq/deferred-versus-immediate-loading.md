---
title: Adiado contra a carga immediate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 992d9a018f81bbd3f0c9204168f513024769e079
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="deferred-versus-immediate-loading"></a>Adiado contra a carga immediate
Quando você consulta para um objeto, você só retorna o objeto que você solicitou. O *relacionados* objetos não são buscados automaticamente ao mesmo tempo. (Para obter mais informações, consulte [consulta entre relações](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) Você não pode ver o fato de que os objetos relacionados não são carregados já, porque uma tentativa de acessar gerencia uma solicitação que recupere-os.  
  
 Por exemplo, você pode desejar consultar um determinado conjunto de pedidos e depois envie apenas ocasionalmente um email de notificação para clientes específicos. Você não precisará necessariamente inicialmente de recuperar todos os dados do cliente com cada pedido. Você pode usar o carregamento adiada para adiar a recuperação de informações extras até que você tenha que absolutamente. Considere o exemplo a seguir:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 O oposto também pode ser true. Você pode ter um aplicativo que tenha que exibir o cliente e ordenação dados ao mesmo tempo. Você conhece-o necessidade dois conjuntos de dados. Você sabe suas informações de ordem das necessidades do aplicativo para cada cliente para que você obter os resultados. Você não deve enviar para consultas individuais de pedidos para cada cliente. O que você deseja realmente é recuperar os dados de pedidos juntamente com os clientes.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 Você também pode associar à clientes e pedidos em uma consulta formando entre o produto e recuperar todos os bits de dados relacionados como uma grande projeção. Mas esses resultados não são entidades. (Para obter mais informações, consulte [o LINQ no modelo de objeto SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)). As entidades são objetos que possuem a identidade e que você pode alterar, enquanto esses resultados seriam as projeções que não podem ser modificadas e persistente. Ainda pior, você poderia ser recuperando lotes de dados redundantes como as repetições de cada cliente para cada ordem em aplainado se associam a saída.  
  
 O que você precisa realmente é uma maneira para recuperar ao mesmo tempo um conjunto de objetos relacionados. O conjunto é uma seção delineado de um gráfico de modo que você nunca está recuperando mais ou menos que foi necessário para seu uso pretendido. Para essa finalidade, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornece <xref:System.Data.Linq.DataLoadOptions> para carregamento imediato de uma região do seu modelo de objeto. Os métodos incluem:  
  
-   O método de <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> , imediatamente para carregar os dados relacionados ao destino principal.  
  
-   O método de <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> , para filtrar os objetos recuperados para um relacionamento específico.  
  
## <a name="see-also"></a>Consulte também  
 [Conceitos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
