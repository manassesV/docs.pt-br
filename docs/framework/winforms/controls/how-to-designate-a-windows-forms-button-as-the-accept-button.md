---
title: "Como designar um botão dos Windows Forms como o botão Aceitar"
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
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bf5f8dbf8718cb6a30883395d54c5cbc6bafaff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="47704-102">Como designar um botão dos Windows Forms como o botão Aceitar</span><span class="sxs-lookup"><span data-stu-id="47704-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="47704-103">Em qualquer formulário do Windows, você pode designar um <xref:System.Windows.Forms.Button> controle botão aceitar, também conhecido como o botão padrão.</span><span class="sxs-lookup"><span data-stu-id="47704-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="47704-104">Sempre que o usuário pressiona a tecla ENTER, o botão padrão é clicado, independentemente de qual outro controle no formulário tem o foco.</span><span class="sxs-lookup"><span data-stu-id="47704-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47704-105">As exceções são quando o controle com foco é outro botão — nesse caso, o botão com o foco será clicado — ou uma caixa de texto de várias linhas, ou um controle personalizado que intercepta a tecla ENTER.</span><span class="sxs-lookup"><span data-stu-id="47704-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="47704-106">Para designar o botão aceitar</span><span class="sxs-lookup"><span data-stu-id="47704-106">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="47704-107">Definir o formulário <xref:System.Windows.Forms.Form.AcceptButton%2A> propriedade apropriada <xref:System.Windows.Forms.Button> controle.</span><span class="sxs-lookup"><span data-stu-id="47704-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="47704-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="47704-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="47704-109">Visão geral do controle de botão</span><span class="sxs-lookup"><span data-stu-id="47704-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="47704-110">Formas de selecionar um controle de botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47704-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="47704-111">Como responder a cliques no botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47704-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="47704-112">Como designar um botão dos Windows Forms como o botão Cancelar</span><span class="sxs-lookup"><span data-stu-id="47704-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [<span data-ttu-id="47704-113">Controle de botão</span><span class="sxs-lookup"><span data-stu-id="47704-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)