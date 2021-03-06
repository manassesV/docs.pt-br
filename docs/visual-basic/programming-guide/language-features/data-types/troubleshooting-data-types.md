---
title: Solucionando problemas de tipos de dados (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d2fb1cd1be9c88ad0dd413eedb8a226fe59f41e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-data-types-visual-basic"></a>Solucionando problemas de tipos de dados (Visual Basic)
Esta página lista alguns problemas comuns que podem ocorrer quando você executa operações em tipos de dados intrínseco.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Expressões de ponto flutuantes não comparar como iguais  
 Quando você trabalha com números de ponto flutuante ([único tipo de dados](../../../../visual-basic/language-reference/data-types/single-data-type.md) e [tipo de dados Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), lembre-se de que eles são armazenados como frações binárias. Isso significa que eles não podem manter uma representação exata de qualquer quantidade que não seja uma fração binária (do formulário k / (2 ^ n) em que k e n são números inteiros). Por exemplo, 0,5 (= 1/2) e 0.3125 (= 5/16) podem ser mantidos como valores precisos, enquanto 0.2 (= 1/5) e 0,3 (= 3/10) podem ser apenas aproximações.  
  
 Devido a essa imprecisão, você não pode depender resultados exatos quando opera com valores de ponto flutuante. Em particular, os dois valores forem iguais, teoricamente, podem ter representações ligeiramente diferentes.  
  
| Para comparar as quantidades de ponto flutuantes | 
|---| 
|1.  Calcular o valor absoluto de seu diferença usando o <xref:System.Math.Abs%2A> método o <xref:System.Math> classe no <xref:System> namespace.<br />2.  Determine uma diferença máxima aceitável, de modo que você pode considerar as duas quantidades são iguais para fins práticos, se sua diferença não for maior.<br />3.  Compare o valor absoluto da diferença com a diferença aceitável.|  
  
 O exemplo a seguir demonstra a comparação correta e incorreta de dois `Double` valores.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 O exemplo anterior usa o <xref:System.Double.ToString%2A> método o <xref:System.Double> estrutura para que ele possa especificar melhor precisão que o `CStr` usa de palavra-chave. O padrão é 15 dígitos, mas o formato "G17" estende a 17 dígitos.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Operador Mod não retorna resultados precisos  
 Devido à imprecisão de armazenamento de ponto flutuante, o [operador Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) pode retornar um resultado inesperado quando pelo menos um dos operandos for ponto flutuante.  
  
 O [tipo de dados Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) não usa representação de ponto flutuante. Muitos números que são inexatos em `Single` e `Double` são exatos em `Decimal` (por exemplo 0.2 e 0,3). Embora a aritmética seja mais lenta em `Decimal` que em ponto flutuante, talvez valha a redução de desempenho para obter melhor precisão.  
  
|Para localizar o resto inteiro de quantidades de ponto flutuantes|  
|---|  
|1.  Declarar variáveis como `Decimal`.<br />2.  Use o caractere de tipo literal `D` para forçar literais a `Decimal`, no caso de seus valores são muito grandes para o `Long` tipo de dados.|  
  
 O exemplo a seguir demonstra a imprecisão potencial de operandos de ponto flutuantes.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 O exemplo anterior usa o <xref:System.Double.ToString%2A> método o <xref:System.Double> estrutura para que ele possa especificar melhor precisão que o `CStr` usa de palavra-chave. O padrão é 15 dígitos, mas o formato "G17" estende a 17 dígitos.  
  
 Porque `zeroPointTwo` é `Double`, seu valor 0,2 é uma fração binária infinitamente de repetição com um valor armazenado de 0.20000000000000001. A divisão 2.0 por essa quantidade produz 9.9999999999999995 com resto 0.19999999999999991.  
  
 Em uma expressão para `decimalRemainder`, o caractere de tipo literal `D` força ambos os operandos para `Decimal`, e 0.2 tem uma representação exata. Portanto, o `Mod` operador produz o resto 0.0 esperado.  
  
 Observe que não é suficiente declarar `decimalRemainder` como `Decimal`. Você também deve forçar os literais para `Decimal`, ou eles usam `Double` por padrão e `decimalRemainder` recebe o mesmo valor como `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Tipo booleano não converte para tipo numérico com precisão  
 [Tipo de dados Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) valores não são armazenados como números, e os valores armazenados não devem ser equivalentes a números. Para compatibilidade com versões anteriores, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] fornece palavras-chave de conversão ([função CType](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, e assim por diante) para converter entre `Boolean` e tipos numéricos. No entanto, outras linguagens, às vezes, executam essas conversões diferente, como o [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] métodos.  
  
 Você nunca deve gravar códigos que contem com valores numéricos equivalentes para `True` e `False`. Sempre que possível, você deve restringir o uso de `Boolean` variáveis para os valores lógicos para os quais eles são criados. Se você deve combinar `Boolean` e valores numéricos, certifique-se de que você entende o método de conversão que você selecionar.  
  
### <a name="conversion-in-visual-basic"></a>Conversão em Visual Basic  
 Quando você usa o `CType` ou `CBool` palavras-chave de conversão para converter tipos de dados numéricos para `Boolean`, 0 se torna `False` e todos os outros valores tornam-se `True`. Quando você converte `Boolean` valores para tipos numéricos usando as palavras-chave de conversão, `False` se torna 0 e `True` torna-se -1.  
  
### <a name="conversion-in-the-framework"></a>Conversão no Framework  
 O <xref:System.Convert.ToInt32%2A> método o <xref:System.Convert> classe no <xref:System> namespace converte `True` para + 1.  
  
 Se você deve converter um `Boolean` valor para um tipo de dados numéricos, tenha cuidado sobre qual método de conversão usar.  
  
## <a name="character-literal-generates-compiler-error"></a>Caractere Literal gera erro do compilador  
 Na ausência de qualquer caractere de tipo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] assume o padrão a tipos de dados para literais. O tipo de padrão de um caractere literal — entre aspas (`" "`) — é `String`.  
  
 O `String` tipo de dados não se estendem ao [tipo de dados Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Isso significa que, se você deseja atribuir um literal para um `Char` variável, você deve fazer uma conversão de restrição ou forçar o literal para o `Char` tipo.  

|Para criar um caractere literal para atribuir a uma variável ou constante|
|---|  
|1.  Declarar a variável ou constante como `Char`.<br />2.  Coloque o valor do caractere entre aspas (`" "`).<br />3.  Siga as aspas duplas de fechamento do caractere de tipo literal `C` para forçar o literal para `Char`. Isso é necessário se a verificação de tipo muda ([instrução Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) é `On`, e é desejável em qualquer caso.|  
  
 O exemplo a seguir demonstra atribuições bem e malsucedidas sucedidas de um literal para um `Char` variável.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Sempre há um risco usando conversões de estreitamento, pois elas podem falhar em tempo de execução. Por exemplo, uma conversão de `String` para `Char` pode falhar se o `String` valor contém mais de um caractere. Portanto, é melhor programação para usar o `C` caractere de tipo.  
  
## <a name="string-conversion-fails-at-run-time"></a>Falha na conversão de cadeia de caracteres em tempo de execução  
 O [tipo de dados de cadeia de caracteres](../../../../visual-basic/language-reference/data-types/string-data-type.md) participa de poucas conversões ampliadoras. `String`amplia somente a mesmo e `Object`e apenas `Char` e `Char()` (uma `Char` matriz) se estendem ao `String`. Isso ocorre porque `String` constantes e variáveis podem conter valores que outros tipos de dados não podem conter.  
  
 Quando a verificação de tipo muda ([instrução Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) é `On`, o compilador proíbe todos as conversões de estreitamento implícitas. Isso inclui aquelas que envolvem `String`. Seu código ainda pode usar palavras-chave de conversão, como `CStr` e [função CType](../../../../visual-basic/language-reference/functions/ctype-function.md), quais direta a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] a tentar a conversão.  
  
> [!NOTE]
>  O erro de conversão de estreitamento é suprimido para conversões de elementos em um `For Each…Next` coleção para a variável de controle de loop. Para obter mais informações e exemplos, consulte a seção "Conversões de estreitamento" [para cada um... Próxima instrução](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Proteção de conversão de estreitamento  
 A desvantagem de conversões de estreitamento é que eles podem falhar em tempo de execução. Por exemplo, se um `String` variável contiver qualquer coisa diferente de "True" ou "False", ele não pode ser convertido em `Boolean`. Se ele contiver caracteres de pontuação, a conversão em qualquer tipo numérico falhará. A menos que você sabe que seu `String` variável sempre contém valores que o tipo de destino pode aceitar, você não deve tentar uma conversão.  
  
 Se você deve converter de `String` em outro tipo de dados, o procedimento mais seguro é colocar a tentativa de conversão de [tente... Catch... Instrução Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Isso lhe permite lidar com uma falha de tempo de execução.  
  
### <a name="character-arrays"></a>Matrizes de caracteres  
 Um único `Char` e uma matriz de `Char` elementos ampliam para `String`. No entanto, `String` não se estendem ao `Char()`. Para converter um `String` valor para um `Char` matriz, você pode usar o <xref:System.String.ToCharArray%2A> método o <xref:System.String?displayProperty=nameWithType> classe.  
  
### <a name="meaningless-values"></a>Valores sem sentido  
 Em geral, `String` valores não são significativos em outros tipos de dados e a conversão é perigosa e altamente artificial. Sempre que possível, você deve restringir o uso de `String` variáveis para as sequências de caracteres para o qual eles são criados. Você nunca deve gravar códigos que contem com valores equivalentes em outros tipos.  
  
## <a name="see-also"></a>Consulte também  
 [Tipos de Dados](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Caracteres de Tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipos de Valor e Tipos de Referência](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversões de tipo no Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Tipos de Dados](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funções de Conversão do Tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Uso Eficiente de Tipos de Dados](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
