---
title: Como acessar objetos associados a linhas DataGridView dos Windows Forms
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
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66db5f6ff7b964162f77317f17a9e3a8d3ed22b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a>Como acessar objetos associados a linhas DataGridView dos Windows Forms
Às vezes, é útil exibir uma tabela de informações armazenadas em uma coleção de objetos de negócios. Quando você associa um <xref:System.Windows.Forms.DataGridView> controle para essa coleção, cada propriedade pública é exibido em sua própria coluna, a menos que a propriedade foi marcado como não pesquisável com um <xref:System.ComponentModel.BrowsableAttribute>. Por exemplo, uma coleção de objetos `Customer` teria colunas como **Nome** e **Endereço**.  
  
 Se esses objetos contiverem informações adicionais e o código que você deseja acessar, será possível alcançá-lo por meio de objetos de linha. No exemplo de código a seguir, os usuários podem selecionar várias linhas e clicar em um botão para enviar uma fatura para cada um dos clientes correspondentes.  
  
### <a name="to-access-row-bound-objects"></a>Para acessar objetos associados a linhas  
  
-   Use a propriedade <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a>Exemplo  
 O exemplo de código completo inclui um simples `Customer` implementação e associa o <xref:System.Windows.Forms.DataGridView> para um <xref:System.Collections.ArrayList> que contém alguns `Customer` objetos. O <xref:System.Windows.Forms.Control.Click> manipulador de eventos do <xref:System.Windows.Forms.Button?displayProperty=nameWithType> deve acessar o `Customer` objetos por meio de linhas, porque a coleção de cliente não está acessível fora de <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> manipulador de eventos.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies Sistema e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo na linha de comando para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Building from the Command Line (Compilando na linha de comando)](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [Compilando pela linha de comando com csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Também é possível compilar este exemplo em [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] colando o código em um novo projeto.  Consulte também [Como compilar e executar um exemplo completo de código do Windows Forms usando o Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>  
 [Exibindo dados no controle DataGridView do Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Como associar objetos a controles DataGridView do Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
