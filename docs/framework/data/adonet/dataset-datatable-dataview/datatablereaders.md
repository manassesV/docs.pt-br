---
title: DataTableReaders
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0e3f3da6554239b4f04e244d3339a4280e1add85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="datatablereaders"></a>DataTableReaders
O <xref:System.Data.DataTableReader> apresenta o conteúdo de um <xref:System.Data.DataTable> ou <xref:System.Data.DataSet> na forma de um ou mais resultados de somente leitura, somente encaminhamento define.  
  
 Quando você cria um **DataTableReader** de um **DataTable**, resultante **DataTableReader** objeto contém um conjunto de resultados com os mesmos dados que o  **DataTable** do qual ele foi criado, exceto para todas as linhas que foram marcadas como excluídas. As colunas aparecem na mesma ordem que o original **DataTable**.  
  
 Um **DataTableReader** pode conter vários conjuntos de resultados se ela foi criada chamando <xref:System.Data.DataSet.CreateDataReader%2A>. Os resultados estão na mesma ordem que a **DataTables** no **DataSet** do objeto <xref:System.Data.DataSet.Tables%2A> coleção.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Criando um DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Discute como criar um **DataTableReader** objeto.  
  
 [Navegando DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Descreve o uso do **leitura** método para mover o conteúdo de um **DataTableReader**.  
  
## <a name="see-also"></a>Consulte também  
 [Retrieving and Modifying Data in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md) (Recuperando e modificando dados no ADO.NET)  
 [ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)
