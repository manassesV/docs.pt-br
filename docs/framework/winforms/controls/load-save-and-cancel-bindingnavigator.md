---
title: "Como adicionar botões Carregar, Salvar e Cancelar ao controle BindingNavigator dos Windows Forms"
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
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4bc4f53c404e3767b9f98ca5ab46b19db31f9c6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="b409b-102">Como adicionar botões Carregar, Salvar e Cancelar ao controle BindingNavigator dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b409b-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="b409b-103">O <xref:System.Windows.Forms.BindingNavigator> controle é uma finalidade especial <xref:System.Windows.Forms.ToolStrip> controle que é destinado para navegar e manipular os controles no formulário que estão associados a dados.</span><span class="sxs-lookup"><span data-stu-id="b409b-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="b409b-104">Porque ele é um <xref:System.Windows.Forms.ToolStrip> controle, o <xref:System.Windows.Forms.BindingNavigator> componente pode ser facilmente modificado para incluir comandos adicionais ou alternativos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="b409b-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="b409b-105">No procedimento a seguir, uma <xref:System.Windows.Forms.TextBox> controle está associado a dados e o <xref:System.Windows.Forms.ToolStrip> controle que é adicionado ao formulário é modificado para incluir carregar, salvar e Cancelar botões.</span><span class="sxs-lookup"><span data-stu-id="b409b-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="b409b-106">Para adicionar botões carregar, salvar e cancelar ao componente do BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="b409b-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="b409b-107">Adicione um controle <xref:System.Windows.Forms.TextBox> ao seu formulário.</span><span class="sxs-lookup"><span data-stu-id="b409b-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="b409b-108">Associa um <xref:System.Windows.Forms.BindingSource>, que está associada a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b409b-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="b409b-109">Neste exemplo, o <xref:System.Windows.Forms.BindingSource> está associado a um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b409b-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="b409b-110">Depois que o adaptador de conjunto de dados e tabela são geradas, arraste um <xref:System.Windows.Forms.BindingNavigator> controle no formulário.</span><span class="sxs-lookup"><span data-stu-id="b409b-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="b409b-111">Definir o <xref:System.Windows.Forms.BindingNavigator> do controle <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> propriedade para o <xref:System.Windows.Forms.BindingSource> no formulário que está associado aos controles.</span><span class="sxs-lookup"><span data-stu-id="b409b-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="b409b-112">Selecione o <xref:System.Windows.Forms.BindingNavigator> controle.</span><span class="sxs-lookup"><span data-stu-id="b409b-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="b409b-113">Clique no glifo de smart tag (![glifo de smart tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) para que a caixa de diálogo **Tarefas BindingNavigator** seja exibida e selecione **Editar Itens**.</span><span class="sxs-lookup"><span data-stu-id="b409b-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="b409b-114">O **Editor de Coleção de Itens** aparece.</span><span class="sxs-lookup"><span data-stu-id="b409b-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="b409b-115">No **Editor de Coleção de Itens**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b409b-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="b409b-116">Adicionar um <xref:System.Windows.Forms.ToolStripSeparator> e três <xref:System.Windows.Forms.ToolStripButton> itens selecionando o tipo apropriado de <xref:System.Windows.Forms.ToolStripItem> e clicando o **adicionar** botão.</span><span class="sxs-lookup"><span data-stu-id="b409b-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="b409b-117">Definir o <xref:System.Windows.Forms.ToolStripItem.Name%2A> propriedade dos botões para**LoadButton**,**SaveButton**, e**CancelButton**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b409b-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to**LoadButton**,**SaveButton**, and**CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="b409b-118">Definir o <xref:System.Windows.Forms.ToolStripItem.Text%2A> propriedade dos botões para**carga** `,` **salvar**, e**Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b409b-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to**Load**`,` **Save**, and**Cancel**.</span></span>  
  
    4.  <span data-ttu-id="b409b-119">Definir o <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propriedade para cada um dos botões para**texto**.</span><span class="sxs-lookup"><span data-stu-id="b409b-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to**Text**.</span></span> <span data-ttu-id="b409b-120">Como alternativa, você pode definir essa propriedade**imagem**ou**ImageAndText**e definir a imagem a ser exibida no <xref:System.Windows.Forms.ToolStripItem.Image%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="b409b-120">Alternatively, you can set this property to**Image**or**ImageAndText**and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="b409b-121">Clique em **Okey** para fechar a caixa de diálogo. Os botões são adicionados para o <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b409b-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="b409b-122">Clique com o botão direito do mouse no formulário e escolha **Exibir Código**.</span><span class="sxs-lookup"><span data-stu-id="b409b-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="b409b-123">No Editor de Códigos, localize a linha de código que carrega dados no adaptador de tabela.</span><span class="sxs-lookup"><span data-stu-id="b409b-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="b409b-124">Esse código foi gerado quando você configura a vinculação de dados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b409b-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="b409b-125">O código deve ser semelhante ao seguinte: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="b409b-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="b409b-126">Ele será mais provavelmente estará do formulário <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="b409b-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="b409b-127">Criar um manipulador de eventos para o <xref:System.Windows.Forms.ToolStripItem.Click> evento o**carga** <xref:System.Windows.Forms.ToolStripButton> criado anteriormente e mova este código de carregamento de dados para ela.</span><span class="sxs-lookup"><span data-stu-id="b409b-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Load**<xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="b409b-128">Agora, seu código deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="b409b-128">Your code should now look similar to the following:</span></span>  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. <span data-ttu-id="b409b-129">Criar um manipulador de eventos para o <xref:System.Windows.Forms.ToolStripItem.Click> eventos do **salvar** <xref:System.Windows.Forms.ToolStripButton> criado anteriormente e escrever um código para atualizar os dados dentro da tabela, o controle está vinculado a.</span><span class="sxs-lookup"><span data-stu-id="b409b-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b409b-130">Em alguns casos, o <xref:System.Windows.Forms.BindingNavigator> componente já terá um**salvar** botão, mas nenhum código será foram geradas pelo Designer de formulários do Windows.</span><span class="sxs-lookup"><span data-stu-id="b409b-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a**Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="b409b-131">Nesse caso, você pode colocar o código acima no <xref:System.Windows.Forms.ToolStripItem.Click> manipulador de eventos para esse botão, em vez de criar um botão inteiramente novo no <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b409b-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b409b-132">No entanto, o botão está desabilitado por padrão, portanto, você deve definir o <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propriedade do botão para `true` para que a função de botão corretamente.</span><span class="sxs-lookup"><span data-stu-id="b409b-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>  
  
12. <span data-ttu-id="b409b-133">Criar um manipulador de eventos para o <xref:System.Windows.Forms.ToolStripItem.Click> eventos do**Cancelar** <xref:System.Windows.Forms.ToolStripButton> criado anteriormente e escrever código para cancelar as alterações para o registro de dados que é exibido.</span><span class="sxs-lookup"><span data-stu-id="b409b-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Cancel**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b409b-134">O <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> método voltado para a linha de dados.</span><span class="sxs-lookup"><span data-stu-id="b409b-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="b409b-135">Salve as alterações feitas ao exibir um registro individual antes de navegar até o próximo registro.</span><span class="sxs-lookup"><span data-stu-id="b409b-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b409b-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b409b-136">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="b409b-137">Controle BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="b409b-137">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="b409b-138">Visão geral do componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="b409b-138">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)