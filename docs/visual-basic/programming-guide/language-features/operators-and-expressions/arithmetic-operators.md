---
title: "Operadores aritméticos no Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7fec98c38eebc34a0f84e051dc7c0914f537418f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="arithmetic-operators-in-visual-basic"></a>Operadores aritméticos no Visual Basic
Operadores aritméticos são usados para executar muitas das operações aritméticas familiares que envolvem o cálculo de valores numéricos representados por literais, variáveis, outras expressões, função e chamadas de propriedade e constantes. Também são classificados com operadores aritméticos são os operadores bit shift, que atuam no nível dos bits individuais dos operandos e mudar seus padrões de bits para a esquerda ou direita.  
  
## <a name="arithmetic-operations"></a>Operações aritméticas  
 Você pode adicionar dois valores em uma expressão junto com o [operador +](../../../../visual-basic/language-reference/operators/addition-operator.md), ou subtrair um outro com o [-operador (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), como demonstrado no exemplo a seguir.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Negação também usa o [-operador (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), mas com apenas um operando, como o exemplo a seguir demonstra.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Multiplicação e divisão usam o [* operador](../../../../visual-basic/language-reference/operators/multiplication-operator.md) e [/ operador (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), respectivamente, como demonstrado no exemplo a seguir.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Exponenciação usa o [^ operador](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), como demonstrado no exemplo a seguir.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 Divisão de inteiro é realizada usando o [\ operador (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). Divisão de inteiros retorna o quociente, ou seja, o inteiro que representa o número de vezes o divisor pode dividir no dividendo sem consideração de todo o restante. O divisor e o dividendo devem ser tipos integrais (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, e `ULong`) para esse operador. Todos os outros tipos devem ser convertidos em um tipo integral pela primeira vez. O exemplo a seguir demonstra a divisão.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 Módulo aritmético é realizado usando o [operador Mod](../../../../visual-basic/language-reference/operators/mod-operator.md). Esse operador retorna o resto após dividir o divisor no dividendo um número integral de vezes. Se o divisor e o dividendo são tipos integral, o valor retornado é integral. Se o divisor e o dividendo são tipos de ponto flutuante, o valor retornado também é ponto flutuante. O exemplo a seguir demonstra esse comportamento.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>Tentativa de divisão por Zero  
 Divisão por zero tem resultados diferentes dependendo dos tipos de dados envolvidos. Em divisões integrais (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), o [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] lança um <xref:System.DivideByZeroException> exceção. Em operações de divisão no `Decimal` ou `Single` tipo de dados, o [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] também gera um <xref:System.DivideByZeroException> exceção.  
  
 Em divisões de ponto flutuantes que envolvem o `Double` tipo de dados, nenhuma exceção é gerada e o resultado é o membro da classe que representa <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, ou <xref:System.Double.NegativeInfinity>, dependendo o dividendo. A tabela a seguir resume os resultados várias de tentar dividir um `Double` valor por zero.  
  
|Tipo de dados do dividendo|Tipo de dados do divisor|Valor de dividendo|Resultado|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(não um número definido matematicamente)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Quando você captura um <xref:System.DivideByZeroException> exceção, você pode usar seus membros para ajudá-lo a tratá-la. Por exemplo, o <xref:System.Exception.Message%2A> propriedade contém o texto da mensagem da exceção. Para obter mais informações, consulte [Instrução Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Operações bit Shift  
 Uma operação bit shift executa um deslocamento aritmético em um padrão de bit. O padrão está contido no operando à esquerda, enquanto o operando à direita especifica o número de posições para deslocar o padrão. Você pode alterar o padrão para a direita com o [>> operador](../../../../visual-basic/language-reference/operators/right-shift-operator.md) ou para a esquerda com a [<< operador](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 O tipo de dados do operando padrão deve ser `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, ou `ULong`. O tipo de dados do operando quantidade turno deve ser `Integer` ou deve ampliar a `Integer`.  
  
 Deslocamentos aritméticos não são circulares, que significa que os bits deslocados uma extremidade do resultado não são reintroduzidos na outra extremidade. As posições de bit disponíveis por um deslocamento são definidas da seguinte maneira:  
  
-   0 para um deslocamento aritmético à esquerda  
  
-   0 para um deslocamento aritmético à direita de um número positivo  
  
-   0 para um deslocamento aritmético à direita de um tipo de dados sem sinal (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 para um deslocamento aritmético à direita de um número negativo (`SByte`, `Short`, `Integer`, ou `Long`)  
  
 O exemplo a seguir desloca um `Integer` valor esquerda e direita.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Deslocamentos aritméticos nunca geram exceções de estouro.  
  
## <a name="bitwise-operations"></a>Operações bit a bit  
 Além de serem operadores lógicos, `Not`, `Or`, `And`, e `Xor` também executam aritmética bit a bit quando usado em valores numéricos. Para obter mais informações, consulte "Operações bit a bit" em [lógica e operadores de bit a bit no Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Segurança de tipo  
 Normalmente, os operandos devem ser do mesmo tipo. Por exemplo, se você estiver fazendo adição com uma `Integer` variável, você deverá adicioná-lo para outro `Integer` variável e você deve atribuir o resultado a uma variável do tipo `Integer` também.  
  
 Uma maneira para garantir o bom fortemente tipado prática de codificação é usar o [instrução Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Se você definir `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] executa automaticamente *fortemente tipado* conversões. Por exemplo, se você tentar adicionar um `Integer` variável para um `Double` variável e atribuir o valor para um `Double` variável, a operação continua normalmente, porque um `Integer` valor pode ser convertido em `Double` sem perda de dados. Conversões de tipo inseguro, por outro lado, causa um erro do compilador com `Option Strict On`. Por exemplo, se você tentar adicionar um `Integer` variável para um `Double` variável e atribuir o valor para um `Integer` variável, um erro do compilador resulta, porque uma `Double` variável não pode ser convertida implicitamente para tipo `Integer`.  
  
 Se você definir `Option Strict Off`, no entanto, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] permite conversões de estreitamento implícitas entrem em vigor, embora isso pode resultar na perda de dados ou precisão inesperada. Por esse motivo, recomendamos que você use `Option Strict On` quando escrever código de produção. Para obter mais informações, consulte [Ampliando e restringindo conversões](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Consulte também  
 [Operadores Aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operadores Bit Shift](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operadores de comparação no Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operadores de concatenação no Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Operadores lógicos e bit a bit no Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Combinação Eficiente de Operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
