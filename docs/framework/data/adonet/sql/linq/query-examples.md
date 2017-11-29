---
title: Exemplos de consulta
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e7d7a0a1f641603887675ed0c1faebd5c06b273
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="query-examples"></a><span data-ttu-id="aef5e-102">Exemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="aef5e-102">Query Examples</span></span>
<span data-ttu-id="aef5e-103">Esta seção fornece exemplos do [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] e do C# de consultas típicas do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aef5e-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="aef5e-104">Os desenvolvedores que usam [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] podem encontrar muito mais exemplos em uma solução de exemplo disponível na seção de exemplos.</span><span class="sxs-lookup"><span data-stu-id="aef5e-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="aef5e-105">Para obter mais informações, consulte [exemplos](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span><span class="sxs-lookup"><span data-stu-id="aef5e-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aef5e-106">*banco de dados* geralmente é usado em exemplos de código [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentação.</span><span class="sxs-lookup"><span data-stu-id="aef5e-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="aef5e-107">*banco de dados* deve para ser uma instância de um *Northwind* classe que herda de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aef5e-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="aef5e-108">In This Section</span></span>  
 [<span data-ttu-id="aef5e-109">Consultas de agregação</span><span class="sxs-lookup"><span data-stu-id="aef5e-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="aef5e-110">Descreve como usar o <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="aef5e-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="aef5e-111">Retornar o primeiro elemento em uma sequência</span><span class="sxs-lookup"><span data-stu-id="aef5e-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="aef5e-112">Fornece exemplos de como usar <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-113">Elementos Return ou Skip em uma sequência</span><span class="sxs-lookup"><span data-stu-id="aef5e-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="aef5e-114">Fornece exemplos de como usar <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-115">Elementos de classificação em uma sequência</span><span class="sxs-lookup"><span data-stu-id="aef5e-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="aef5e-116">Fornece exemplos de como usar <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-117">Elementos de grupo em uma sequência</span><span class="sxs-lookup"><span data-stu-id="aef5e-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="aef5e-118">Fornece exemplos de como usar <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-119">Elimine elementos duplicados de uma sequência</span><span class="sxs-lookup"><span data-stu-id="aef5e-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="aef5e-120">Fornece exemplos de como usar <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-121">Determinar se algum ou todos os elementos em uma sequência satisfazem uma condição</span><span class="sxs-lookup"><span data-stu-id="aef5e-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="aef5e-122">Fornece exemplos de como usar <xref:System.Linq.Enumerable.All%2A> e <xref:System.Linq.Enumerable.Any%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-123">Concatenar duas sequências</span><span class="sxs-lookup"><span data-stu-id="aef5e-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="aef5e-124">Fornece exemplos de como usar <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-125">Retorna a diferença entre duas sequências ajustada</span><span class="sxs-lookup"><span data-stu-id="aef5e-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="aef5e-126">Fornece exemplos de como usar <xref:System.Linq.Enumerable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-127">Retornar a interseção de duas sequências</span><span class="sxs-lookup"><span data-stu-id="aef5e-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="aef5e-128">Fornece exemplos de como usar <xref:System.Linq.Enumerable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-129">Retorna a união de duas sequências</span><span class="sxs-lookup"><span data-stu-id="aef5e-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="aef5e-130">Fornece exemplos de como usar <xref:System.Linq.Enumerable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-131">Converter uma sequência em uma matriz</span><span class="sxs-lookup"><span data-stu-id="aef5e-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="aef5e-132">Fornece exemplos de como usar <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-133">Converter uma sequência em uma lista genérica</span><span class="sxs-lookup"><span data-stu-id="aef5e-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="aef5e-134">Fornece exemplos de como usar <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-135">Converter um tipo em um IEnumerable genérico</span><span class="sxs-lookup"><span data-stu-id="aef5e-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="aef5e-136">Fornece exemplos de como usar <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="aef5e-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="aef5e-137">Formular junções e consultas entre produtos</span><span class="sxs-lookup"><span data-stu-id="aef5e-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="aef5e-138">Fornece exemplos de uso de navegação de chave estrangeira nas cláusulas `from`, `where` e `select`.</span><span class="sxs-lookup"><span data-stu-id="aef5e-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="aef5e-139">Formule projeções</span><span class="sxs-lookup"><span data-stu-id="aef5e-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="aef5e-140">Fornece exemplos de combinação `select` com outros recursos (por exemplo, *tipos anônimos*) para projeções de consulta do formulário.</span><span class="sxs-lookup"><span data-stu-id="aef5e-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aef5e-141">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="aef5e-141">Related Sections</span></span>  
 [<span data-ttu-id="aef5e-142">Visão Geral de Operadores de Consulta Padrão</span><span class="sxs-lookup"><span data-stu-id="aef5e-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="aef5e-143">Explica o conceito de operadores de consulta padrão.</span><span class="sxs-lookup"><span data-stu-id="aef5e-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="aef5e-144">Conceitos de consulta</span><span class="sxs-lookup"><span data-stu-id="aef5e-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="aef5e-145">Explica como o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usa conceitos que se aplicam às consultas.</span><span class="sxs-lookup"><span data-stu-id="aef5e-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="aef5e-146">Guia de Programação</span><span class="sxs-lookup"><span data-stu-id="aef5e-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="aef5e-147">Fornece um portal para tópicos que explicam os conceitos de programação relacionados ao [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aef5e-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>