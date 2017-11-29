---
title: "Instruções passo a passo: fornecendo itens de menu padrão para um formulário"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1eccb033dd07f634f3629fd6f314eaa3df56b422
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="a2e04-102">Instruções passo a passo: fornecendo itens de menu padrão para um formulário</span><span class="sxs-lookup"><span data-stu-id="a2e04-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="a2e04-103">Você pode fornecer um menu padrão para seus formulários com o <xref:System.Windows.Forms.MenuStrip> controle.</span><span class="sxs-lookup"><span data-stu-id="a2e04-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="a2e04-104">Este passo a passo demonstra como usar um <xref:System.Windows.Forms.MenuStrip> controle para criar um menu padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e04-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="a2e04-105">O formulário também responde quando um usuário seleciona um item de menu.</span><span class="sxs-lookup"><span data-stu-id="a2e04-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="a2e04-106">As seguintes tarefas são ilustradas nesta instrução passo a passo:</span><span class="sxs-lookup"><span data-stu-id="a2e04-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="a2e04-107">Criando um projeto do Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a2e04-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="a2e04-108">Criando um menu padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e04-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="a2e04-109">Criando um <xref:System.Windows.Forms.StatusStrip> controle.</span><span class="sxs-lookup"><span data-stu-id="a2e04-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="a2e04-110">Manipulação da seleção de item de menu.</span><span class="sxs-lookup"><span data-stu-id="a2e04-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="a2e04-111">Quando você terminar, você terá um formulário com um menu padrão que exibe as seleções de item de menu em um <xref:System.Windows.Forms.StatusStrip> controle.</span><span class="sxs-lookup"><span data-stu-id="a2e04-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="a2e04-112">Para copiar o código deste tópico como uma única lista, consulte [Como fornecer itens de menu padrão para um formulário](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="a2e04-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2e04-113">As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas.</span><span class="sxs-lookup"><span data-stu-id="a2e04-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a2e04-114">Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="a2e04-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a2e04-115">Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a2e04-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2e04-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a2e04-116">Prerequisites</span></span>  
 <span data-ttu-id="a2e04-117">Para concluir este passo a passo, você precisará de:</span><span class="sxs-lookup"><span data-stu-id="a2e04-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="a2e04-118">Permissões suficientes para poder criar e executar projetos de Aplicativo do Windows Forms no computador no qual [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="a2e04-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="a2e04-119">Criando o Projeto</span><span class="sxs-lookup"><span data-stu-id="a2e04-119">Creating the Project</span></span>  
 <span data-ttu-id="a2e04-120">A primeira etapa é criar o projeto e configurar o formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="a2e04-121">Para criar o projeto</span><span class="sxs-lookup"><span data-stu-id="a2e04-121">To create the project</span></span>  
  
1.  <span data-ttu-id="a2e04-122">Criar um projeto de aplicativos do Windows chamado **StandardMenuForm**.</span><span class="sxs-lookup"><span data-stu-id="a2e04-122">Create a Windows application project called **StandardMenuForm**.</span></span>  
  
     <span data-ttu-id="a2e04-123">Para obter mais informações, consulte [Como criar um projeto de aplicativos do Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="a2e04-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="a2e04-124">No Designer de Formulários do Windows, selecione o formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-124">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="a2e04-125">Criando um menu padrão</span><span class="sxs-lookup"><span data-stu-id="a2e04-125">Creating a Standard Menu</span></span>  
 <span data-ttu-id="a2e04-126">O Designer de formulários do Windows pode preencher automaticamente uma <xref:System.Windows.Forms.MenuStrip> controle com itens de menu padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e04-126">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="a2e04-127">Criar um menu padrão</span><span class="sxs-lookup"><span data-stu-id="a2e04-127">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="a2e04-128">Do **caixa de ferramentas**, arraste um <xref:System.Windows.Forms.MenuStrip> controle no formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-128">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="a2e04-129">Clique o <xref:System.Windows.Forms.MenuStrip> glifo de marca inteligente do controle (![marca inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selecione **inserir itens padrão**.</span><span class="sxs-lookup"><span data-stu-id="a2e04-129">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="a2e04-130">O <xref:System.Windows.Forms.MenuStrip> controle é preenchido com os itens de menu padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e04-130">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="a2e04-131">Clique no item de menu **Arquivo** para ver seus itens de menu padrão e ícones correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a2e04-131">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="a2e04-132">Criando um controle StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a2e04-132">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="a2e04-133">Use o <xref:System.Windows.Forms.StatusStrip> controle para exibir o status de seus aplicativos de formulários do Windows.</span><span class="sxs-lookup"><span data-stu-id="a2e04-133">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="a2e04-134">No exemplo atual, os itens de menu selecionados pelo usuário são exibidos em um <xref:System.Windows.Forms.StatusStrip> controle.</span><span class="sxs-lookup"><span data-stu-id="a2e04-134">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="a2e04-135">Criar um controle StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a2e04-135">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="a2e04-136">Do **caixa de ferramentas**, arraste um <xref:System.Windows.Forms.StatusStrip> controle no formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-136">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="a2e04-137">O <xref:System.Windows.Forms.StatusStrip> controle encaixa automaticamente para a parte inferior do formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-137">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="a2e04-138">Clique o <xref:System.Windows.Forms.StatusStrip> do controle de botão suspenso e selecione **StatusLabel** para adicionar um <xref:System.Windows.Forms.ToolStripStatusLabel> o controle para o <xref:System.Windows.Forms.StatusStrip> controle.</span><span class="sxs-lookup"><span data-stu-id="a2e04-138">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="a2e04-139">Manipulação da seleção de item</span><span class="sxs-lookup"><span data-stu-id="a2e04-139">Handling Item Selection</span></span>  
 <span data-ttu-id="a2e04-140">Manipular o <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento para responder quando o usuário seleciona um item de menu.</span><span class="sxs-lookup"><span data-stu-id="a2e04-140">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="a2e04-141">Manipular a seleção de itens</span><span class="sxs-lookup"><span data-stu-id="a2e04-141">To handle item selection</span></span>  
  
1.  <span data-ttu-id="a2e04-142">Clique no item de menu **Arquivo** que você criou na seção Criando um menu padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e04-142">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="a2e04-143">Na janela **Propriedades**, clique em **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="a2e04-143">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="a2e04-144">Clique duas vezes o <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="a2e04-144">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="a2e04-145">O Designer de formulários do Windows gera um manipulador de eventos para o <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento.</span><span class="sxs-lookup"><span data-stu-id="a2e04-145">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="a2e04-146">Insira o seguinte código ao manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2e04-146">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="a2e04-147">Inserir a definição de método de utilitário `UpdateStatus` ao formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-147">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="a2e04-148">Ponto de verificação</span><span class="sxs-lookup"><span data-stu-id="a2e04-148">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="a2e04-149">Testar o formulário</span><span class="sxs-lookup"><span data-stu-id="a2e04-149">To test your form</span></span>  
  
1.  <span data-ttu-id="a2e04-150">Pressione F5 para compilar e executar seu formulário.</span><span class="sxs-lookup"><span data-stu-id="a2e04-150">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="a2e04-151">Clique no item de menu **Arquivo** para abrir o menu.</span><span class="sxs-lookup"><span data-stu-id="a2e04-151">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="a2e04-152">No menu **Arquivo**, clique em um dos itens para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="a2e04-152">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="a2e04-153">O <xref:System.Windows.Forms.StatusStrip> controle exibe o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="a2e04-153">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a2e04-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a2e04-154">Next Steps</span></span>  
 <span data-ttu-id="a2e04-155">Neste passo a passo, você criou um formulário com um menu padrão.</span><span class="sxs-lookup"><span data-stu-id="a2e04-155">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="a2e04-156">Você pode usar o <xref:System.Windows.Forms.ToolStrip> família de controles para muitas outras finalidades:</span><span class="sxs-lookup"><span data-stu-id="a2e04-156">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="a2e04-157">Criar menus de atalho para os controles com <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="a2e04-157">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="a2e04-158">Para obter mais informações, consulte [Visão geral do componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a2e04-158">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="a2e04-159">Criar um formulário de interface MDI vários documentos com encaixe <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="a2e04-159">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="a2e04-160">Para obter mais informações, consulte [Instruções passo a passo: criando um formulário MDI com mesclagem de menu e controles ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a2e04-160">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="a2e04-161">Dê sua <xref:System.Windows.Forms.ToolStrip> controla uma aparência profissional.</span><span class="sxs-lookup"><span data-stu-id="a2e04-161">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="a2e04-162">Para obter mais informações, consulte [Como definir o renderizador ToolStrip para um aplicativo](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="a2e04-162">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e04-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a2e04-163">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="a2e04-164">Controle MenuStrip</span><span class="sxs-lookup"><span data-stu-id="a2e04-164">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)