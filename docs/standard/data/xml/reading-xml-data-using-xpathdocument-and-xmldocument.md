---
title: Lendo dados XML usando XPathDocument e XmlDocument
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
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 607d9d3616db0d0bd431fa2ca0b6aee03a85f896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a><span data-ttu-id="6cd4e-102">Lendo dados XML usando XPathDocument e XmlDocument</span><span class="sxs-lookup"><span data-stu-id="6cd4e-102">Reading XML Data using XPathDocument and XmlDocument</span></span>
<span data-ttu-id="6cd4e-103">Há duas maneiras para ler um documento XML no namespace <xref:System.Xml.XPath?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-103">There are two ways to read an XML document in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="6cd4e-104">Uma é ler um documento XML usando a classe <xref:System.Xml.XPath.XPathDocument> somente leitura e a outra é ler um documento XML usando a classe <xref:System.Xml.XmlDocument> editável no namespace <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-104">One is to read an XML document using the read-only <xref:System.Xml.XPath.XPathDocument> class and the other is to read an XML document using the editable <xref:System.Xml.XmlDocument> class in the <xref:System.Xml?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a><span data-ttu-id="6cd4e-105">Lendo documentos XML usando a classe XPathDocument</span><span class="sxs-lookup"><span data-stu-id="6cd4e-105">Reading XML Documents using the XPathDocument Class</span></span>  
 <span data-ttu-id="6cd4e-106">A classe <xref:System.Xml.XPath.XPathDocument> fornece uma representação rápida, somente leitura e na memória de um documento XML usando o modelo de dados XPath.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-106">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="6cd4e-107">As instâncias da classe <xref:System.Xml.XPath.XPathDocument> são criadas usando um de seus seis construtores.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-107">Instances of the <xref:System.Xml.XPath.XPathDocument> class are created using one of its six constructors.</span></span> <span data-ttu-id="6cd4e-108">Esses construtores permitem que você leia um documento XML usando um objeto <xref:System.IO.Stream>, <xref:System.IO.TextReader> ou <xref:System.Xml.XmlReader>, bem como o caminho `string` para um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-108">These constructors allow you to read an XML document using a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="6cd4e-109">O exemplo a seguir ilustra o uso do construtor <xref:System.Xml.XPath.XPathDocument> da classe `string` para ler um documento XML.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-109">The following example illustrates using the <xref:System.Xml.XPath.XPathDocument> class's `string` constructor to read an XML document.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a><span data-ttu-id="6cd4e-110">Lendo documentos XML usando a classe XmlDocument</span><span class="sxs-lookup"><span data-stu-id="6cd4e-110">Reading XML Documents using the XmlDocument Class</span></span>  
 <span data-ttu-id="6cd4e-111">A classe <xref:System.Xml.XmlDocument> é uma representação editável e na memória de um documento XML que implementa o núcleo de nível 1 do DOM (Modelo de Objeto de Documento) do W3C e o nível 2 do DOM principal.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-111">The <xref:System.Xml.XmlDocument> class is an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="6cd4e-112">As instâncias da classe <xref:System.Xml.XmlDocument> são criadas usando um de seus três construtores.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-112">Instances of the <xref:System.Xml.XmlDocument> class are created using one of its three constructors.</span></span> <span data-ttu-id="6cd4e-113">Você pode criar um objeto <xref:System.Xml.XmlDocument> novo e vazio chamando o construtor de classe <xref:System.Xml.XmlDocument> sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-113">You can create a new, empty <xref:System.Xml.XmlDocument> object by calling the <xref:System.Xml.XmlDocument> class constructor with no parameters.</span></span> <span data-ttu-id="6cd4e-114">Após chamar o construtor, use o método <xref:System.Xml.XmlDocument.Load%2A> para carregar dados XML no novo objeto <xref:System.Xml.XmlDocument> de um <xref:System.IO.Stream>, <xref:System.IO.TextReader> ou objeto <xref:System.Xml.XmlReader>, assim como o caminho `string` para um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-114">After calling the constructor, use the <xref:System.Xml.XmlDocument.Load%2A> method to load XML data into the new <xref:System.Xml.XmlDocument> object from a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="6cd4e-115">O exemplo a seguir ilustra o uso do construtor da classe <xref:System.Xml.XmlDocument> sem parâmetros e o método <xref:System.Xml.XmlDocument.Load%2A> para ler um documento XML.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-115">The following example illustrates using the <xref:System.Xml.XmlDocument> class constructor with no parameters and the <xref:System.Xml.XmlDocument.Load%2A> method to read an XML document.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a><span data-ttu-id="6cd4e-116">Determinando a codificação de um documento XML</span><span class="sxs-lookup"><span data-stu-id="6cd4e-116">Determining the Encoding of an XML Document</span></span>  
 <span data-ttu-id="6cd4e-117">Um objeto <xref:System.Xml.XmlReader> pode ser usado para ler um documento XML e criar objetos <xref:System.Xml.XPath.XPathDocument> e <xref:System.Xml.XmlDocument> conforme mostrado nas seções anteriores.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-117">An <xref:System.Xml.XmlReader> object can be used to read an XML document and to create <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> objects as shown in the previous sections.</span></span> <span data-ttu-id="6cd4e-118">No entanto, um objeto <xref:System.Xml.XmlReader> pode ler os dados que não são codificados e, como um resultado, não fornece nenhuma informação de codificação.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-118">However, an <xref:System.Xml.XmlReader> object may read data that is not encoded and as a result does not provide any encoding information.</span></span>  
  
 <span data-ttu-id="6cd4e-119">A classe <xref:System.Xml.XmlTextReader> herda da classe <xref:System.Xml.XmlReader>, fornece informações de codificação usando a propriedade <xref:System.Xml.XmlTextReader.Encoding%2A> e pode ser usada para criar um objeto <xref:System.Xml.XPath.XPathDocument> ou objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-119">The <xref:System.Xml.XmlTextReader> class inherits from the <xref:System.Xml.XmlReader> class, provides encoding information using its <xref:System.Xml.XmlTextReader.Encoding%2A> property, and can be used to create an <xref:System.Xml.XPath.XPathDocument> object or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="6cd4e-120">Para obter mais informações sobre as informações de codificação fornecidas pela classe <xref:System.Xml.XmlTextReader>, consulte a propriedade <xref:System.Xml.XmlTextReader.Encoding%2A> na documentação de referência da classe <xref:System.Xml.XmlTextReader>.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-120">For more information about the encoding information provided by the <xref:System.Xml.XmlTextReader> class, see the <xref:System.Xml.XmlTextReader.Encoding%2A> property in the <xref:System.Xml.XmlTextReader> class reference documentation.</span></span>  
  
## <a name="creating-xpathnavigator-objects"></a><span data-ttu-id="6cd4e-121">Criando objetos XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="6cd4e-121">Creating XPathNavigator Objects</span></span>  
 <span data-ttu-id="6cd4e-122">Depois que você tiver lido um documento XML em um objeto <xref:System.Xml.XPath.XPathDocument> ou <xref:System.Xml.XmlDocument>, poderá criar um objeto <xref:System.Xml.XPath.XPathNavigator> para selecionar, avaliar, navegar e, em alguns casos, editar os dados de XML subjacentes.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-122">After you have read an XML document into either an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, you can create an <xref:System.Xml.XPath.XPathNavigator> object to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="6cd4e-123">As classes <xref:System.Xml.XPath.XPathDocument> e <xref:System.Xml.XmlDocument>, além da classe <xref:System.Xml.XmlNode>, implementam a interface <xref:System.Xml.XPath.IXPathNavigable> do namespace <xref:System.Xml.XPath?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-123">Both the <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> classes, in addition to the <xref:System.Xml.XmlNode> class, implement the <xref:System.Xml.XPath.IXPathNavigable> interface of the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="6cd4e-124">Como resultado, todas as três classes fornecem um método <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> que retorna um objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-124">As a result, all three classes provide a <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> method that returns an <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a><span data-ttu-id="6cd4e-125">Editando documentos XML usando a classe XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="6cd4e-125">Editing XML Documents using the XPathNavigator Class</span></span>  
 <span data-ttu-id="6cd4e-126">Além de selecionar, avaliar e navegar dados XML, a classe <xref:System.Xml.XPath.XPathNavigator> pode ser usada para editar um documento XML em alguns casos, com base no objeto que o criou.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-126">In addition to selecting, evaluating, and navigating XML data, the <xref:System.Xml.XPath.XPathNavigator> class can be used to edit an XML document in some cases, based on the object that created it.</span></span>  
  
 <span data-ttu-id="6cd4e-127">A classe <xref:System.Xml.XPath.XPathDocument> será somente leitura quando a classe <xref:System.Xml.XmlDocument> for editável e, como resultado, os objetos <xref:System.Xml.XPath.XPathNavigator> criados de um objeto <xref:System.Xml.XPath.XPathDocument> não podem ser usados para editar um documento XML, enquanto que os criados de um objeto <xref:System.Xml.XmlDocument> podem.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-127">The <xref:System.Xml.XPath.XPathDocument> class is read-only while the <xref:System.Xml.XmlDocument> class is editable and as a result, <xref:System.Xml.XPath.XPathNavigator> objects created from an <xref:System.Xml.XPath.XPathDocument> object cannot be used to edit an XML document while those created from an <xref:System.Xml.XmlDocument> object can.</span></span> <span data-ttu-id="6cd4e-128">A classe <xref:System.Xml.XPath.XPathDocument> deve ser usada para ler um documento XML somente.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-128">The <xref:System.Xml.XPath.XPathDocument> class should be used to read an XML document only.</span></span> <span data-ttu-id="6cd4e-129">Em casos onde você precisa editar um documento XML ou precisa de acesso à funcionalidade adicional fornecida pela classe <xref:System.Xml.XmlDocument>, como tratamento de evento, a classe <xref:System.Xml.XmlDocument> deverá ser usada.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-129">In cases where you need to edit an XML document, or require access to the additional functionality provided by the <xref:System.Xml.XmlDocument> class, like event handling, the <xref:System.Xml.XmlDocument> class should be used.</span></span>  
  
 <span data-ttu-id="6cd4e-130">A propriedade <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> da classe <xref:System.Xml.XPath.XPathNavigator> especifica se um objeto <xref:System.Xml.XPath.XPathNavigator> pode editar dados XML.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-130">The <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class specifies if an <xref:System.Xml.XPath.XPathNavigator> object may edit XML data.</span></span>  
  
 <span data-ttu-id="6cd4e-131">A tabela a seguir descreve o valor da propriedade <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> para cada classe.</span><span class="sxs-lookup"><span data-stu-id="6cd4e-131">The following table describes the value of the <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property for each class.</span></span>  
  
|<span data-ttu-id="6cd4e-132"><xref:System.Xml.XPath.IXPathNavigable>Implementação</span><span class="sxs-lookup"><span data-stu-id="6cd4e-132"><xref:System.Xml.XPath.IXPathNavigable> Implementation</span></span>|<span data-ttu-id="6cd4e-133">Valor <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A></span><span class="sxs-lookup"><span data-stu-id="6cd4e-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Value</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a><span data-ttu-id="6cd4e-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6cd4e-134">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="6cd4e-135">Processar dados XML usando o modelo de dados XPath</span><span class="sxs-lookup"><span data-stu-id="6cd4e-135">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="6cd4e-136">Acessando dados XML usando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="6cd4e-136">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6cd4e-137">Editando dados XML usando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="6cd4e-137">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6cd4e-138">Validação de esquema usando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="6cd4e-138">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)