---
title: "Função GetTypeLibInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetTypeLibInfo
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: GetTypeLibInfo
helpviewer_keywords: GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f6b1ad18809b46b7a2b38137231028f696d51b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="gettypelibinfo-function"></a>Função GetTypeLibInfo
Retorna informações sobre a biblioteca de tipos especificada examinando sua [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) estrutura.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `szFile`  
 [in] O nome do arquivo da biblioteca de tipos.  
  
 `pTypeLibID`  
 [out] O GUID da biblioteca de tipos.  
  
 `pTypeLibLCID`  
 [out] A identificação da localização da biblioteca de tipos.  
  
 `pTypeLibPlatform`  
 [out] Um [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) sinalizador que identifica o sistema operacional de destino para a biblioteca de tipos. Os valores comuns são SYS_WIN32 e SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] O número de versão principal da biblioteca de tipos. Por exemplo, para versão *x. y*, o número de versão principal é *x*.  
  
 `pTypeLibMinorVer`  
 [out] O número de versão secundária da biblioteca de tipos. Por exemplo, para versão *x. y*, é o número de versão secundária *y*.  
  
## <a name="remarks"></a>Comentários  
 O `GetTypeLibInfo` função é chamada pelo [Tlbexp.exe (exportador da biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Essa ferramenta gera uma biblioteca de tipos que descreve os tipos em um assembly do common language runtime (CLR).  
  
 Se nenhum parâmetro for nulo, a função retorna um `HRESULT` de `E_POINTER`. Caso contrário, retornará `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Funções auxiliares do Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Função LoadTypeLibEx](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
