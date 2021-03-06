---
title: "Padrão assíncrono baseado em tarefa (TAP)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 8cef1fcf-6f9f-417c-b21f-3fd8bac75007
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d195cc046ad7ea50cd3695ef32bf53be75c387da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="task-based-asynchronous-pattern-tap"></a>Padrão assíncrono baseado em tarefa (TAP)
O TAP (Padrão Assíncrono Baseado em Tarefa) baseia-se nos tipos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> no namespace <xref:System.Threading.Tasks?displayProperty=nameWithType>, os quais são usados para representar operações assíncronas arbitrárias. O TAP é o padrão de design assíncrono recomendado para novos desenvolvimentos.  
  
## <a name="naming-parameters-and-return-types"></a>Nomenclatura, parâmetros e tipos de retorno  
 O TAP usa um único método para representar o início e a conclusão de uma operação assíncrona. Esse método contrasta com o padrão APM (Modelo de Programação Assíncrona) ou `IAsyncResult`, o qual requer os métodos `Begin` e `End` e com o EAP (Padrão Assíncrono Baseado em Eventos), que requer um método com o sufixo `Async` e também requer um ou mais eventos, tipos de delegados de manipuladores de eventos e tipo derivados de `EventArg`. Métodos assíncronos no toque incluem o `Async` sufixo após o nome da operação; por exemplo, `GetAsync` para um `Get` operação. Se você estiver adicionando um método TAP a uma classe que já contenha o nome do método com o sufixo `Async`, use o sufixo `TaskAsync` em seu lugar. Por exemplo, se a classe já possuir um método `GetAsync`, use o nome `GetTaskAsync`.  
  
 O método TAP retorna <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> ou <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, dependendo se o método síncrono correspondente retorna void ou um tipo `TResult`.  
  
 Os parâmetros de um método TAP devem corresponder às definições de suas contrapartes síncronas e devem ser fornecidos na mesma ordem.  No entanto, os parâmetros `out` e `ref` são isentos dessa regra e devem ser evitados inteiramente. Quaisquer dados retornados por um parâmetro `out` ou `ref` deve, em vez disso, ser retornado como parte do `TResult` retornado por <xref:System.Threading.Tasks.Task%601> e deve usar uma tupla ou uma estrutura de dados personalizada para acomodar diversos valores. Os métodos que se dedicam exclusivamente para a criação, a manipulação ou a combinação de tarefas (onde a intenção assíncrona do método é criptografada no nome do método ou no nome do tipo ao qual pertence o método) não precisam seguir esse padrão de nomenclatura; Esses métodos são referidos como *combinadores*. Exemplos de combinadores <xref:System.Threading.Tasks.Task.WhenAll%2A> e <xref:System.Threading.Tasks.Task.WhenAny%2A>e são discutidas no [usando os combinadores baseado em tarefas internas](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md#combinators) seção do artigo [consumindo o padrão assíncrono baseado em tarefa](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).  
  
 Para obter exemplos de como a sintaxe de toque difere da sintaxe usada em herdados padrões de programação assíncrono, como o modelo APM (Asynchronous Programming) e a baseada em evento assíncrono padrão (EAP), consulte [padrões de programação assíncrona ](../../../docs/standard/asynchronous-programming-patterns/index.md).  
  
## <a name="initiating-an-asynchronous-operation"></a>Iniciando uma operação assíncrona  
 Um método assíncrono baseado no TAP pode fazer uma pequena quantidade de trabalho de forma síncrona, como validar argumentos e iniciar a operação assíncrona, antes de retornar a tarefa resultante. O trabalho síncrono deve ser mantido no mínimo possível para que o método assíncrono possa retornar rapidamente. Os motivos para um retorno rápido incluem:  
  
-   Os métodos assíncronos podem ser chamados de segmentos de interface do usuário (UI), e qualquer trabalho síncrono longo pode prejudicar a resposta do aplicativo.  
  
-   É possível iniciar vários métodos assíncronos simultaneamente. Portanto, qualquer trabalho longo na parte síncrona de um método assíncrono pode atrasar a inicialização de outras operações assíncronas, diminuindo assim os benefícios de simultaneidade.  
  
 Em alguns casos, a quantidade de trabalho necessária para concluir a operação é menor do que a quantidade de trabalho necessária para iniciar a operação de forma assíncrona. Ler de um fluxo em que a operação de leitura pode ser satisfeita pelos dados que já estão armazenados no buffer de memória é um exemplo de cenário desse tipo. Em casos como esse, a operação pode ser concluída de forma síncrona e retornar uma tarefa que já havia sido concluída.  
  
## <a name="exceptions"></a>Exceções  
 Um método assíncrono deve gerar uma exceção para ser lançada fora da chamada do método assíncrono somente em resposta a um erro de uso. Erros de uso nunca devem ocorrer em código de produção. Por exemplo, se passar uma referência nula (`Nothing` no Visual Basic) como um dos argumentos do método faz com que um estado de erro (geralmente representado por uma exceção de <xref:System.ArgumentNullException>) ocorra, você pode alterar o código chamador para garantir que uma referência nula nunca seja passada. Para todos outros erros, as exceções que ocorrem quando um método assíncrono está em execução devem ser atribuídas a tarefa retornada, mesmo quando o método assíncrono é concluído de forma síncrona antes de a tarefa ser retornada. Normalmente, uma tarefa contém no máximo uma exceção. No entanto, se a tarefa representa várias operações (por exemplo, <xref:System.Threading.Tasks.Task.WhenAll%2A>), várias exceções podem ser associadas a uma única tarefa.  
  
## <a name="target-environment"></a>Ambiente de destino  
 Quando você implementa um método TAP, pode determinar o local em que a execução assíncrona ocorre. Você pode optar por executar a carga de trabalho no pool de thread, implementá-la usando E/S assíncrona (sem ser associada a um segmento para a maior parte da execução da operação), executá-la em um thread específico (como o thread da interface do usuário) ou usar qualquer número de contextos em potencial. Um método TAP pode até mesmo não ter nada para executar, e pode retornar apenas um <xref:System.Threading.Tasks.Task> que representa a ocorrência de uma condição em outro lugar no sistema (por exemplo, uma tarefa que representa os dados que chegam em um estrutura de dados na fila). O chamador do método TAP pode bloquear a espera do método TAP para concluir de forma síncrona enquanto aguarda a tarefa resultante ou executar código adicional (continuação) após a operação assíncrona ser concluída. O criador do código de continuação tem o controle sobre o local em que o código é executado. Você pode criar o código de continuação explicitamente com os métodos da classe <xref:System.Threading.Tasks.Task> (por exemplo, <xref:System.Threading.Tasks.Task.ContinueWith%2A>) ou implicitamente usando o suporte à linguagem compilado nas continuações (por exemplo, `await` em C#, `Await` em Visual Basic, `AwaitValue` em F#).  
  
## <a name="task-status"></a>Status da tarefa  
 A classe <xref:System.Threading.Tasks.Task> fornece um ciclo de vida para operações assíncronas, e esse ciclo é representado pela enumeração <xref:System.Threading.Tasks.TaskStatus>. Para oferecer suporte a casos extremos de tipos que derivam de <xref:System.Threading.Tasks.Task> e de <xref:System.Threading.Tasks.Task%601> e suporte à separação da construção do agendamento, a classe <xref:System.Threading.Tasks.Task> expõe um método <xref:System.Threading.Tasks.Task.Start%2A>. Tarefas que são criadas pelo público <xref:System.Threading.Tasks.Task> construtores são chamados de *tarefas frios*, porque eles começam seu ciclo de vida de não agendada <xref:System.Threading.Tasks.TaskStatus.Created> estado e são agendadas somente quando <xref:System.Threading.Tasks.Task.Start%2A> é chamado em Essas instâncias. 
 
 Todas tarefas restantes começam seu ciclo de vida em um estado quente, o que significa que as operações assíncronas que elas representam já foram iniciadas, e seus status de tarefa são um valor de enumeração diferente de <xref:System.Threading.Tasks.TaskStatus.Created?displayProperty=nameWithType>. Todas as tarefas que são retornadas dos métodos TAP devem ser ativadas. **Se um método de toque internamente usa o construtor da tarefa para instanciar a tarefa a ser retornado, deve chamar o método de toque <xref:System.Threading.Tasks.Task.Start%2A> no <xref:System.Threading.Tasks.Task> objeto antes de retorná-lo.** Os consumidores de um método TAP podem presumir com segurança que a tarefa retornada está ativa e não devem tentar chamar <xref:System.Threading.Tasks.Task.Start%2A> em qualquer <xref:System.Threading.Tasks.Task> que é retornado de um método TAP. A chamada <xref:System.Threading.Tasks.Task.Start%2A> em uma tarefa ativa resulta em uma exceção de <xref:System.InvalidOperationException>.  
  
## <a name="cancellation-optional"></a>Cancelamento (opcional)  
 Em TAP, o cancelamento é opcional para implementadores e consumidores de métodos assíncronos. Se uma operação permite o cancelamento, ela expõe uma sobrecarga do método assíncrono que aceita um símbolo de cancelamento (<xref:System.Threading.CancellationToken>). Por convenção, o parâmetro é chamado `cancellationToken`.  
  
 [!code-csharp[Conceptual.TAP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#1)]
 [!code-vb[Conceptual.TAP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#1)]  
  
 A operação assíncrona monitora esse token para solicitações de cancelamento. Se ela recebe uma solicitação de cancelamento, pode escolher honrar a solicitação e cancelar a operação. Se a solicitação de cancelamento resulta em algum trabalho ser encerrado prematuramente, o método TAP retorna uma tarefa que termina em estado de <xref:System.Threading.Tasks.TaskStatus.Canceled>; não há nenhum resultado disponível, e nenhuma exceção é gerada.  O estado <xref:System.Threading.Tasks.TaskStatus.Canceled> é considerado um estado final (concluído) para uma tarefa, juntamente com os estados <xref:System.Threading.Tasks.TaskStatus.Faulted> e <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Portanto, se uma tarefa está no estado <xref:System.Threading.Tasks.TaskStatus.Canceled>, sua propriedade <xref:System.Threading.Tasks.Task.IsCompleted%2A> retorna `true`. Quando uma tarefa termina no estado <xref:System.Threading.Tasks.TaskStatus.Canceled>, todas as continuações registradas com a tarefa ou agendadas são executadas, a menos que uma opção de continuação como <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled> tenha sido especificada para optar pela não continuação. Qualquer código que esteja aguardando de forma assíncrona uma tarefa cancelada com o uso de recursos de linguagem continuará a ser executada, mas receberá <xref:System.OperationCanceledException> ou uma exceção derivada dela. O código bloqueado que espera de forma síncrona a tarefa através de métodos como <xref:System.Threading.Tasks.Task.Wait%2A> e <xref:System.Threading.Tasks.Task.WaitAll%2A> também continuará a ser executado com uma exceção.  
  
 Se um token de cancelamento solicitou o cancelamento antes do método TAP que aceita esse token ter sido chamado, o método TAP deve retornar uma tarefa <xref:System.Threading.Tasks.TaskStatus.Canceled>.  No entanto, se o cancelamento é solicitado enquanto a operação assíncrona é executada, a operação assíncrona não precisa aceitar a solicitação de cancelamento.  A tarefa retornada deverá terminar no estado <xref:System.Threading.Tasks.TaskStatus.Canceled> somente se a operação terminar como um resultado da solicitação de cancelamento. Se o cancelamento for solicitado, mas um resultado ou uma exceção ainda forem gerados, a tarefa deve terminar no estado <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> ou <xref:System.Threading.Tasks.TaskStatus.Faulted>. Para os métodos assíncronos utilizados por um desenvolvedor que deseja o cancelamento antes de tudo o mais, você não precisará fornecer uma sobrecarga que não aceite um token de cancelamento.  Para os métodos que não podem ser cancelados, não forneça sobrecargas que aceitem um token de cancelamento; isso ajuda a indicar ao chamador se o método de destino é realmente cancelável.  O código consumidor que não deseja cancelamento pode chamar um método que aceita um <xref:System.Threading.CancellationToken> e fornece <xref:System.Threading.CancellationToken.None%2A> como o valor do argumento. <xref:System.Threading.CancellationToken.None%2A> é funcionalmente equivalente ao <xref:System.Threading.CancellationToken> padrão.  
  
## <a name="progress-reporting-optional"></a>Relatório de progresso (opcional)  
 Algumas operações assíncronas beneficiam-se do fornecimento de notificações de progresso; esses são normalmente usados para atualizar uma interface do usuário com informações sobre o andamento da operação assíncrona. No TAP, o progresso é tratado por uma interface <xref:System.IProgress%601> que é passada para o método assíncrono como um parâmetro que é chamado geralmente de `progress`.  Fornecer a interface de progresso quando o método assíncrono é chamado ajuda a eliminar as condições de corrida resultantes do uso incorreto (isto é, quando os manipuladores de eventos registrados incorretamente depois que a operação é iniciada podem carecer de atualizações).  Mais importante, a interface de progresso suporta implementações de variação de progresso, conforme determinado pelo código consumidor.  Por exemplo, o código consumidor só pode importar-se com a última atualização de progresso, pode desejar armazenar em buffer todas as atualizações, pode querer chamar uma ação para cada atualização ou pode desejar controlar se a chamada é vinculada a um thread específico. Todas essas opções podem ser obtidas usando-se uma implementação diferente de interface, personalizada de acordo com as necessidades específicas do consumidor.  Assim como no cancelamento, as implementações de TAP devem fornecer um parâmetro de <xref:System.IProgress%601> somente se a API oferecer suporte a notificações de progresso. Por exemplo, se o método `ReadAsync` discutido anteriormente nesse artigo for capaz de relatar o progresso intermediário na forma do número de bytes lidos até aqui, o retorno de chamada de progresso poderá ser uma interface <xref:System.IProgress%601>:  
  
 [!code-csharp[Conceptual.TAP#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#2)]
 [!code-vb[Conceptual.TAP#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#2)]  
  
 Se um método `FindFilesAsync` retornar uma lista de todos os arquivos que estão de acordo com um padrão específico de pesquisa, o retorno da chamada de progresso deverá fornecer uma estimativa da porcentagem do trabalho concluído, bem como o conjunto atual de resultados parciais.  Isso poderia ser feito com uma tupla:  
  
 [!code-csharp[Conceptual.TAP#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#3)]
 [!code-vb[Conceptual.TAP#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#3)]  
  
 ou com um tipo de dados que é específico da API:  
  
 [!code-csharp[Conceptual.TAP#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#4)]
 [!code-vb[Conceptual.TAP#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#4)]  
  
 No último caso, o tipo de dados especial geralmente é sufixado com `ProgressInfo`.  
  
 Se as implementações de TAP fornecem sobrecargas que aceitam um parâmetro de `progress`, elas deverão permitir que o argumento seja `null`, caso em que nenhum progresso será relatado. As implementações de TAP devem relatar o progresso para o objeto <xref:System.Progress%601> de forma síncrona, o que permite que o método assíncrono forneça rapidamente o progresso e permita que o consumidor de progresso determine como e onde melhor manipular as informações. Por exemplo, a instância de progresso poderia optar por controlar retornos de chamada e gerar eventos em um contexto de sincronização capturado.  
  
## <a name="iprogresst-implementations"></a>IProgress\<T > implementações  
 O [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] fornece uma implementação única de <xref:System.IProgress%601>: <xref:System.Progress%601>. A classe <xref:System.Progress%601> é declarada da seguinte forma:  
  
```csharp  
public class Progress<T> : IProgress<T>  
{  
    public Progress();  
    public Progress(Action<T> handler);  
    protected virtual void OnReport(T value);  
    public event EventHandler<T> ProgressChanged;  
}  
```  
  
```vb  
Public Class Progress(Of T) : Inherits IProgress(Of T)  
    Public Sub New()  
    Public Sub New(handler As Action(Of T))  
    Protected Overridable Sub OnReport(value As T)  
    Public Event ProgressChanged As EventHandler(Of T>  
End Class  
```  
  
 Uma instância de <xref:System.Progress%601> expõe um evento <xref:System.Progress%601.ProgressChanged>, o qual é gerado sempre que a operação assíncrona relata uma atualização de progresso. O evento <xref:System.Progress%601.ProgressChanged> é gerado no objeto de <xref:System.Threading.SynchronizationContext> que foi capturado quando a instância de <xref:System.Progress%601> foi criada. Se não havia contexto de sincronização disponível, um contexto padrão que tem como alvo o pool de segmentos é usado. É possível registrar manipuladores com esse evento. Um único manipulador também pode ser fornecido para o construtor <xref:System.Progress%601> para maior conveniência. Seu comportamento é exatamente como um manipulador de eventos para o evento <xref:System.Progress%601.ProgressChanged>. As atualizações de progresso são geradas de forma assíncrona para evitar atrasar a operação assíncrona enquanto os manipuladores de eventos são executados. Outra implementação de <xref:System.IProgress%601> pode optar por aplicar uma semântica diferente.  
  
## <a name="choosing-the-overloads-to-provide"></a>Escolhendo as sobrecargas a serem fornecidas  
 Se uma implementação de TAP ambos os parâmetros <xref:System.Threading.Tasks.TaskFactory.CancellationToken%2A> e <xref:System.IProgress%601> opcionais, ela poderá potencialmente exigir até quatro cargas de trabalho:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
public Task MethodNameAsync(…, IProgress<T> progress);   
public Task MethodNameAsync(…,   
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken cancellationToken) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task   
Public MethodNameAsync(…, cancellationToken As CancellationToken,   
                       progress As IProgress(Of T)) As Task  
```  
  
 No entanto, muitas implementações de TAP fornecem recursos de cancelamento ou progresso de modo a exigir um único método:  
  
```csharp  
public Task MethodNameAsync(…);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
```  
  
 Se uma implementação de TAP oferecer suporte a cancelamento ou progresso, mas não a ambos, ela poderá fornecer duas sobrecargas:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
  
// … or …  
  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken) As Task  
  
' … or …  
  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task  
```  
  
 Se uma implementação de TAP oferecer suporte a cancelamento e progresso, ela poderá expor todas as quatro sobrecargas. No entanto, ela pode fornecer somente estas duas:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…,   
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken,   
                       progress As IProgress(Of T)) As Task  
```  
  
 Para compensar as duas combinações intermediárias ausentes, os desenvolvedores podem passar <xref:System.Threading.CancellationToken.None%2A> ou um <xref:System.Threading.CancellationToken> padrão para o parâmetro `cancellationToken` e `null` para o parâmetro `progress`.  
  
 Se você espera que cada uso do método TAP ofereça suporte a cancelamento ou progresso, pode omitir sobrecargas que não aceitam o parâmetro relevante.  
  
 Se você decidir expor várias sobrecargas para tornar o cancelamento ou o progresso opcional, as sobrecargas que não suportam cancelamento ou progresso devem se comportar como se passassem <xref:System.Threading.CancellationToken.None%2A> para o cancelamento ou `null` para o progresso para a sobrecarga que oferece suporte a eles.  
  
## <a name="related-topics"></a>Tópicos relacionados  
  
|Título|Descrição|  
|-----------|-----------------|  
|[Padrões de programação assíncrona](../../../docs/standard/asynchronous-programming-patterns/index.md)|Apresenta os três padrões para execução de operações assíncronas: TAP (Padrão Assíncrono Baseado em Tarefas), APM (Modelo de Programação Assíncrona) e EAP (Padrão Assíncrono Baseado em Eventos).|  
|[Implementando o padrão assíncrono baseado em tarefa](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)|Descreve como implementar o TAP de três formas: usando os compiladores C# e Visual Basic no Visual Studio, manualmente ou por meio de uma combinação de compilador com o método manual.|  
|[Consumindo o padrão assíncrono baseado em tarefa](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)|Descreve como você pode usar tarefas e retornos de chamada para implementar a espera sem causar bloqueios.|  
|[Interoperabilidade com outros tipos e padrões assíncronos](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)|Descreve como usar o TAP (Padrão Assíncrono Baseado em Tarefas) para implementar o APM (Modelo de Programação Assíncrona) e o EAP (Padrão Assíncrono Baseado em Eventos).|
