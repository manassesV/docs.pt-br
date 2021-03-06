---
title: "Consultas LINQ to DataSet de depuração"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 08c66309d4c789acc0f2ddf6159a11c5fb963e80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-linq-to-dataset-queries"></a>Consultas LINQ to DataSet de depuração
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] oferece suporte a depuração de código de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] . No entanto, há algumas diferenças entre depuração [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código e não-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código gerenciado. A maioria dos recursos de depuração trabalhar com [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instruções, inclusive o passo a passo, definindo pontos de interrupção e exibir os resultados são mostrados nas janelas de depurador. No entanto, adiada execução em tem alguns efeitos colaterais que devem ser consideradas durante a depuração de consulta [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] de código e existem algumas limitações ao uso de editar e continuar. Este tópico aborda aspectos de depuração que são exclusivos para [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] comparado a não -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código gerenciado.  
  
## <a name="viewing-results"></a>Resultados de exibição  
 Você pode exibir o resultado de uma [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrução usando a caixa de diálogo QuickWatch, a janela Inspeção e DataTips. Usando uma janela de origem, você pode pausar o ponteiro em uma consulta na janela de origem e um DataTip aparecerá. Você pode copiar um [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] variável e cole-o na janela de inspeção ou a caixa de diálogo QuickWatch. Em [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], uma consulta não é avaliada quando ele for criado ou declarado, mas somente quando a consulta é executada. Isso é chamado de *execução diferida*. Portanto, a variável de consulta não tem um valor até que seja avaliada. Para obter mais informações, consulte [consultas no LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 O depurador deve avaliar uma consulta para exibir os resultados da consulta. Esta avaliação implícita ocorre quando você exibir um [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] resultado da consulta no depurador e tem alguns efeitos que você deve considerar. Cada avaliação de consulta leva tempo. Expandir o nó de resultados leva tempo. Para algumas consultas, a avaliação repetida pode causar uma caneta visível de desempenho. Avaliar uma consulta também pode causar efeitos colaterais, que são alterações ao valor de dados ou de estado do seu programa. Nem todas as consultas têm efeitos colaterais. Para determinar se uma consulta pode ser avaliada com segurança sem efeitos colaterais, você deve entender o código que implementa a consulta. Para obter mais informações, consulte [efeitos colaterais e expressões](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e).  
  
## <a name="edit-and-continue"></a>Editar e continuar  
 Editar e continuar não dá suporte a alterações para [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consultas. Se você adicionar, remover ou alterar uma [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrução durante uma sessão de depuração, uma caixa de diálogo é exibida informando que a alteração não é suportada por Edit e Continue. Nesse ponto, você pode desfazer as alterações ou parar a sessão de depuração e reiniciar uma nova sessão com o código editado.  
  
 Além disso, editar e continuar não dá suporte para alterar o tipo ou o valor de uma variável que é usado em um [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrução. Além disso, você pode desfazer as alterações ou parar e reiniciar a sessão de depuração.  
  
 No Visual c# no Visual Studio, você não pode usar Editar e continuar em qualquer código em um método que contém um [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta.  
  
 No Visual Basic no Visual Studio, você pode usar Editar e continuar não-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código, mesmo em um método que contém um [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta. Você pode adicionar ou remover o código antes do [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] instrução, mesmo se as alterações afetam o número de linha de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta. Sua experiência para de depuração do Visual Basic não[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] código permanece o mesmo antes de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] foi introduzido. Você não pode alterar, adicionar ou remover um [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] de consulta, no entanto, a menos que você parar a depuração para aplicar as alterações.  
  
## <a name="see-also"></a>Consulte também  
 [Depurando código gerenciado](/visualstudio/debugger/debugging-managed-code)  
 [Guia de Programação](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
