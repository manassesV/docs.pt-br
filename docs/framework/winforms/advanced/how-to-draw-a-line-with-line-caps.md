---
title: "Como desenhar uma linha com terminações"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4048757e11724aa1e175d8b18c47f48d22d807e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Como desenhar uma linha com terminações
Você pode desenhar o início ou término de uma linha em uma das várias formas chamadas terminações de linha. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]oferece suporte a várias terminações de linha, como round, quadrado, losango e ponta de seta.  
  
## <a name="example"></a>Exemplo  
 Você pode especificar as terminações de linha para o início de uma linha (início cap), o fim de uma linha final cap () ou os traços de uma linha tracejada (traço cap).  
  
 O exemplo a seguir desenha uma linha com uma ponta de seta em uma extremidade e uma extremidade redonda na outra extremidade. A ilustração mostra a linha resultante:  
  
 ![Canetas](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
  
-   Criar um formulário do Windows e controlar o formulário <xref:System.Windows.Forms.Control.Paint> eventos. Cole o código de exemplo para o <xref:System.Windows.Forms.Control.Paint> passando do manipulador de eventos `e` como <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Elementos Gráficos e Desenho nos Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Usando uma caneta para desenhar linhas e formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
