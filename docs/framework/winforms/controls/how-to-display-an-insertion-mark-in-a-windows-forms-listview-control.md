---
title: "Como exibir uma marca de inserção em um controle ListView dos Windows Forms"
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
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff59a7b716944779fd5c87b58034eb60d5981b02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a>Como exibir uma marca de inserção em um controle ListView dos Windows Forms
A marca de inserção no <xref:System.Windows.Forms.ListView> controle mostra aos usuários o ponto onde os itens arrastados serão inseridos. Quando um usuário arrasta um item para um ponto entre dois outros itens, a marca de inserção mostra o local da nova esperado do item.  
  
> [!NOTE]
>  O recurso de marca de inserção está disponível apenas em [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando o aplicativo chama o <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método. Em sistemas operacionais anteriores, qualquer código relacionado à marca de inserção não tem nenhum efeito e a marca de inserção não será exibida. Para obter mais informações, consulte <xref:System.Windows.Forms.ListViewInsertionMark>.  
  
 A imagem a seguir mostra uma marca de inserção:  
  
 ![Uma marca de inserção de ListView](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")  
  
 O exemplo de código a seguir demonstra como usar esse recurso.  
  
## <a name="example"></a>Exemplo  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies Sistema e System.Windows.Forms.  
  
 Para obter informações sobre como compilar este exemplo na linha de comando para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Building from the Command Line (Compilando na linha de comando)](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [Compilando pela linha de comando com csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Também é possível compilar este exemplo em [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] colando o código em um novo projeto.  Consulte também [Como compilar e executar um exemplo completo de código do Windows Forms usando o Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewInsertionMark>  
 [Controle ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Visão geral do controle ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Recursos do Windows XP e controles do Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Instruções Passo a Passo: Executando uma Operação do Tipo "Arrastar e Soltar" nos Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
