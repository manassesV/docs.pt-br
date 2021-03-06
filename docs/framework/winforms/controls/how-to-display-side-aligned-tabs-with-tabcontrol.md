---
title: Como exibir guias alinhadas lateralmente com TabControl
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
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0dcbf2cc1aee1333ad5062f2a467adfd0dbe00c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a>Como exibir guias alinhadas lateralmente com TabControl
O <xref:System.Windows.Forms.TabControl.Alignment%2A> propriedade <xref:System.Windows.Forms.TabControl> dá suporte a exibir as guias verticalmente (ao longo de borda esquerda ou direita do controle), em vez de horizontalmente (na parte superior ou inferior do controle). Por padrão, essa exibição vertical resulta em uma experiência de usuário ruim, porque o <xref:System.Windows.Forms.TabPage.Text%2A> propriedade o <xref:System.Windows.Forms.TabPage> objeto não exibidas na guia quando esses estilos estejam habilitados. Também não há nenhuma maneira direta de controlar a direção do texto dentro da guia. Você pode usar o proprietário desenhar em <xref:System.Windows.Forms.TabControl> para melhorar essa experiência.  
  
 O procedimento a seguir mostra como renderizar guias alinhadas à direita, com o texto da guia indo da esquerda para a direita, usando o recurso de “desenho do proprietário”.  
  
### <a name="to-display-right-aligned-tabs"></a>Exibir guias alinhadas à direita  
  
1.  Adicionar uma <xref:System.Windows.Forms.TabControl> ao formulário.  
  
2.  Defina a propriedade <xref:System.Windows.Forms.TabControl.Alignment%2A> como <xref:System.Windows.Forms.TabAlignment.Right>.  
  
3.  Definir o <xref:System.Windows.Forms.TabControl.SizeMode%2A> propriedade <xref:System.Windows.Forms.TabSizeMode.Fixed>, de modo que todas as guias são a mesma largura.  
  
4.  Definir o <xref:System.Windows.Forms.TabControl.ItemSize%2A> tamanho para as guias de fixo de propriedade para o preferencial. Lembre-se de que o <xref:System.Windows.Forms.TabControl.ItemSize%2A> propriedade se comporta como se foram as guias na parte superior, embora sejam alinhado à direita. Como resultado, para tornar as guias mais ampla, você deve alterar o <xref:System.Drawing.Size.Height%2A> propriedade, e para torná-las mais alto, você deve alterar o <xref:System.Drawing.Size.Width%2A> propriedade.  
  
     Para melhores resultados com o código de exemplo abaixo, defina o <xref:System.Drawing.Size.Width%2A> das guias para 25 e <xref:System.Drawing.Size.Height%2A> a 100.  
  
5.  Defina a propriedade <xref:System.Windows.Forms.TabControl.DrawMode%2A> como <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.  
  
6.  Definir um manipulador para o <xref:System.Windows.Forms.TabControl.DrawItem> evento <xref:System.Windows.Forms.TabControl> que renderiza o texto da esquerda para a direita.  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Consulte também  
 [Controle TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
