---
title: Como associar um controle dos Windows Forms a um tipo
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
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ffde36d9644dade3372292a6fb3961cbbfb6a5da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="74f27-102">Como associar um controle dos Windows Forms a um tipo</span><span class="sxs-lookup"><span data-stu-id="74f27-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="74f27-103">Quando estiver criando controles que interagem com os dados, às vezes, achará necessário associar um controle a um tipo, em vez de um objeto.</span><span class="sxs-lookup"><span data-stu-id="74f27-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="74f27-104">Essa situação ocorre especialmente em tempo de design, quando os dados podem não estar disponíveis, mas seus controles ligados a dados ainda precisam exibir informações da interface pública de um tipo.</span><span class="sxs-lookup"><span data-stu-id="74f27-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="74f27-105">Por exemplo, você pode associar um <xref:System.Windows.Forms.DataGridView> controle a um objeto exposto por um serviço Web e deseja que o <xref:System.Windows.Forms.DataGridView> controle para rotular suas colunas em tempo de design com o membro nomes de um tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="74f27-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="74f27-106">Você pode facilmente associar um controle a um tipo com o <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="74f27-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74f27-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="74f27-107">Example</span></span>  
 <span data-ttu-id="74f27-108">O exemplo de código a seguir demonstra como associar um <xref:System.Windows.Forms.DataGridView> controle para um tipo personalizado usando um <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="74f27-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="74f27-109">Quando você executa o exemplo, você observará o <xref:System.Windows.Forms.DataGridView> intitulada colunas que refletem as propriedades de um `Customer` do objeto, antes do controle é preenchido com dados.</span><span class="sxs-lookup"><span data-stu-id="74f27-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="74f27-110">O exemplo tem um botão Add Customer para adicionar dados ao <xref:System.Windows.Forms.DataGridView> controle.</span><span class="sxs-lookup"><span data-stu-id="74f27-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="74f27-111">Quando você clica no botão, uma nova `Customer` objeto é adicionado para o <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="74f27-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="74f27-112">Em um cenário do mundo real, os dados podem ser obtidos por uma chamada para um serviço Web ou outra fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="74f27-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74f27-113">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="74f27-113">Compiling the Code</span></span>  
 <span data-ttu-id="74f27-114">Este exemplo requer:</span><span class="sxs-lookup"><span data-stu-id="74f27-114">This example requires:</span></span>  
  
-   <span data-ttu-id="74f27-115">Referências aos assemblies Sistema e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="74f27-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="74f27-116">Para obter informações sobre como criar este exemplo da linha de comando para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) (Compilação da linha de comando) ou [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) (Compilação da linha de comando com csc.exe).</span><span class="sxs-lookup"><span data-stu-id="74f27-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="74f27-117">Também é possível compilar este exemplo em [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] colando o código em um novo projeto.</span><span class="sxs-lookup"><span data-stu-id="74f27-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="74f27-118">Consulte também [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) (Como compilar e executar um exemplo completo de código dos Windows Forms usando o Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="74f27-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f27-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="74f27-119">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="74f27-120">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="74f27-120">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)