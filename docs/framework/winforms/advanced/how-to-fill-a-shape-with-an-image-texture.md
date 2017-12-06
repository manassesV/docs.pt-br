---
title: Como preencher uma forma com uma textura de imagem
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
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c20562cade6917a3426fe04861a05c4b6b0bd543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="93ecd-102">Como preencher uma forma com uma textura de imagem</span><span class="sxs-lookup"><span data-stu-id="93ecd-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="93ecd-103">Você pode preencher uma forma fechada com uma textura usando o <xref:System.Drawing.Image> classe e o <xref:System.Drawing.TextureBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="93ecd-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93ecd-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="93ecd-104">Example</span></span>  
 <span data-ttu-id="93ecd-105">O exemplo a seguir preenche uma elipse com uma imagem.</span><span class="sxs-lookup"><span data-stu-id="93ecd-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="93ecd-106">O código constrói um <xref:System.Drawing.Image> de objeto e, em seguida, passa o endereço do que <xref:System.Drawing.Image> objeto como um argumento para um <xref:System.Drawing.TextureBrush.%23ctor%2A> construtor.</span><span class="sxs-lookup"><span data-stu-id="93ecd-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="93ecd-107">A terceira instrução redimensiona a imagem e a quarta instrução preenche a elipse com repetidas cópias da imagem dimensionada.</span><span class="sxs-lookup"><span data-stu-id="93ecd-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="93ecd-108">No código a seguir, o <xref:System.Drawing.TextureBrush.Transform%2A> propriedade contém a transformação que é aplicada à imagem antes que ela é desenhada.</span><span class="sxs-lookup"><span data-stu-id="93ecd-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="93ecd-109">Suponha que a imagem original possui uma largura de 640 pixels e uma altura de 480 pixels.</span><span class="sxs-lookup"><span data-stu-id="93ecd-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="93ecd-110">A transformação reduz a imagem a 75 × 75 configurando os valores de colocação em escala horizontal e vertical.</span><span class="sxs-lookup"><span data-stu-id="93ecd-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93ecd-111">No exemplo a seguir, o tamanho da imagem é 75 × 75 e o tamanho da elipse é 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="93ecd-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="93ecd-112">Como a imagem é menor do que a elipse que ela está preenchendo, a elipse é organizada lado a lado com a imagem.</span><span class="sxs-lookup"><span data-stu-id="93ecd-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="93ecd-113">Lado a lado significa que a imagem é repetida horizontal e verticalmente até o limite da forma ser atingido.</span><span class="sxs-lookup"><span data-stu-id="93ecd-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="93ecd-114">Para obter mais informações sobre o organização lado a lado, consulte [Como organizar lado a lado uma forma com uma imagem](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="93ecd-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93ecd-115">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="93ecd-115">Compiling the Code</span></span>  
 <span data-ttu-id="93ecd-116">O exemplo anterior é projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro do <xref:System.Windows.Forms.Control.Paint> manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="93ecd-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ecd-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="93ecd-117">See Also</span></span>  
 [<span data-ttu-id="93ecd-118">Usando um pincel para preencher formas</span><span class="sxs-lookup"><span data-stu-id="93ecd-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)