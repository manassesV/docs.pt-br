---
title: "virtual (Referência de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords: virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dce3333646bca6f558e3760849b6cffdb34a6c0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-c-reference"></a>virtual (Referência de C#)
A palavra-chave `virtual` é usada para modificar uma declaração de método, propriedade, indexador ou evento e permitir que ela seja substituída em uma classe derivada. Por exemplo, esse método pode ser substituído por qualquer classe que o herde:  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 A implementação de um membro virtual pode ser alterada por um [membro de substituição](../../../csharp/language-reference/keywords/override.md) em uma classe derivada. Para obter mais informações sobre como usar a palavra-chave `virtual`, consulte [Controle de versão com as palavras-chave override e new](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Quando usar as palavras-chave override e new](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="remarks"></a>Comentários  
 Quando um método virtual é invocado, o tipo de tempo de execução do objeto é verificado para um membro de substituição. O membro de substituição na classe mais derivada é chamado, que pode ser o membro original, se nenhuma classe derivada tiver substituído o membro.  
  
 Por padrão, os métodos não são virtuais. Você não pode substituir um método não virtual.  
  
 Não é possível usar o `virtual` modificador com o `static`, `abstract`, `private`, ou `override` modificadores. O exemplo a seguir mostra uma propriedade virtual:  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 Propriedades virtuais se comportam como métodos abstratos, exceto pelas diferenças na sintaxe de declaração e chamada.  
  
-   É um erro usar o modificador `virtual` em uma propriedade estática.  
  
-   Uma propriedade herdada virtual pode ser substituída em uma classe derivada incluindo uma declaração de propriedade que usa o modificador `override`.  
  
## <a name="example"></a>Exemplo  
 Neste exemplo, a classe `Shape` contém as duas coordenadas `x`, `y` e o método virtual `Area()`. Classes de forma diferentes como `Circle`, `Cylinder` e `Sphere` herdam a classe `Shape` e a área de superfície é calculada para cada figura. Cada classe derivada tem a própria implementação de substituição de `Area()`.  
  
 Observe que as classes herdadas `Circle`, `Sphere` e `Cylinder` usam construtores que inicializam a classe base, conforme mostrado na declaração a seguir.  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 O programa a seguir calcula e exibe a área apropriada para cada figura invocando a implementação apropriada do método `Area()`, de acordo com o objeto que está associado ao método.  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a>Especificação da Linguagem C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Referência de C#](../../../csharp/language-reference/index.md)  
 [Guia de Programação em C#](../../../csharp/programming-guide/index.md)  
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)  
 [Palavras-chave do C#](../../../csharp/language-reference/keywords/index.md)  
 [Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [abstract](../../../csharp/language-reference/keywords/abstract.md)  
 [override](../../../csharp/language-reference/keywords/override.md)  
 [new](../../../csharp/language-reference/keywords/new.md)
