---
title: "-noconfig (opções do compilador C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2b15853cdd6ee9fe12b8b3ba3388a74e49c9701
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig-c-compiler-options"></a>/noconfig (opções do compilador C#)
A opção **/noconfig** informa que o compilador não deve compilar com o arquivo csc.rsp, localizado no mesmo diretório que o arquivo csc.exe e carregado dele.  
  
## <a name="syntax"></a>Sintaxe  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a>Comentários  
 O arquivo csc.rsp referencia todos os assemblies que acompanham o .NET Framework. As referências reais que o ambiente de desenvolvimento do Visual Studio .NET inclui dependem do tipo de projeto.  
  
 É possível modificar o arquivo csc.rsp e especificar opções do compilador adicionais que devem ser incluídas em cada compilação na linha de comando com csc.exe (exceto a opção **/noconfig**).  
  
 O compilador processa as opções passadas para o comando **csc** pela última vez. Portanto, qualquer opção na linha de comando substitui a configuração da mesma opção no arquivo csc.rsp.  
  
 Se você não desejar que o compilador procure e use as configurações no arquivo csc.rsp, especifique **/noconfig**.  
  
 Essa opção do compilador não está disponível no Visual Studio e não pode ser alterada programaticamente.  
  
## <a name="see-also"></a>Consulte também  
 [Opções do compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gerenciando propriedades de solução e de projeto](/visualstudio/ide/managing-project-and-solution-properties)
