---
title: Como ocultar ToolStripMenuItems usando o designer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ac840953e34ac6726bb1c240c062d0f17b8cb71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Como ocultar ToolStripMenuItems usando o designer
Ocultar itens de menu é uma maneira de controlar a interface do usuário (IU) do seu aplicativo e restringir comandos do usuário. Geralmente, é recomendável ocultar um menu inteiro quando todos os itens de menu estão indisponíveis. Isso apresenta menos distrações para o usuário. Além disso, pode ser útil ocultar e desabilitar o menu ou item de menu, visto que apenas ocultar não impede que o usuário acesse um comando de menu usando uma tecla de atalho. Para obter mais informações sobre como desabilitar itens de menu, consulte [Como desabilitar ToolStripMenuItems usando o Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Ocultar um menu de nível superior e seus itens de submenu  
  
1.  Selecione o item de menu de nível superior e defina seu <xref:System.Windows.Forms.ToolStripItem.Visible%2A> ou <xref:System.Windows.Forms.ToolStripItem.Available%2A> propriedade `false`.  
  
     Quando você oculta o item de menu de nível superior, todos os itens de menu dentro desse menu também são ocultos. Se você clicar em outro lugar que no <xref:System.Windows.Forms.MenuStrip> depois de definir <xref:System.Windows.Forms.ToolStripItem.Visible%2A> para `false`, o item de menu de nível superior inteiro e seus itens de submenu desaparecem do formulário, assim, mostrando o efeito do tempo de execução da ação. Para exibir o item de menu de nível superior oculto em tempo de design, clique no <xref:System.Windows.Forms.MenuStrip> no **bandeja de componente**, na **esboço de documento**, ou na parte superior da grade de propriedades.  
  
> [!NOTE]
>  Você raramente ocultará um menu inteiro, exceto por menus filho MDI (interface de vários documentos) em um cenário de mesclagem.  
  
### <a name="to-hide-a-submenu-item"></a>Ocultar um item de submenu  
  
1.  Selecione o item de submenu e defina seu <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propriedade `false`.  
  
     Quando você oculta um item de submenu, ele permanece visível no formulário no tempo de design para que você pode selecioná-lo facilmente para continuar trabalhando nele. Ele será ocultado efetivamente no tempo de execução.  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Visão geral do controle MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Como desabilitar ToolStripMenuItems usando o designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
