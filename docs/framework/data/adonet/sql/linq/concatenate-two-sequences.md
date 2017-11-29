---
title: "Concatenar duas sequências"
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
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e7230e1f53f58f37dacbb1f22fbad1593768e01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="8171b-102">Concatenar duas sequências</span><span class="sxs-lookup"><span data-stu-id="8171b-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="8171b-103">Use o operador de <xref:System.Linq.Queryable.Concat%2A> para concatenar duas sequências.</span><span class="sxs-lookup"><span data-stu-id="8171b-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="8171b-104">O operador de <xref:System.Linq.Queryable.Concat%2A> é definido para os multisets ordenados onde os pedidos do receptor e argumento são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="8171b-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="8171b-105">Ordenação em SQL é a etapa final antes que os resultados são gerados.</span><span class="sxs-lookup"><span data-stu-id="8171b-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="8171b-106">Por esse motivo, o operador de <xref:System.Linq.Queryable.Concat%2A> é implementado usando `UNION ALL` e não preserva a ordem dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="8171b-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="8171b-107">Para certificar-se de ordenação está correta nos resultados, certifique-se pedir explicitamente os resultados.</span><span class="sxs-lookup"><span data-stu-id="8171b-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8171b-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8171b-108">Example</span></span>  
 <span data-ttu-id="8171b-109">Este exemplo usa <xref:System.Linq.Queryable.Concat%2A> para retornar uma sequência de todos os números de `Customer` e de telefone e fax de `Employee` .</span><span class="sxs-lookup"><span data-stu-id="8171b-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="8171b-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8171b-110">Example</span></span>  
 <span data-ttu-id="8171b-111">Este exemplo usa <xref:System.Linq.Queryable.Concat%2A> para retornar uma sequência mapeamentos de qualquer nome de `Customer` e de `Employee` e de número de telefone.</span><span class="sxs-lookup"><span data-stu-id="8171b-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="8171b-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8171b-112">See Also</span></span>  
 [<span data-ttu-id="8171b-113">Exemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="8171b-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="8171b-114">Conversão de operador de consulta padrão</span><span class="sxs-lookup"><span data-stu-id="8171b-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)