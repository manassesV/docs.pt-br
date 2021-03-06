---
title: "Função StrongNameSignatureVerificationEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationEx
helpviewer_keywords: StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d00c2f03968e69423da31a336d275c46291d8da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationex-function"></a>Função StrongNameSignatureVerificationEx
Obtém um valor que indica se o manifesto do assembly no caminho fornecido contém uma assinatura de nome forte.  
  
 Essa função foi preterida. Use o [: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) método em vez disso.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `wszFilePath`  
 [in] O caminho para o executável (.exe ou. dll) arquivo portátil para o assembly a ser verificado.  
  
 `fForceVerification`  
 [in] `true` para executar a verificação, mesmo se for necessário substituir as configurações do registro; caso contrário, `false`.  
  
 `pfWasVerified`  
 [out] `true` se a assinatura de nome forte foi verificado; caso contrário, `false`. `pfWasVerified`também é definido como `false` se a verificação for bem-sucedida devido às configurações do registro.  
  
## <a name="return-value"></a>Valor de retorno  
 `true`Se a verificação for bem-sucedida; Caso contrário, `false`.  
  
## <a name="remarks"></a>Comentários  
 `StrongNameSignatureVerificationEx`Fornece uma funcionalidade semelhante para o [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) função. No entanto, o segundo parâmetro de entrada e o parâmetro de saída para `StrongNameSignatureVerificationEx` são do tipo `BOOLEAN` em vez de `DWORD`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** StrongName.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Método StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [Método StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [Interface ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
