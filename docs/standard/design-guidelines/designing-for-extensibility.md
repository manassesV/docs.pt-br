---
title: "Criação de extensibilidade"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f21e9239199ecd36432ed8f14adb896f1799506b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/23/2017
---
# <a name="designing-for-extensibility"></a>Criação de extensibilidade
Um aspecto importante da criação de uma estrutura é verificar se que a extensibilidade do framework foram considerada com cuidado. Isso requer que você entenda os custos e os benefícios associados a vários mecanismos de extensibilidade. Este capítulo ajuda você a decidir qual dos mecanismos de extensibilidade — subclassificação, eventos, membros virtuais, retornos de chamada e assim por diante — melhor pode atender aos requisitos da sua estrutura.  
  
 Há várias maneiras para permitir a extensibilidade em estruturas. Elas variam de menos eficiente, mas menos dispendiosa para muito eficientes, mas caros. Para qualquer requisito de extensibilidade de determinado, você deve escolher o mecanismo de extensibilidade menos dispendioso que atenda aos requisitos. Tenha em mente que é possível adicionar mais extensibilidade posteriormente, mas você pode nunca tirá-lo sem introduzir alterações significativas.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Classes não seladas](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Membros protegidos](../../../docs/standard/design-guidelines/protected-members.md)  
 [Eventos e retornos de chamada](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Membros virtuais](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstrações (tipos e interfaces abstratos)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Classes base para implementar abstrações](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Selar](../../../docs/standard/design-guidelines/sealing.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*  
  
 *Reimpressas pela permissão de Pearson educação, Inc. de [diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008, Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*  
  
## <a name="see-also"></a>Consulte também  
 [Diretrizes de design do Framework](../../../docs/standard/design-guidelines/index.md)
