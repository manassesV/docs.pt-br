---
title: "Como verificar se um GridSplitter está visível"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8692d356b1b20c7405b4478cef1d16c173389ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="7b212-102">Como verificar se um GridSplitter está visível</span><span class="sxs-lookup"><span data-stu-id="7b212-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="7b212-103">Este exemplo mostra como verificar se um <xref:System.Windows.Controls.GridSplitter> controle não está oculto pelos outros controles em um <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="7b212-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b212-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7b212-104">Example</span></span>  
 <span data-ttu-id="7b212-105">O <xref:System.Windows.Controls.Panel.Children%2A> de um <xref:System.Windows.Controls.Grid> controle são renderizados na ordem que eles estão definidos na marcação ou código.</span><span class="sxs-lookup"><span data-stu-id="7b212-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="7b212-106"><xref:System.Windows.Controls.GridSplitter>controles podem estar ocultos por outros controles, se você não defini-los como os últimos elementos no <xref:System.Windows.Controls.Panel.Children%2A> coleção ou se você fornecer a outros controles de posterior <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="7b212-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="7b212-107">Para impedir que oculta <xref:System.Windows.Controls.GridSplitter> controles, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="7b212-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="7b212-108">Verifique se <xref:System.Windows.Controls.GridSplitter> controles são as últimas <xref:System.Windows.Controls.Panel.Children%2A> adicionado para o <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="7b212-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="7b212-109">A exemplo a seguir mostra o <xref:System.Windows.Controls.GridSplitter> como o último elemento de <xref:System.Windows.Controls.Panel.Children%2A> coleção do <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="7b212-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="7b212-110">Definir o <xref:System.Windows.Controls.Panel.ZIndexProperty> no <xref:System.Windows.Controls.GridSplitter> seja maior do que um controle que outra forma seria ocultá-lo.</span><span class="sxs-lookup"><span data-stu-id="7b212-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="7b212-111">O exemplo a seguir fornece o <xref:System.Windows.Controls.GridSplitter> controlar posterior <xref:System.Windows.Controls.Panel.ZIndexProperty> que o <xref:System.Windows.Controls.Button> controle.</span><span class="sxs-lookup"><span data-stu-id="7b212-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="7b212-112">Define as margens do controle que iria ocultar caso contrário, o <xref:System.Windows.Controls.GridSplitter> para que o <xref:System.Windows.Controls.GridSplitter> é exposto.</span><span class="sxs-lookup"><span data-stu-id="7b212-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="7b212-113">O exemplo a seguir define margens em um controle que iria do contrário sobrepor e ocultar o <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="7b212-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="7b212-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7b212-114">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="7b212-115">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="7b212-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)