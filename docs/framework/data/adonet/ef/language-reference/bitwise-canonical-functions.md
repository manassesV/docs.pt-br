---
title: "Funções canônicas bit a bit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a4311b610859b36f1587e5e3f85e2a5f06503e1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="bitwise-canonical-functions"></a>Funções canônicas bit a bit
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] inclui funções canônicas bit a bit.  
  
## <a name="remarks"></a>Comentários  
 A tabela a seguir mostra a [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bit a bit funções canônicas. Essas funções retornarão `Null` se `Null` entrada é fornecida. O tipo de retorno de funções é o mesmo que os tipos de argumento. Os argumentos devem ser do mesmo tipo, se a função recebe mais de um argumento. Para executar operações bit a bit em diferentes tipos, você precisa converter explicitamente para o mesmo tipo.  
  
|Função|Descrição|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Retorna a conjução bit a bit de `value1` e de `value2` como o tipo de `value1` e de `value2`.<br /><br /> **Argumentos**<br /><br /> Um `Byte`, `Int16`, `Int32`, e `Int64`.<br /><br /> **Exemplo**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (``value``)`|Retorna a negação bit a bit de `value`.<br /><br /> **Argumentos**<br /><br /> Um `Byte`, `Int16`, `Int32`, e `Int64`.<br /><br /> **Exemplo**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Retorna a disjução bit a bit de `value1` e de `value2` como o tipo de `value1` e de `value2`.<br /><br /> **Argumentos**<br /><br /> Um `Byte`, `Int16`, `Int32` e `Int64`.<br /><br /> **Exemplo**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Retorna a disjunção bit a bit exclusiva de `value1` e de `value2` como o tipo de `value1` e de `value2`.<br /><br /> **Argumentos**<br /><br /> Um `Byte`, `Int16`, `Int32` e `Int64`.<br /><br /> **Exemplo**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Consulte também  
 [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) (Funções canônicas)
