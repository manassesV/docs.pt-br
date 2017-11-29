---
title: "Trabalhando com a linguagem de definição de dados"
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
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d65fb17796339f38be59b64e550d7ec77336083d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="7021b-102">Trabalhando com a linguagem de definição de dados</span><span class="sxs-lookup"><span data-stu-id="7021b-102">Working with Data Definition Language</span></span>
<span data-ttu-id="7021b-103">Começando com o [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] versão 4, o [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] oferece suporte a linguagem de definição de dados (DDL).</span><span class="sxs-lookup"><span data-stu-id="7021b-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="7021b-104">Isso permite que você crie ou exclua uma instância do banco de dados com base na cadeia de conexão e nos metadados do modelo de armazenamento (SSDL).</span><span class="sxs-lookup"><span data-stu-id="7021b-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="7021b-105">Os métodos a seguir no <xref:System.Data.Objects.ObjectContext> usam a cadeia de conexão e o conteúdo SSDL para criar ou excluir o banco de dados, verificar se o banco de dados existe e exibir o script DDL gerado:</span><span class="sxs-lookup"><span data-stu-id="7021b-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="7021b-106">A execução de comandos DDL pressupõe permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="7021b-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="7021b-107">Os métodos listados anteriormente delegam a maioria do trabalho para o provedor de dados ADO.NET subjacente.</span><span class="sxs-lookup"><span data-stu-id="7021b-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="7021b-108">É responsabilidade do provedor garantir que a convenção de nomenclatura usada para gerar objetos de banco de dados seja consistente com as convenções usadas nas consultas e atualizações.</span><span class="sxs-lookup"><span data-stu-id="7021b-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="7021b-109">O exemplo a seguir mostra como gerar o banco de dados com base no modelo existente.</span><span class="sxs-lookup"><span data-stu-id="7021b-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="7021b-110">Ele também adiciona um novo objeto de entidade ao contexto de objeto e os salva no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7021b-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7021b-111">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="7021b-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="7021b-112">Para definir um banco de dados com base no modelo existente</span><span class="sxs-lookup"><span data-stu-id="7021b-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="7021b-113">Crie um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="7021b-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="7021b-114">Adicione um modelo existente ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7021b-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="7021b-115">Adicionar um modelo vazio chamado `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="7021b-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="7021b-116">Para criar um modelo vazio, consulte o [como: criar um novo arquivo de EDMX](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) tópico.</span><span class="sxs-lookup"><span data-stu-id="7021b-116">To create an empty model, see the [How to: Create a New .edmx File](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="7021b-117">O arquivo SchoolModel.edmx é adicionado ao projeto.</span><span class="sxs-lookup"><span data-stu-id="7021b-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="7021b-118">Copiar o conceitual, armazenamento e mapeamento de conteúdo para o modelo de escola do [modelo School](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) tópico.</span><span class="sxs-lookup"><span data-stu-id="7021b-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="7021b-119">Abra o arquivo SchoolModel.edmx e cole o conteúdo nas marcas `edmx:Runtime`.</span><span class="sxs-lookup"><span data-stu-id="7021b-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="7021b-120">Adicione o seguinte código à função principal.</span><span class="sxs-lookup"><span data-stu-id="7021b-120">Add the following code to your main function.</span></span> <span data-ttu-id="7021b-121">O código inicializa a cadeia de conexão ao servidor de banco de dados, exibe o script DDL, cria o banco de dados, adiciona uma nova entidade ao contexto e salva as alterações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7021b-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]