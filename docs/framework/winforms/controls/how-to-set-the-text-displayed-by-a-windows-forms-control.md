---
title: Como definir o texto exibido por um controle dos Windows Forms
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
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a81c2202400968b4d4c95b40de7476fbd68d6182
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="833a7-102">Como definir o texto exibido por um controle dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="833a7-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="833a7-103">Controles dos Windows Forms normalmente exibem algum texto que está relacionado à função primária do controle.</span><span class="sxs-lookup"><span data-stu-id="833a7-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="833a7-104">Por exemplo, um <xref:System.Windows.Forms.Button> controle geralmente exibe uma legenda que indica qual ação será executada quando o botão é clicado.</span><span class="sxs-lookup"><span data-stu-id="833a7-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="833a7-105">Para todos os controles, você pode definir ou retornar o texto usando o <xref:System.Windows.Forms.Control.Text%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="833a7-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="833a7-106">Você pode alterar a fonte usando o <xref:System.Windows.Forms.Control.Font%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="833a7-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="833a7-107">Você também pode definir o texto usando o designer.</span><span class="sxs-lookup"><span data-stu-id="833a7-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="833a7-108">Consulte também [Como criar chaves de acesso para controles dos Windows Forms usando o Designer](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [Como definir o texto exibido por um controle dos Windows Forms usando o Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [Como definir a imagem exibida por um controle dos Windows Forms usando o Designer](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="833a7-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="833a7-109">Como definir o texto exibido por um controle de forma programática</span><span class="sxs-lookup"><span data-stu-id="833a7-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="833a7-110">Definir o <xref:System.Windows.Forms.Control.Text%2A> propriedade como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="833a7-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="833a7-111">Para criar uma tecla de acesso sublinhada, inclua um e comercial (&) antes da letra que será a tecla de acesso.</span><span class="sxs-lookup"><span data-stu-id="833a7-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="833a7-112">Definir o <xref:System.Windows.Forms.Control.Font%2A> propriedade para um objeto do tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="833a7-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="833a7-113">Você pode usar um caractere de escape para exibir um caractere especial nos elementos de interface do usuário que seriam normalmente interpretados de maneira diferente, como itens de menu.</span><span class="sxs-lookup"><span data-stu-id="833a7-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="833a7-114">Por exemplo, a linha de código a seguir define o texto do item de menu para ler "& agora para algo completamente diferente":</span><span class="sxs-lookup"><span data-stu-id="833a7-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="833a7-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="833a7-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="833a7-116">Como criar teclas de acesso para controles dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="833a7-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="833a7-117">Como responder a cliques no botão dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="833a7-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)