---
title: SqlDependency em um aplicativo ASP.NET
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
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c63118db5333158feb596a534e01f922473cd7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="sqldependency-in-an-aspnet-application"></a>SqlDependency em um aplicativo ASP.NET
O exemplo nesta seção mostra como usar <xref:System.Data.SqlClient.SqlDependency> indiretamente, aproveitando o ASP.NET <xref:System.Web.Caching.SqlCacheDependency> objeto. O <xref:System.Web.Caching.SqlCacheDependency> objeto usa um <xref:System.Data.SqlClient.SqlDependency> para ouvir as notificações e atualizar corretamente o cache.  
  
> [!NOTE]
>  O exemplo de código pressupõe que você habilitou as notificações de consulta executando os scripts [habilitar notificações de consulta](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>Sobre o aplicativo de exemplo  
 O aplicativo de exemplo usa uma única página da Web do ASP.NET para exibir informações de produto o **AdventureWorks** banco de dados do SQL Server em um <xref:System.Web.UI.WebControls.GridView> controle. Quando a página for carregada, o código grava a hora atual para um <xref:System.Web.UI.WebControls.Label> controle. Em seguida, define um <xref:System.Web.Caching.SqlCacheDependency> de objeto e define as propriedades no <xref:System.Web.Caching.Cache> objeto para armazenar os dados do cache para até três minutos. O código, em seguida, conecta-se ao banco de dados e recupera os dados. Quando a página for carregada e o aplicativo está executando o ASP.NET irá recuperar dados do cache, você pode verificar observando que o tempo na página não é alterado. Se os dados que estão sendo monitorados forem alterados, ASP.NET invalida o cache e preencher novamente o `GridView` controle com dados atualizados, atualizando o horário exibido no `Label` controle.  
  
## <a name="creating-the-sample-application"></a>Criando o aplicativo de exemplo  
 Siga estas etapas para criar e executar o aplicativo de exemplo:  
  
1.  Crie um novo site da Web do ASP.NET.  
  
2.  Adicionar um <xref:System.Web.UI.WebControls.Label> e um <xref:System.Web.UI.WebControls.GridView> controle para a página Default.aspx.  
  
3.  Abra o módulo de classe da página e adicione as seguintes diretivas:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  Adicione o seguinte código na página de `Page_Load` eventos:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  Adicione dois métodos auxiliares, `GetConnectionString` e `GetSQL`. A cadeia de caracteres de conexão definida usa segurança integrada. Você precisará verificar se a conta que você está usando tem as permissões necessárias e se o banco de dados de exemplo, **AdventureWorks**, tem notificações habilitadas. Para obter mais informações, consulte [especiais considerações ao usar notificações de consulta](http://msdn.microsoft.com/en-us/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Testando o aplicativo  
 O aplicativo armazena em cache os dados exibidos no formulário da Web e atualiza cada três minutos se não houver nenhuma atividade. Se ocorrer uma alteração no banco de dados, o cache é atualizado imediatamente. Execute o aplicativo do Visual Studio, que carrega a página no navegador. O tempo de atualização do cache exibido indica quando o cache foi atualizada pela última vez. Aguarde três minutos e, em seguida, atualize a página, fazendo com que um evento de postback ocorra. Observe que a hora exibida na página foi alterada. Se você atualizar a página em menos de três minutos, o horário exibido na página permanece o mesmo.  
  
 Agora, atualize os dados no banco de dados, usando um comando Transact-SQL UPDATE e atualize a página. Agora, a hora exibida indica que o cache foi atualizado com novos dados do banco de dados. Observe que embora o cache é atualizado, o horário exibido na página não se altera até que ocorra um evento de postback.  
  
## <a name="see-also"></a>Consulte também  
 [Notificações de consulta no SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)
