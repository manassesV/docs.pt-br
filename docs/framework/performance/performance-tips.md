---
title: Dicas de desempenho do .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: "36"
author: BillWagner
ms.author: wiwagn
manager: wpickett
ms.workload: wiwagn
ms.openlocfilehash: 60c25de889e5055241486078baf46657b6870afd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="net-performance-tips"></a>Dicas de desempenho do .NET
O termo *desempenho* geralmente se refere à velocidade de execução de um programa. Às vezes, você pode aumentar a velocidade de execução seguindo algumas regras básicas em seu código-fonte. Em alguns programas, é importante examinar atentamente o código e usar criadores de perfil para verificar se eles estão executando o mais rápido possível. Em outros programas, você não precisa executar essa otimização porque o código é executado em velocidade aceitável conforme ele é gravado. Este artigo lista algumas áreas comuns em que o desempenho pode ser prejudicado e dicas para melhorá-lo, bem como links para tópicos adicionais sobre desempenho. Para obter mais informações sobre como planejar e medir o desempenho, consulte [Desempenho](../../../docs/framework/performance/index.md)  
  
## <a name="boxing-and-unboxing"></a>Conversão boxing e unboxing  
 É melhor evitar o uso de tipos de valor em situações em que eles devem sofrer conversão boxing um grande número de vezes, por exemplo, em classes de coleções não genéricas como <xref:System.Collections.ArrayList?displayProperty=nameWithType>. Você pode evitar a conversão boxing de tipos de valor por meio de coleções genéricas como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. As conversões boxing e unboxing são processos computacionalmente dispendiosos. Quando um tipo de valor é convertido, um objeto totalmente novo deve ser criado. Isso pode levar até 20 vezes mais tempo que a atribuição de uma referência simples. Ao fazer unboxing, o processo de conversão pode demorar quatro vezes mais que uma atribuição. Para obter mais informações, consulte [Boxing e unboxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Cadeias de caracteres  
 Ao concatenar um grande número de variáveis de cadeia de caracteres, por exemplo em um loop estreito, use <xref:System.Text.StringBuilder?displayProperty=nameWithType> em vez do [operador +](~/docs/csharp/language-reference/operators/addition-operator.md) de C# ou dos [operadores de concatenação](~/docs/visual-basic/language-reference/operators/concatenation-operators.md) do Visual Basic. Para obter mais informações, consulte [Como concatenar várias cadeias de caracteres](~/docs/csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md) e [Operadores de concatenação no Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Destruidores  
 Destruidores vazios não devem ser usados. Quando uma classe contém um destruidor, uma entrada é criada na fila Finalizar. Quando o destruidor é chamado, o coletor de lixo é invocado para processar a fila. Se o destruidor estiver vazio, isso apenas resultará em uma perda de desempenho. Para obter mais informações, consulte [Destruidores](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) e [Tempo de vida do objeto: como os objetos são criados e destruídos](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Outros recursos  
  
-   [Gravar código gerenciado mais rápido: conheça o custo das coisas](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [Gravação de aplicativos de alto desempenho gerenciados: informações elementares](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [Noções básicas do coletor de lixo e dicas de desempenho](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [Dicas e truques sobre desempenho em aplicativos .NET](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [Ferramentas de Diagnóstico Internas para .NET](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Informações úteis sobre desempenho, por Rico Mariani](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## <a name="see-also"></a>Consulte também  
 [Desempenho](../../../docs/framework/performance/index.md)  
 [Conceitos de Programação](http://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)  
 [Guia de programação do Visual Basic](../../visual-basic/programming-guide/index.md)  
 [Guia de Programação em C#](http://msdn.microsoft.com/library/ac0f23a2-6bf3-4077-be99-538ae5fd3bc5)
