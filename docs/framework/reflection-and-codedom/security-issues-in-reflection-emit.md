---
title: "Problemas de segurança na emissão de reflexão | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- partially trusted code
- emitting dynamic assemblies, security
- reflection emit, security
- reflection emit, partial trust scenarios
- partial trust,emitting dynamic methods
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- dynamic assemblies, security
ms.assetid: 0f8bf8fa-b993-478f-87ab-1a1a7976d298
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6f3dc4235c75d7438f019838cb22192f4dc7c41a
ms.openlocfilehash: 5d2d814989564dfd4c2d49ebb4b44e5964cf031f
ms.contentlocale: pt-br
ms.lasthandoff: 06/02/2017

---
# <a name="security-issues-in-reflection-emit"></a>Problemas de segurança na emissão de reflexão
O [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fornece três maneiras de emitir a MSIL (Microsoft Intermediate Language), cada uma com seus próprios problemas de segurança:  
  
-   [Assemblies dinâmicos](#Dynamic_Assemblies)  
  
-   [Métodos dinâmicos hospedados anonimamente](#Anonymously_Hosted_Dynamic_Methods)  
  
-   [Métodos dinâmicos associados a assemblies existentes](#Dynamic_Methods_Associated_with_Existing_Assemblies)  
  
 Independentemente do modo como você gerar código dinâmico, a execução do código gerado requer que todas as permissões necessárias para os tipos e métodos que o código gerado usa.  
  
> [!NOTE]
>  As permissões que são necessárias para refletir o código e emitir o código foram alteradas com versões posteriores do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Consulte [Informações de versão](#Version_Information) posteriormente neste tópico.  
  
<a name="Dynamic_Assemblies"></a>   
## <a name="dynamic-assemblies"></a>Assemblies Dinâmicos  
 Os assemblies dinâmicos são criados usando as sobrecargas do método <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>. A maioria das sobrecargas desse método foi preterida no [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] devido à eliminação da política de segurança de todo o computador. (Consulte [Alterações de segurança](../../../docs/framework/security/security-changes.md).) As sobrecargas restantes podem ser executadas por qualquer código, independentemente do nível de confiança. Essas sobrecargas se enquadram em dois grupos: aquelas que especificam uma lista de atributos a ser aplicada ao assembly dinâmico quando ele é criado e aquelas que não. Se você não especificar o modelo de transparência do assembly, aplicando o atributo <xref:System.Security.SecurityRulesAttribute> quando criá-lo, o modelo de transparência será herdado do assembly emissor.  
  
> [!NOTE]
>  Os atributos aplicados ao assembly dinâmico após ele ser criado, usando o método <xref:System.Reflection.Emit.AssemblyBuilder.SetCustomAttribute%2A>, não entram em vigor até que o assembly tenha sido salvo no disco e carregado na memória novamente.  
  
 O código em um assembly dinâmico pode acessar membros e tipos visíveis em outros assemblies.  
  
> [!NOTE]
>  Os assemblies dinâmicos não usam os sinalizadores <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName> e <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> que permitem que os métodos dinâmicos acessem tipos e membros não públicos.  
  
 Os assemblies dinâmicos transitórios são criados na memória e nunca salvos no disco, portanto, eles não exigem nenhuma permissão de acesso ao arquivo. Salvar um assembly dinâmico em disco requer <xref:System.Security.Permissions.FileIOPermission> com os sinalizadores adequados.  
  
### <a name="generating-dynamic-assemblies-from-partially-trusted-code"></a>Gerando assemblies dinâmicos do código parcialmente confiável  
 Considere as condições em que um assembly com permissões de Internet pode gerar um assembly dinâmico transitório e executar seu código:  
  
-   O assembly dinâmico usa apenas tipos e membros públicos de outros assemblies.  
  
-   As permissões exigidas por esses tipos e membros são incluídas no conjunto de concessão do assembly parcialmente confiável.  
  
-   O assembly não é salvo no disco.  
  
-   Os símbolos de depuração não são gerados. (Os conjuntos de permissões `Internet` e `LocalIntranet` não incluem as permissões necessárias.)  
  
<a name="Anonymously_Hosted_Dynamic_Methods"></a>   
## <a name="anonymously-hosted-dynamic-methods"></a>Métodos Dinâmicos Hospedados Anonimamente  
 Os métodos dinâmicos hospedados anonimamente são criados usando os dois construtores <xref:System.Reflection.Emit.DynamicMethod> que não especificam um módulo ou tipo associado, <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%29> e <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29>. Esses construtores colocam os métodos dinâmicos em um assembly transparente de segurança totalmente confiável fornecido pelo sistema. Não é necessária nenhuma permissão para usar esses construtores ou para emitir o código para os métodos dinâmicos.  
  
 Em vez disso, quando um método dinâmico hospedado anonimamente é criado, a pilha de chamadas é capturada. Quando o método é construído, as demandas de segurança são feitas em relação à pilha de chamadas capturada.  
  
> [!NOTE]
>  Conceitualmente, as demandas são feitas durante a construção do método. Ou seja, as demandas podem ser feitas conforme cada instrução MSIL é emitida. Na implementação atual, todas as solicitações são feitas quando o método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A?displayProperty=fullName> é chamado ou quando o compilador JIT (Just-In-Time) é invocado, se o método for invocado sem chamar <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  
  
 Se o domínio do aplicativo permitir isso, os métodos dinâmicos hospedados anonimamente podem ignorar as verificações de visibilidade JIT, sujeitos à seguinte restrição: os tipos e membros não públicos acessados por um método dinâmico hospedado anonimamente devem estar em assemblies cujos conjuntos de concessões sejam iguais ao, ou subconjuntos de, conjunto de concessões da pilha de chamadas emissora. Essa capacidade restrita de ignorar as verificações de visibilidade JIT é habilitada se o domínio do aplicativo concede <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>.  
  
-   Se o método usar apenas membros e tipos públicos, não serão necessárias permissões durante a construção.  
  
-   Se você especificar que as verificações de visibilidade JIT devem ser ignoradas, a solicitação feita quando o método é construído incluirá <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> e o conjunto de concessões do assembly que contém o membro não público sendo acessado.  
  
 Como o conjunto de concessões do membro não público é considerado, o código parcialmente confiável que recebeu <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> não pode elevar seus privilégios executando membros não públicos de assemblies confiáveis.  
  
 Como com qualquer outro código emitido, executar o método dinâmico requer as permissões que são exigidas pelos métodos que o método dinâmico usa.  
  
 O assembly do sistema que hospeda métodos dinâmicos hospedados anonimamente usa o modelo de transparência <xref:System.Security.SecurityRuleSet.Level1?displayProperty=fullName>, que é o modelo de transparência que era usado no .NET Framework antes do [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
 Para obter mais informações, consulte a classe <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-anonymously-hosted-dynamic-methods-from-partially-trusted-code"></a>Gerando métodos dinâmicos hospedados anonimamente do código parcialmente confiável  
 Considere as condições em que um assembly com permissões de Internet pode gerar um assembly dinâmico hospedado anonimamente e executá-lo:  
  
-   O método dinâmico usa apenas tipos e membros públicos. Se o seu conjunto de concessões inclui <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>, ele pode usar membros e tipos não públicos de qualquer assembly cujo conjunto de concessões seja igual ao, ou um subconjunto do, conjunto de concessões do assembly emissor.  
  
-   As permissões exigidas por todos os tipos e membros usados pelo método dinâmico são incluídas no conjunto de concessões do assembly parcialmente confiável.  
  
> [!NOTE]
>  Os métodos dinâmicos não têm suporte para símbolos de depuração.  
  
<a name="Dynamic_Methods_Associated_with_Existing_Assemblies"></a>   
## <a name="dynamic-methods-associated-with-existing-assemblies"></a>Métodos Dinâmicos Associados a Assemblies Existentes  
 Para associar um método dinâmico a um tipo ou um módulo em um assembly existente, use qualquer um dos construtores <xref:System.Reflection.Emit.DynamicMethod> que especificam o módulo ou tipo associado. As permissões necessárias para chamar esses construtores variam, pois associar um método dinâmico a um módulo ou tipo existente fornece ao método dinâmico o acesso aos membros e tipos não públicos:  
  
-   Um método dinâmico associado um tipo tem acesso a todos os membros desse tipo, mesmo membros privados e a todos os tipos e membros internos no assembly que contém o tipo associado.  
  
-   Um método dinâmico que está associado um módulo tem acesso a todos os tipos e membros `internal` (`Friend` no Visual Basic, `assembly` nos metadados do Common Language Runtime) no módulo.  
  
 Além disso, você pode usar um construtor que especifica a capacidade de ignorar as verificações de visibilidade do compilador JIT. Fazer isso concede ao seu método dinâmico o acesso a todos os tipos e membros em todos os assemblies, independentemente do nível de acesso.  
  
 As permissões exigidas pelo construtor dependem de quanto acesso você decide conceder ao seu método dinâmico:  
  
-   Se o método usar apenas membros e tipos públicos e você associá-lo ao seu próprio tipo ou módulo, não será necessária nenhuma permissão.  
  
-   Se você especificar que as verificações de visibilidade JIT devem ser ignoradas, o construtor exigirá <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName>.  
  
-   Se você associar o método dinâmico a outro tipo, mesmo outro tipo em seu próprio assembly, o construtor exigirá <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName> e <xref:System.Security.Permissions.SecurityPermission> com o sinalizador <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=fullName>.  
  
-   Se você associar o método dinâmico a um tipo ou um módulo em outro assembly, o construtor exigirá duas coisas: <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> e o conjunto de concessões do assembly que contém o outro módulo. Ou seja, a pilha de chamadas deve incluir todas as permissões no conjunto de concessões do módulo de destino, além de <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName>.  
  
    > [!NOTE]
    >  Para compatibilidade com versões anteriores, se a exigência do conjunto de concessões com <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> falhar, o construtor exigirá <xref:System.Security.Permissions.SecurityPermission> com o sinalizador <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=fullName>.  
  
 Embora os itens nessa lista estejam descritos em termos do conjunto de concessões do assembly emissor, lembre-se de que as exigências são feitas em relação à pilha de chamadas completa, incluindo o limite de domínio do aplicativo.  
  
 Para obter mais informações, consulte a classe <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-dynamic-methods-from-partially-trusted-code"></a>Gerando métodos dinâmicos do código parcialmente confiável  
  
> [!NOTE]
>  A maneira recomendada para gerar métodos dinâmicos do código parcialmente confiável é usar [métodos dinâmicos hospedados anonimamente](#Anonymously_Hosted_Dynamic_Methods).  
  
 Considere as condições em que um assembly com permissões de Internet pode gerar um método dinâmico e executá-lo:  
  
-   O método dinâmico é associado ao módulo ou tipo que o emite ou seu conjunto de concessões inclui <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> e ele é associado a um módulo em um assembly cujo conjunto de concessões é igual ao ou um subconjunto do, conjunto de concessões do assembly emissor.  
  
-   O método dinâmico usa apenas tipos e membros públicos. Se seu conjunto de concessões incluir <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> e estiver associado a um módulo em um assembly cujo conjunto de concessões é igual ao ou um subconjunto do, conjunto de concessões do assembly emissor, ele poderá usar tipos e membros marcados com `internal` (`Friend` no Visual Basic, `assembly` nos metadados do Common Language Runtime) no módulo associado.  
  
-   As permissões exigidas por todos os tipos e membros usados pelo método dinâmico são incluídas no conjunto de concessões do assembly parcialmente confiável.  
  
-   O método dinâmico não ignora as verificações de visibilidade JIT.  
  
> [!NOTE]
>  Os métodos dinâmicos não têm suporte para símbolos de depuração.  
  
<a name="Version_Information"></a>   
## <a name="version-information"></a>Informações de versão  
 Desde o [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], a política de segurança de todo computador é eliminada e a transparência de segurança se torna o mecanismo de imposição padrão. Consulte [Alterações de segurança](../../../docs/framework/security/security-changes.md).  
  
 Desde o [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)], <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=fullName> não é mais necessário ao emitir métodos dinâmicos e assemblies dinâmicos. Esse sinalizador é exigido em todas as versões anteriores do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
> [!NOTE]
>  <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=fullName> é incluído por padrão nos conjuntos de permissões denominados `FullTrust` e `LocalIntranet`, mas não no conjunto de permissões `Internet`. Portanto, em versões anteriores do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], uma biblioteca poderá ser usada com permissões de Internet somente se ela executar um <xref:System.Security.PermissionSet.Assert%2A> para <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Tais bibliotecas exigem uma análise atenta da segurança, pois erros de código poderiam resultar em falhas de segurança. O [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] permite que o código seja emitido em cenários de confiança parcial sem emitir qualquer demanda de segurança, pois a geração de código não é uma operação inerentemente privilegiada. Ou seja, o código gerado não tem mais permissões que o assembly que o emite. Isso permite que as bibliotecas que emitem código tenham a segurança transparente e remove a necessidade de declarar <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, o que simplifica a tarefa de escrever uma biblioteca de segurança.  
  
 Além disso, o [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] introduz o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=fullName> para acessar membros e tipos não públicos de métodos dinâmicos parcialmente confiáveis. Versões anteriores do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] exigem o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=fullName> para os métodos dinâmicos que acessam os membros e tipos não públicos. Essa é uma permissão que não deve ser concedida nunca ao código parcialmente confiável.  
  
 Por fim, o [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] introduz os métodos hospedados anonimamente.  
  
### <a name="obtaining-information-on-types-and-members"></a>Obtendo informações sobre tipos e membros  
 Desde o [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)], não é necessária nenhuma permissão para obter informações sobre membros e tipos não públicos. A reflexão é usada para obter as informações necessárias para emitir métodos dinâmicos. Por exemplo, os objetos <xref:System.Reflection.MethodInfo> são usados para emitir chamadas de método. Versões anteriores do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] exigem <xref:System.Security.Permissions.ReflectionPermission> com o sinalizador <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=fullName>. Para obter mais informações, consulte [Security Considerations for Reflection](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md) (Considerações sobre segurança relacionadas à reflexão).  
  
## <a name="see-also"></a>Consulte também  
 [Security Considerations for Reflection](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)  (Considerações sobre segurança relacionadas à reflexão)  
 [Emissão de métodos e assemblies dinâmicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)