---
title: Escrevendo um provedor de dados do Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6cbb6d4c11c06c1771cb32021c6c148564a6034a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="ccc75-102">Escrevendo um provedor de dados do Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ccc75-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="ccc75-103">Esta seção discute como escrever um [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provedor para dar suporte a uma fonte de dados diferente de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc75-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ccc75-104">O [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] inclui um provedor que dá suporte a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc75-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="ccc75-105">Introdução ao modelo de provedor de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ccc75-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="ccc75-106">O [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] é independente de banco de dados e você pode escrever um provedor usando o modelo do provedor do ADO.NET para se conectar a um conjunto de várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="ccc75-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="ccc75-107">O provedor de dados do Entity Framework (compilado usando o modelo do provedor de dados do ADO.NET) executa as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="ccc75-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="ccc75-108">Mapeia tipos primitivos de EDM (Modelo de Dados de Entidade) para os tipos de provedor.</span><span class="sxs-lookup"><span data-stu-id="ccc75-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="ccc75-109">Expõe funções específicas do provedor.</span><span class="sxs-lookup"><span data-stu-id="ccc75-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="ccc75-110">Gera comandos específicos de provedor para um determinado DbQueryCommandTree para dar suporte a consultas do [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc75-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="ccc75-111">Gera comandos de atualização específicos do provedor para um determinado DbModificationCommandTree para dar suporte a atualizações por meio do [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc75-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="ccc75-112">Expõe arquivos de mapeamento para a definição do esquema de armazenamento, para dar suporte à geração de um modelo baseado em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ccc75-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="ccc75-113">Expõe metadados (tabelas e exibições, por exemplo) por meio de um modelo conceitual.</span><span class="sxs-lookup"><span data-stu-id="ccc75-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="ccc75-114">![b42a7a5c &#45; 0ac0 &#45; 4911 &#45; 86be &#45; 0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="ccc75-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="ccc75-115">Amostra</span><span class="sxs-lookup"><span data-stu-id="ccc75-115">Sample</span></span>  
 <span data-ttu-id="ccc75-116">Consulte o [provedor do Entity Framework exemplo](http://go.microsoft.com/fwlink/?LinkId=180616) para obter um exemplo de um [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provedor que dá suporte a uma fonte de dados diferente de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc75-116">See the [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccc75-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ccc75-117">In This Section</span></span>  
 [<span data-ttu-id="ccc75-118">Geração SQL</span><span class="sxs-lookup"><span data-stu-id="ccc75-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="ccc75-119">Geração de alteração SQL</span><span class="sxs-lookup"><span data-stu-id="ccc75-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="ccc75-120">Especificação do manifesto do provedor</span><span class="sxs-lookup"><span data-stu-id="ccc75-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="ccc75-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ccc75-121">See Also</span></span>  
 [<span data-ttu-id="ccc75-122">Trabalhando com provedores de dados</span><span class="sxs-lookup"><span data-stu-id="ccc75-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)