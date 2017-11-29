---
title: Como detectar quando o ponteiro do mouse passa sobre um ToolStripItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 633b92bf6da837b3727001c621548fa58b230102
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="1ab2c-102">Como detectar quando o ponteiro do mouse passa sobre um ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="1ab2c-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="1ab2c-103">Use o procedimento a seguir para detectar quando o ponteiro do mouse está sobre um <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="1ab2c-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="1ab2c-104">Detectar quando o ponteiro passa sobre um ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="1ab2c-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="1ab2c-105">Use o <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propriedade para itens na qual <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> é `true`.</span><span class="sxs-lookup"><span data-stu-id="1ab2c-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="1ab2c-106">Isso impedirá que você precise sincronizar o <xref:System.Windows.Forms.ToolStripItem.MouseEnter> e <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="1ab2c-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab2c-107">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1ab2c-107">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [<span data-ttu-id="1ab2c-108">Visão geral do controle ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1ab2c-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)