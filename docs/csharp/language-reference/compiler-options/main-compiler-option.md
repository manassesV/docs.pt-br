---
title: "-main (opções do compilador C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6dca6e62dbf69783babf2e16dc4e7c36c6705c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="main-c-compiler-options"></a>/main (opções do compilador C#)
Esta opção especifica a classe que contém o ponto de entrada para o programa, se mais de uma classe contiver um método **Main**.  
  
## <a name="syntax"></a>Sintaxe  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a>Arguments  
 `class`  
 O tipo que contém o método **Main**.  
  
## <a name="remarks"></a>Comentários  
 Se sua compilação incluir mais de um tipo com um método [Main](../../../csharp/programming-guide/main-and-command-args/index.md), você poderá especificar qual tipo contém o método **Main** que deseja usar como o ponto de entrada para o programa.  
  
 Essa opção é para uso durante a compilação de um arquivo .exe.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio  
  
1.  Abra a página **Propriedades** do projeto.  
  
2.  Clique na página de propriedades do **Aplicativo**.  
  
3.  Modifique a propriedade **Objeto de inicialização**.  
  
     Para definir programaticamente essa opção do compilador, confira <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## <a name="example"></a>Exemplo  
 Compile `t2.cs` e `t3.cs`, especificando que o método **Main** será encontrado em `Test2`:  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a>Consulte também  
 [Opções do compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gerenciando propriedades de solução e de projeto](/visualstudio/ide/managing-project-and-solution-properties)
