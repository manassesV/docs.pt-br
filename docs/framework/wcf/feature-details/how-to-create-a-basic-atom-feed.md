---
title: "Como criar um Feed Atom básico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51a42e9b954fba7ccd58d74248fb65dc2b57a76b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-basic-atom-feed"></a>Como criar um Feed Atom básico
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]permite que você crie um serviço que expõe um feed de distribuição. Este tópico discute como criar um serviço de distribuição que expõe um feed de distribuição Atom.  
  
### <a name="to-create-a-basic-syndication-service"></a>Para criar um serviço básico de distribuição  
  
1.  Definir um contrato de serviço usando uma interface marcada com o <xref:System.ServiceModel.Web.WebGetAttribute> atributo. Cada operação que é exposta como um feed de distribuição deve retornar um <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> objeto.  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  Todas as operações de serviço que se aplicam a <xref:System.ServiceModel.Web.WebGetAttribute> são mapeados para solicitações HTTP GET. Para mapear a operação para um método diferente de HTTP, use o <xref:System.ServiceModel.Web.WebInvokeAttribute> em vez disso. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Como: criar um serviço de Web HTTP WCF básico](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).  
  
2.  Implemente o contrato de serviço.  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3.  Criar um <xref:System.ServiceModel.Syndication.SyndicationFeed> do objeto e adicionar um autor, categoria e descrição.  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4.  Criar diversos <xref:System.ServiceModel.Syndication.SyndicationItem> objetos.  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5.  Adicionar o <xref:System.ServiceModel.Syndication.SyndicationItem> objetos para o feed.  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6.  Retorne o feed.  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a>Para hospedar o serviço  
  
1.  Crie um objeto <xref:System.ServiceModel.Web.WebServiceHost>.  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2.  Abrir o host de serviço, carregar o feed do serviço, exibir o feed e aguarde até que o usuário pressione ENTER.  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>Para chamar GetBlog() com um HTTP GET  
  
1.  Abra o Internet Explorer, digite a URL a seguir e pressione ENTER: http://localhost:8000/BlogService/GetBlog  
  
     A URL contém o endereço base do serviço (http://localhost:8000/BlogService), o endereço relativo do ponto de extremidade e chamar a operação de serviço.  
  
### <a name="to-call-getblog-from-code"></a>Para chamar GetBlog() do código  
  
1.  Criar um <xref:System.Xml.XmlReader> com o endereço base e o método de chamada.  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2.  Chamar estático <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> método, passando o <xref:System.Xml.XmlReader> você acabou de criar.  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     Isso chama a operação de serviço e preenche um novo <xref:System.ServiceModel.Syndication.SyndicationFeed> com o formatador retornado da operação de serviço.  
  
3.  Acesse o objeto de feed.  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## <a name="example"></a>Exemplo  
 A seguir está a listagem completa de códigos deste exemplo.  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Ao compilar o código anterior, fazer referência a System.ServiceModel.dll e System.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>
