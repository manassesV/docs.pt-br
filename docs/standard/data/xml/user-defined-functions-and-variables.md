---
title: "Funções definidas pelo usuário e variáveis"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e1327ac2a3df7a84c157e4bf60d2ad63d69b1677
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions-and-variables"></a>Funções definidas pelo usuário e variáveis
A classe de <xref:System.Xml.XPath.XPathNavigator> fornece um conjunto de métodos que são usados para interagir com os dados de <xref:System.Xml.XPath.XPathDocument> . Você pode complementar as funções padrão XPath implementando funções e variáveis de extensão para o uso de expressões de consulta XPath. O método de <xref:System.Xml.XPath.XPathExpression.SetContext%2A> pode aceitar um contexto definido pelo usuário derivado de <xref:System.Xml.Xsl.XsltContext>. As funções definidas pelo usuário são resolvidas pelo contexto personalizado.  
  
 Funções e variáveis de extensão podem ser úteis em prevenção de ataques de injeção XML. Na entrada do usuário desses cenários é atribuído a variáveis personalizados e processado por funções de extensão, não como entrada raw concatenada com instruções de processamento. Funções e variáveis de extensão contêm a entrada do usuário para que funciona somente em dados XML como destinada pelo designer.  
  
 Para usar extensões você implementa uma classe personalizada de <xref:System.Xml.Xsl.XsltContext> junto com as interfaces <xref:System.Xml.Xsl.IXsltContextFunction> e <xref:System.Xml.Xsl.IXsltContextVariable> que suportam funções e variáveis de extensão. <xref:System.Xml.XPath.XPathExpression> adiciona a entrada do usuário com seu <xref:System.Xml.Xsl.XsltArgumentList> a <xref:System.Xml.Xsl.XsltContext>personalizado.  
  
 <xref:System.Xml.XPath.XPathExpression> representa uma consulta compilado que <xref:System.Xml.XPath.XPathNavigator> usa para localizar e processa os nós identificados pela expressão.  
  
 A implementação da seguir mostra de uma classe personalizada de contexto derivada de <xref:System.Xml.Xsl.XsltContext>. Comentários no código a seguir descrevem membros de classe e seu uso em funções personalizados. As implementações de função e de variável e um aplicativo de exemplo que usa essas implementações seguem este segmento de código.  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 O código a seguir implementa <xref:System.Xml.Xsl.IXsltContextFunction>. A classe que implementa resoluções de <xref:System.Xml.Xsl.IXsltContextFunction> e executa funções definidas pelo usuário. Este exemplo usa a função identificada pela declaração: `private int CountChar(string title, char charTocount)`.  
  
 Comentários de código a seguir descrevem membros de classe.  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 O código a seguir implementa <xref:System.Xml.Xsl.IXsltContextVariable>. Essa classe resolve referências a variáveis definidas pelo usuário em expressões de consulta XPath em tempo de execução. Uma instância dessa classe é criada e retornada pelo método substituído de <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> de classe personalizada de <xref:System.Xml.Xsl.XsltContext> .  
  
 Comentários de código a seguir descrevem os membros de classe.  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 Com definições de classe anteriores no escopo, o código a seguir usa a função personalizado para contar caracteres em elementos de documento de `Tasks.xml` . Comentários no código descrevem o código que cria a função personalizado e para executar contra o documento de `Tasks.xml` .  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 Este exemplo usa os seguintes dados XML.  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
