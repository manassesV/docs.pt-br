---
title: "Usando o escopo de edição"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79306f9e-318b-4687-9863-8b93d1841716
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6f20ff0577e43106886f5910b8f6a69578d1b3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="using-editing-scope"></a>Usando o escopo de edição
Este exemplo demonstra como em lotes um conjunto de alterações de modo que eles possam ser desfeitos em uma única unidade atômica. Por padrão, as ações executadas por um autor do designer de atividade automaticamente são integradas desfazer/refazem o sistema.  
  
## <a name="demonstrates"></a>Demonstra  
 Edite o escopo e desfaz e refaz.  
  
## <a name="discussion"></a>Discussão  
 Este exemplo demonstra como em lotes um conjunto de alterações na árvore de <xref:System.Activities.Presentation.Model.ModelItem> em uma única unidade de trabalho. Observe que ao associar aos valores de <xref:System.Activities.Presentation.Model.ModelItem> diretamente de um designer de WPF, as alterações serão aplicadas automaticamente. Este exemplo demonstra o que deve ser feito quando várias alterações a ser agrupadas estão sendo feitas com o código obrigatório, em vez de uma única alteração.  
  
 Nesse exemplo, três atividades são adicionadas. Quando editar começa, <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> é chamado uma instância de <xref:System.Activities.Presentation.Model.ModelItem>. As alterações feitas na árvore de <xref:System.Activities.Presentation.Model.ModelItem> dentro desse escopo de edição são agrupadas. O comando de <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> retorna <xref:System.Activities.Presentation.Model.EditingScope>, que podem ser usados para controlar essa instância. <xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> ou <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A> podem ser chamados a confirmação ou reverter o escopo de edição.  
  
 Você também pode aninhar objetos de <xref:System.Activities.Presentation.Model.EditingScope> , que permite vários conjuntos de alterações ser controlado como parte de um escopo maior de edição e pode ser controlado individualmente. Um cenário que pode usar esse recurso seria quando as alterações de várias caixas de diálogo devem ser adicionadas ou revertido separada, com as alterações que estão sendo tratados como uma única operação atômica. Nesse exemplo, os escopos de edição são empilhados usando <xref:System.Collections.ObjectModel.ObservableCollection%601> de tipo <xref:System.Activities.Presentation.Model.ModelEditingScope>. <xref:System.Collections.ObjectModel.ObservableCollection%601> é utilizado para que a profundidade de aninhamento pode ser observada na superfície de designer.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Para configurar, compilar, e executar o exemplo  
  
1.  Compilar e executar o exemplo, e depois use os botões à esquerda para alterar o fluxo de trabalho.  
  
2.  Clique em **abrir Editar escopo**.  
  
    1.  Este comando chama <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> que cria um escopo e envia de edição ele na pilha de edição.  
  
    2.  Três atividades são adicionadas a <xref:System.Activities.Presentation.Model.ModelItem>selecionado. Observe que se o escopo de edição não tivesse sido aberto com <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, três novas atividades apareceriam na tela de designer. Porque esta operação ainda está pendente dentro de <xref:System.Activities.Presentation.Model.EditingScope>, o designer não é atualizada ainda.  
  
3.  Pressione **escopo de edição fechar** para confirmar o escopo de edição. Três atividades aparecem no designer.  
  
> [!IMPORTANT]
>  Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\UsingEditingScope`
