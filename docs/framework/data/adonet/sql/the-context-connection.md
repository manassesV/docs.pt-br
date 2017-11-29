---
title: "A conexão de contexto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a41c9a526895057a6c7e785abbaaa4e4cd2c490f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="the-context-connection"></a><span data-ttu-id="780ca-102">A conexão de contexto</span><span class="sxs-lookup"><span data-stu-id="780ca-102">The Context Connection</span></span>
<span data-ttu-id="780ca-103">O problema de acesso a dados internos é um cenário bastante comum.</span><span class="sxs-lookup"><span data-stu-id="780ca-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="780ca-104">Ou seja, você deseja acessar o mesmo servidor no qual o procedimento armazenado ou função CLR está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="780ca-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="780ca-105">Uma opção é criar uma conexão usando <xref:System.Data.SqlClient.SqlConnection>, especificar uma cadeia de conexão que aponta para o servidor local, e abrir a conexão.</span><span class="sxs-lookup"><span data-stu-id="780ca-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="780ca-106">Isso exige a especificação de credenciais para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="780ca-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="780ca-107">A conexão está em uma sessão do banco de dados diferente do procedimento armazenado ou da função, pode ter opções diferentes de `SET`, pode estar em uma transação separada, não ver suas tabelas temporárias e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="780ca-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="780ca-108">Se seu código gerenciado do procedimento armazenado ou função está sendo executado no processo do SQL Server, é porque alguém se conectou a esse servidor e executou uma instrução SQL para chamá-lo.</span><span class="sxs-lookup"><span data-stu-id="780ca-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="780ca-109">Você deseja provavelmente que o procedimento armazenado ou a função seja executada no contexto dessa conexão, junto com sua transação, opções `SET` e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="780ca-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="780ca-110">Isso é chamado de conexão de contexto.</span><span class="sxs-lookup"><span data-stu-id="780ca-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="780ca-111">A conexão de contexto permite executar instruções Transact-SQL no mesmo contexto em que seu código foi chamado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="780ca-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="780ca-112">Para obter informações detalhadas, consulte a versão dos Manuais Online do SQL Server da versão do SQL Server que você está usando.</span><span class="sxs-lookup"><span data-stu-id="780ca-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="780ca-113">**SQL Server Books Online** (Guias online do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="780ca-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="780ca-114">A Conexão de contexto</span><span class="sxs-lookup"><span data-stu-id="780ca-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="780ca-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="780ca-115">See Also</span></span>  
 [<span data-ttu-id="780ca-116">Criando objetos do SQL Server 2005 em código gerenciado</span><span class="sxs-lookup"><span data-stu-id="780ca-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 <span data-ttu-id="780ca-117">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="780ca-117">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>