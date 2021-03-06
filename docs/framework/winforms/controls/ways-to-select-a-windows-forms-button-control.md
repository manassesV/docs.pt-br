---
title: "Forma de selecionar um controle de botão dos Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b6fa31b89b8fbe50077933cf04aa3c17db86438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Forma de selecionar um controle de botão dos Windows Forms
Um botão dos Windows Forms pode ser selecionado das seguintes maneiras:  
  
-   Use um mouse para clicar no botão.  
  
-   Invocar o botão <xref:System.Windows.Forms.Control.Click> eventos no código.  
  
-   Mova o foco para o botão pressionando a tecla TAB e, em seguida, escolha o botão pressionando a barra de espaços ou ENTER.  
  
-   Pressione a tecla de acesso (ALT + a letra sublinhada) para o botão. Para obter mais informações sobre chaves de acesso, consulte [Como criar chaves de acesso para controles dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Se o botão for o botão "Aceitar" do formulário, pressionar ENTER seleciona o botão, mesmo se outro controle tiver o foco — exceto se o outro controle for outro botão, uma caixa de texto de várias linhas ou um controle personalizado que intercepte a tecla enter.  
  
-   Se o botão for o botão "Cancelar" do formulário, pressionar ESC seleciona o botão, mesmo se outro controle tiver o foco.  
  
-   Chamar o <xref:System.Windows.Forms.Button.PerformClick%2A> método para selecionar o botão programaticamente.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral do controle de botão](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Como responder a cliques no botão dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Controle de botão](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
