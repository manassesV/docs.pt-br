---
title: "Função NukeDownloadedCache"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="ba64b-102">Função NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="ba64b-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="ba64b-103">Exclui o cache de download do common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ba64b-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba64b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ba64b-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ba64b-105">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="ba64b-105">Return Value</span></span>  
 <span data-ttu-id="ba64b-106">Esse método retorna códigos de erro COM padrão, conforme definido no Winerror. H.</span><span class="sxs-lookup"><span data-stu-id="ba64b-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba64b-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="ba64b-107">Remarks</span></span>  
 <span data-ttu-id="ba64b-108">O cache de download do CLR é a área de armazenamento de assemblies de nomes fortes que são baixados de uma URL para possível reutilização.</span><span class="sxs-lookup"><span data-stu-id="ba64b-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba64b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba64b-109">Requirements</span></span>  
 <span data-ttu-id="ba64b-110">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba64b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba64b-111">**Cabeçalho:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ba64b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ba64b-112">**Biblioteca:** Fusion e arquivo Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="ba64b-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="ba64b-113">Use Fusion em vez do arquivo Mscorwks.dll para garantir que você a versão correta do .NET Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="ba64b-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ba64b-114">**Versões do .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba64b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba64b-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ba64b-115">See Also</span></span>  
 [<span data-ttu-id="ba64b-116">Função CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="ba64b-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="ba64b-117">Função GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="ba64b-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="ba64b-118">Funções estáticas globais de fusão</span><span class="sxs-lookup"><span data-stu-id="ba64b-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)