---
title: "Modos de seleção no controle DataGridView dos Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f6b603382382971249b08cddd482566ec6e5fa5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8fa93-102">Modos de seleção no controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fa93-102">Selection Modes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8fa93-103">Às vezes você deseja que seu aplicativo para executar ações com base nas seleções do usuário dentro de um <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="8fa93-103">Sometimes you want your application to perform actions based on user selections within a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8fa93-104">Dependendo das ações, você talvez queira restringir os tipos de seleção possíveis.</span><span class="sxs-lookup"><span data-stu-id="8fa93-104">Depending on the actions, you may want to restrict the kinds of selection that are possible.</span></span> <span data-ttu-id="8fa93-105">Por exemplo, suponha que seu aplicativo possa imprimir um relatório para o registro selecionado no momento.</span><span class="sxs-lookup"><span data-stu-id="8fa93-105">For example, suppose your application can print a report for the currently selected record.</span></span> <span data-ttu-id="8fa93-106">Nesse caso, você talvez queira configurar o <xref:System.Windows.Forms.DataGridView> controle para que clicar em qualquer lugar dentro de uma linha sempre seleciona a linha inteira e portanto pode ser selecionada para que somente uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="8fa93-106">In this case, you may want to configure the <xref:System.Windows.Forms.DataGridView> control so that clicking anywhere within a row always selects the entire row, and so that only one row at a time can be selected.</span></span>  
  
 <span data-ttu-id="8fa93-107">Você pode especificar as seleções permitidas, definindo o <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propriedade para um dos seguintes <xref:System.Windows.Forms.DataGridViewSelectionMode> valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="8fa93-107">You can specify the selections allowed by setting the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> property to one of the following <xref:System.Windows.Forms.DataGridViewSelectionMode> enumeration values.</span></span>  
  
|<span data-ttu-id="8fa93-108">Valor de DataGridViewSelectionMode</span><span class="sxs-lookup"><span data-stu-id="8fa93-108">DataGridViewSelectionMode value</span></span>|<span data-ttu-id="8fa93-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="8fa93-109">Description</span></span>|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|<span data-ttu-id="8fa93-110">Clicar em uma célula a seleciona.</span><span class="sxs-lookup"><span data-stu-id="8fa93-110">Clicking a cell selects it.</span></span> <span data-ttu-id="8fa93-111">Cabeçalhos de linha e coluna não podem ser usados para seleção.</span><span class="sxs-lookup"><span data-stu-id="8fa93-111">Row and column headers cannot be used for selection.</span></span>|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|<span data-ttu-id="8fa93-112">Clicar em uma célula a seleciona.</span><span class="sxs-lookup"><span data-stu-id="8fa93-112">Clicking a cell selects it.</span></span> <span data-ttu-id="8fa93-113">Clicar em um cabeçalho de coluna seleciona a coluna inteira.</span><span class="sxs-lookup"><span data-stu-id="8fa93-113">Clicking a column header selects the entire column.</span></span> <span data-ttu-id="8fa93-114">Cabeçalhos de coluna não podem ser usados para classificação.</span><span class="sxs-lookup"><span data-stu-id="8fa93-114">Column headers cannot be used for sorting.</span></span>|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|<span data-ttu-id="8fa93-115">Clicar em um cabeçalho de coluna ou célula seleciona a coluna inteira.</span><span class="sxs-lookup"><span data-stu-id="8fa93-115">Clicking a cell or a column header selects the entire column.</span></span> <span data-ttu-id="8fa93-116">Cabeçalhos de coluna não podem ser usados para classificação.</span><span class="sxs-lookup"><span data-stu-id="8fa93-116">Column headers cannot be used for sorting.</span></span>|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|<span data-ttu-id="8fa93-117">Clicar em um cabeçalho de linha ou célula seleciona toda a linha.</span><span class="sxs-lookup"><span data-stu-id="8fa93-117">Clicking a cell or a row header selects the entire row.</span></span>|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|<span data-ttu-id="8fa93-118">Modo de seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="8fa93-118">Default selection mode.</span></span> <span data-ttu-id="8fa93-119">Clicar em uma célula a seleciona.</span><span class="sxs-lookup"><span data-stu-id="8fa93-119">Clicking a cell selects it.</span></span> <span data-ttu-id="8fa93-120">Clicar em um cabeçalho de linha seleciona toda a linha.</span><span class="sxs-lookup"><span data-stu-id="8fa93-120">Clicking a row header selects the entire row.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8fa93-121">Alterar o modo de seleção em tempo de execução automaticamente limpa a seleção atual.</span><span class="sxs-lookup"><span data-stu-id="8fa93-121">Changing the selection mode at run time automatically clears the current selection.</span></span>  
  
 <span data-ttu-id="8fa93-122">Por padrão, os usuários podem selecionar várias linhas, colunas ou células arrastando com o mouse, pressionando CTRL ou SHIFT ao selecionar para estender ou modificar uma seleção ou clicando na célula de cabeçalho do canto superior esquerdo para selecionar todas as células no controle.</span><span class="sxs-lookup"><span data-stu-id="8fa93-122">By default, users can select multiple rows, columns, or cells by dragging with the mouse, pressing CTRL or SHIFT while selecting to extend or modify a selection, or clicking the top-left header cell to select all cells in the control.</span></span> <span data-ttu-id="8fa93-123">Para evitar esse comportamento, defina o <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propriedade `false`.</span><span class="sxs-lookup"><span data-stu-id="8fa93-123">To prevent this behavior, set the <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> property to `false`.</span></span>  
  
 <span data-ttu-id="8fa93-124">O <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> e <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> modos de permitir que os usuários excluir linhas selecionando-os e pressionando a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="8fa93-124">The <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> and <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> modes allow users to delete rows by selecting them and pressing the DELETE key.</span></span> <span data-ttu-id="8fa93-125">Os usuários podem excluir linhas apenas quando a célula atual não está no modo de edição, o <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> está definida como `true`, e a fonte de dados subjacente oferece suporte a exclusão da linha controlada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8fa93-125">Users can delete rows only when the current cell is not in edit mode, the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property is set to `true`, and the underlying data source supports user-driven row deletion.</span></span> <span data-ttu-id="8fa93-126">Observe que essas configurações não impedem a exclusão programática de linha.</span><span class="sxs-lookup"><span data-stu-id="8fa93-126">Note that these settings do not prevent programmatic row deletion.</span></span>  
  
## <a name="programmatic-selection"></a><span data-ttu-id="8fa93-127">Seleção programática</span><span class="sxs-lookup"><span data-stu-id="8fa93-127">Programmatic Selection</span></span>  
 <span data-ttu-id="8fa93-128">O modo de seleção atual restringe o comportamento de seleção programática, bem como a seleção do usuário.</span><span class="sxs-lookup"><span data-stu-id="8fa93-128">The current selection mode restricts the behavior of programmatic selection as well as user selection.</span></span> <span data-ttu-id="8fa93-129">Você pode alterar a seleção atual por meio de programação, definindo a `Selected` propriedade de todas as células, linhas ou colunas presentes no <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="8fa93-129">You can change the current selection programmatically by setting the `Selected` property of any cells, rows, or columns present in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8fa93-130">Você também pode selecionar todas as células no controle por meio de <xref:System.Windows.Forms.DataGridView.SelectAll%2A> método, dependendo do modo de seleção.</span><span class="sxs-lookup"><span data-stu-id="8fa93-130">You can also select all cells in the control through the <xref:System.Windows.Forms.DataGridView.SelectAll%2A> method, depending on the selection mode.</span></span> <span data-ttu-id="8fa93-131">Para limpar a seleção, use o <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8fa93-131">To clear the selection, use the <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> method.</span></span>  
  
 <span data-ttu-id="8fa93-132">Se o <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está definida como `true`, você pode adicionar <xref:System.Windows.Forms.DataGridView> elementos ou removê-los da seleção, alterando o `Selected` propriedade do elemento.</span><span class="sxs-lookup"><span data-stu-id="8fa93-132">If the <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> property is set to `true`, you can add <xref:System.Windows.Forms.DataGridView> elements to or remove them from the selection by changing the `Selected` property of the element.</span></span> <span data-ttu-id="8fa93-133">Caso contrário, configurar a propriedade `Selected` como `true` para um elemento remove automaticamente os outros elementos da seleção.</span><span class="sxs-lookup"><span data-stu-id="8fa93-133">Otherwise, setting the `Selected` property to `true` for one element automatically removes other elements from the selection.</span></span>  
  
 <span data-ttu-id="8fa93-134">Observe que o valor de alterar o <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propriedade não altera a seleção atual.</span><span class="sxs-lookup"><span data-stu-id="8fa93-134">Note that changing the value of the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property does not alter the current selection.</span></span>  
  
 <span data-ttu-id="8fa93-135">Você pode recuperar uma coleção das células selecionadas no momento, linhas ou colunas por meio de <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> propriedades do <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="8fa93-135">You can retrieve a collection of the currently selected cells, rows, or columns through the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> properties of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8fa93-136">O acesso a essas propriedades é ineficiente quando todas as células no controle estão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="8fa93-136">Accessing these properties is inefficient when every cell in the control is selected.</span></span> <span data-ttu-id="8fa93-137">Para evitar uma penalidade de desempenho nesse caso, use o <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método primeiro.</span><span class="sxs-lookup"><span data-stu-id="8fa93-137">To avoid a performance penalty in this case, use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method first.</span></span> <span data-ttu-id="8fa93-138">Além disso, acessar essas coleções para determinar o número de células, linhas ou colunas selecionadas pode ser ineficiente.</span><span class="sxs-lookup"><span data-stu-id="8fa93-138">Additionally, accessing these collections to determine the number of selected cells, rows, or columns can be inefficient.</span></span> <span data-ttu-id="8fa93-139">Em vez disso, você deve usar o <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, ou <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> método, passando o <xref:System.Windows.Forms.DataGridViewElementStates.Selected> valor.</span><span class="sxs-lookup"><span data-stu-id="8fa93-139">Instead, you should use the <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, or <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> method, passing in the <xref:System.Windows.Forms.DataGridViewElementStates.Selected> value.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="8fa93-140">Código de exemplo que demonstra o uso programático das células selecionadas pode ser encontrado no <xref:System.Windows.Forms.DataGridView> visão geral da classe.</span><span class="sxs-lookup"><span data-stu-id="8fa93-140">Example code that demonstrates the programmatic use of selected cells can be found in the <xref:System.Windows.Forms.DataGridView> class overview.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa93-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8fa93-141">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [<span data-ttu-id="8fa93-142">Seleção e uso da Área de Transferência com o controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fa93-142">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="8fa93-143">Como definir o modo de seleção do controle DataGridView dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fa93-143">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)