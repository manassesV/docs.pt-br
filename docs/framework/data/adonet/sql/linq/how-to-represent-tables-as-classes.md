---
title: 'Como: Representa tabelas como classes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 27e3d21e42dbf841768e2a68ccbfff62368500bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-tables-as-classes"></a>Como: Representa tabelas como classes
Use o [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar uma classe como uma classe de entidade associada a uma tabela de banco de dados.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Para mapear uma classe a uma tabela de base de dados  
  
-   Adicione o atributo de <xref:System.Data.Linq.Mapping.TableAttribute> à declaração de classe.  
  
## <a name="example"></a>Exemplo  
 O código a seguir estabelece a classe de `Customer` como uma classe de entidade que está associada com a tabela de base de dados de `Customers` .  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Você não precisa especificar a propriedade de <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> se o nome pode ser inferido. Se você não especificar um nome, o nome é presumido ser o mesmo nome que a propriedade ou do campo.  
  
## <a name="see-also"></a>Consulte também  
 [O modelo de objeto LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Como personalizar classes de entidade usando o Editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
