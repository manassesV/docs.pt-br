---
title: "Controle de botão (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons
- Button control [Windows Forms]
ms.assetid: d38bc40c-8040-4f19-9e88-2c665b0ab80b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1dd584896dd8698dc881eb00186c6a550f36c75f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="button-control-windows-forms"></a><span data-ttu-id="b5e35-102">Controle de botão (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b5e35-102">Button Control (Windows Forms)</span></span>
<span data-ttu-id="b5e35-103">O controle `Button` dos Windows Forms permite que o usuário clique nele para realizar uma ação.</span><span class="sxs-lookup"><span data-stu-id="b5e35-103">The Windows Forms `Button` control allows the user to click it to perform an action.</span></span> <span data-ttu-id="b5e35-104">O controle `Button` pode exibir texto e imagens.</span><span class="sxs-lookup"><span data-stu-id="b5e35-104">The `Button` control can display both text and images.</span></span> <span data-ttu-id="b5e35-105">Quando o botão é clicado, ele se parece como se estivesse sendo empurrado e solto.</span><span class="sxs-lookup"><span data-stu-id="b5e35-105">When the button is clicked, it looks as if it is being pushed in and released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5e35-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b5e35-106">In This Section</span></span>  
 [<span data-ttu-id="b5e35-107">Visão geral do controle de botão</span><span class="sxs-lookup"><span data-stu-id="b5e35-107">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 <span data-ttu-id="b5e35-108">Explica o que é esse controle e seus principais recursos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="b5e35-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="b5e35-109">Como responder a cliques no botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5e35-109">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 <span data-ttu-id="b5e35-110">Explica o uso mais básico de um botão em um Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b5e35-110">Explains the most basic use of a button on a Windows Form.</span></span>  
  
 [<span data-ttu-id="b5e35-111">Como designar um botão dos Windows Forms como o botão Aceitar</span><span class="sxs-lookup"><span data-stu-id="b5e35-111">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 <span data-ttu-id="b5e35-112">Explica como designar um controle do `Button` para ser o botão Aceitar, também conhecido como o botão padrão.</span><span class="sxs-lookup"><span data-stu-id="b5e35-112">Explains how to designate a `Button` control to be the accept button, also known as the default button.</span></span>  
  
 [<span data-ttu-id="b5e35-113">Como designar um botão dos Windows Forms como o botão Cancelar</span><span class="sxs-lookup"><span data-stu-id="b5e35-113">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 <span data-ttu-id="b5e35-114">Explica como designar um controle do `Button` para ser o botão Cancelar, que é clicado sempre que o usuário pressiona a tecla ESC.</span><span class="sxs-lookup"><span data-stu-id="b5e35-114">Explains how to designate a `Button` control to be the cancel button, which is clicked whenever the user presses the ESC key.</span></span>  
  
 [<span data-ttu-id="b5e35-115">Formas de selecionar um controle de botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5e35-115">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 <span data-ttu-id="b5e35-116">Lista os métodos de seleção de um botão.</span><span class="sxs-lookup"><span data-stu-id="b5e35-116">Lists methods of selecting a button.</span></span>  
  
 <span data-ttu-id="b5e35-117">Consulte também [Como designar um botão dos Windows Forms como botão Aceitar usando o Designer](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md) e [Como designar um botão dos Windows Forms como o botão Cancelar usando o Designer](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b5e35-117">Also see [How to: Designate a Windows Forms Button as the Accept Button Using the Designer](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md) and [How to: Designate a Windows Forms Button as the Cancel Button Using the Designer](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b5e35-118">Referência</span><span class="sxs-lookup"><span data-stu-id="b5e35-118">Reference</span></span>  
 <span data-ttu-id="b5e35-119">Classe <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="b5e35-119"><xref:System.Windows.Forms.Button> class</span></span>  
 <span data-ttu-id="b5e35-120">Descreve essa classe e tem links para todos os seus membros.</span><span class="sxs-lookup"><span data-stu-id="b5e35-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b5e35-121">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="b5e35-121">Related Sections</span></span>  
 [<span data-ttu-id="b5e35-122">Controles a serem usados nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5e35-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="b5e35-123">Fornece uma lista completa dos controles dos Windows Forms, com links para informações sobre seu uso.</span><span class="sxs-lookup"><span data-stu-id="b5e35-123">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 <span data-ttu-id="b5e35-124">Consulte também [Entrada do usuário em caixas de diálogo](http://msdn.microsoft.com/en-us/63ad8645-6842-45e8-b215-73f778e29a55) e [Como fechar caixas de diálogo e manter a entrada do usuário](http://msdn.microsoft.com/en-us/9e118fad-3bf4-4f70-a3de-a0cda2b0229d).</span><span class="sxs-lookup"><span data-stu-id="b5e35-124">Also see [User Input to Dialog Boxes](http://msdn.microsoft.com/en-us/63ad8645-6842-45e8-b215-73f778e29a55) and [How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/en-us/9e118fad-3bf4-4f70-a3de-a0cda2b0229d).</span></span>