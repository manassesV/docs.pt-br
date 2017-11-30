---
title: Como adicionar tratamento de classes para um evento roteado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abbbdce0ca12c4d8bdd12f616bf49c3d6f66f441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="15f4d-102">Como adicionar tratamento de classes para um evento roteado</span><span class="sxs-lookup"><span data-stu-id="15f4d-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="15f4d-103">Eventos roteados podem ser manipulados por manipuladores de classe ou de instância em qualquer nó da rota.</span><span class="sxs-lookup"><span data-stu-id="15f4d-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="15f4d-104">Manipuladores de classe são invocados primeiro e podem ser usados pelas implementações de classe para suprimir eventos da manipulação de instâncias ou apresentar outros comportamentos específicos de evento em eventos pertencentes a classes base.</span><span class="sxs-lookup"><span data-stu-id="15f4d-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="15f4d-105">Este exemplo ilustra duas técnicas intimamente relacionadas para implementar manipuladores de classe.</span><span class="sxs-lookup"><span data-stu-id="15f4d-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15f4d-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="15f4d-106">Example</span></span>  
 <span data-ttu-id="15f4d-107">Este exemplo usa uma classe personalizada com base no <xref:System.Windows.Controls.Canvas> painel.</span><span class="sxs-lookup"><span data-stu-id="15f4d-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="15f4d-108">A premissa básica do aplicativo é que a classe personalizada apresenta comportamentos nos seus elementos filho, incluindo a interceptação de cliques com o botão esquerdo do mouse e a marcação deles como manipulados, antes que a classe de elementos filho ou os manipuladores de instância dela sejam invocados.</span><span class="sxs-lookup"><span data-stu-id="15f4d-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="15f4d-109">O <xref:System.Windows.UIElement> classe expõe um método virtual que permite tratamento de classe no <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> evento, simplesmente sobrescrevendo o evento.</span><span class="sxs-lookup"><span data-stu-id="15f4d-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="15f4d-110">Essa será a maneira mais simples de implementar a manipulação de classes se tal método virtual estiver disponível em algum lugar na hierarquia da classe.</span><span class="sxs-lookup"><span data-stu-id="15f4d-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="15f4d-111">O código a seguir mostra o <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementação no "MyEditContainer" que é derivada de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="15f4d-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="15f4d-112">A implementação marca o evento como manipulado nos argumentos e adiciona algum código para dar ao elemento de origem uma alteração visível básica.</span><span class="sxs-lookup"><span data-stu-id="15f4d-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="15f4d-113">Se nenhum virtual estiver disponível em classes base ou para o método particular, tratamento de classe pode ser adicionado diretamente usando um método de utilitário do <xref:System.Windows.EventManager> classe <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="15f4d-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="15f4d-114">Este método só deve ser chamado dentro da inicialização estática de classes que estão adicionando a manipulação de classes.</span><span class="sxs-lookup"><span data-stu-id="15f4d-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="15f4d-115">Este exemplo adiciona outro manipulador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , e nesse caso, a classe registrada é a classe personalizada.</span><span class="sxs-lookup"><span data-stu-id="15f4d-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="15f4d-116">Por outro lado, ao usar os virtuais, a classe registrada é realmente a <xref:System.Windows.UIElement> classe base.</span><span class="sxs-lookup"><span data-stu-id="15f4d-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="15f4d-117">Em casos em que as classes base e subclasses registram tratamento de classe, os manipuladores de subclasse são invocados primeiro.</span><span class="sxs-lookup"><span data-stu-id="15f4d-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="15f4d-118">O comportamento em um aplicativo seria que primeiro esse manipulador mostraria sua caixa de mensagem e, em seguida, a alteração visual no manipulador do método virtual seria mostrada.</span><span class="sxs-lookup"><span data-stu-id="15f4d-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="15f4d-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="15f4d-119">See Also</span></span>  
 <xref:System.Windows.EventManager>  
 [<span data-ttu-id="15f4d-120">Marcando eventos roteados como manipulados e tratamento de classes</span><span class="sxs-lookup"><span data-stu-id="15f4d-120">Marking Routed Events as Handled, and Class Handling</span></span>](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [<span data-ttu-id="15f4d-121">Manipular um evento roteado</span><span class="sxs-lookup"><span data-stu-id="15f4d-121">Handle a Routed Event</span></span>](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [<span data-ttu-id="15f4d-122">Visão geral de eventos roteados</span><span class="sxs-lookup"><span data-stu-id="15f4d-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)