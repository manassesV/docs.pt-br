---
title: "Implementando o padrão de controle TableItem de interface de usuário "
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5861ab24627f9b78cd20f97fcdb1b1b3d681991a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="fb030-102">Implementando o padrão de controle TableItem de interface de usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="fb030-103">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="fb030-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fb030-104">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="fb030-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="fb030-105">Este tópico apresenta diretrizes e convenções para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluindo informações sobre propriedades e eventos.</span><span class="sxs-lookup"><span data-stu-id="fb030-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="fb030-106">Links para referências adicionais são listadas no final da visão geral.</span><span class="sxs-lookup"><span data-stu-id="fb030-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="fb030-107">O <xref:System.Windows.Automation.TableItemPattern> padrão de controle é usado para oferecer suporte aos controles filho de contêiners que implementam <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="fb030-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="fb030-108">Acesso à funcionalidade das células individuais é fornecido pela implementação simultânea necessária de <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="fb030-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="fb030-109">Esse padrão de controle é análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider> com a diferença que qualquer controle implementando <xref:System.Windows.Automation.Provider.ITableItemProvider> deve programaticamente expor a relação entre a célula individual e suas informações de linha e coluna.</span><span class="sxs-lookup"><span data-stu-id="fb030-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="fb030-110">Para obter exemplos de controles que implementam este padrão de controle, consulte [mapeamento de padrão de controle para clientes de automação de interface do usuário](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="fb030-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="fb030-111">Convenções e diretrizes de implementação</span><span class="sxs-lookup"><span data-stu-id="fb030-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="fb030-112">Para a funcionalidade do item de grade relacionados, consulte [Implementando o padrão controle de GridItem de automação de interface do usuário](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fb030-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="fb030-113">Membros necessários para ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="fb030-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="fb030-114">Membro necessário</span><span class="sxs-lookup"><span data-stu-id="fb030-114">Required member</span></span>|<span data-ttu-id="fb030-115">Tipo de membro</span><span class="sxs-lookup"><span data-stu-id="fb030-115">Member type</span></span>|<span data-ttu-id="fb030-116">Observações</span><span class="sxs-lookup"><span data-stu-id="fb030-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="fb030-117">Método</span><span class="sxs-lookup"><span data-stu-id="fb030-117">Method</span></span>|<span data-ttu-id="fb030-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fb030-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="fb030-119">Método</span><span class="sxs-lookup"><span data-stu-id="fb030-119">Method</span></span>|<span data-ttu-id="fb030-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fb030-120">None</span></span>|  
  
 <span data-ttu-id="fb030-121">Esse padrão de controle não tem propriedades associadas ou eventos.</span><span class="sxs-lookup"><span data-stu-id="fb030-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="fb030-122">Exceções</span><span class="sxs-lookup"><span data-stu-id="fb030-122">Exceptions</span></span>  
 <span data-ttu-id="fb030-123">Esse padrão de controle não tem exceção associada.</span><span class="sxs-lookup"><span data-stu-id="fb030-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb030-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fb030-124">See Also</span></span>  
 [<span data-ttu-id="fb030-125">Visão geral de padrões de controle de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="fb030-126">Suporte a padrões de controle em um provedor de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="fb030-127">Padrões de controle de automação de interface do usuário para clientes</span><span class="sxs-lookup"><span data-stu-id="fb030-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="fb030-128">Implementando o padrão de controle de tabela de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="fb030-129">Implementando o padrão de controle GridItem de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="fb030-130">Visão geral de árvore de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="fb030-131">Usar o cache em automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="fb030-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)