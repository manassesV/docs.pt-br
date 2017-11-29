---
title: Estrutura OSINFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: OSINFO
api_location: mscoree.dll
api_type: COM
f1_keywords: OSINFO
helpviewer_keywords: OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 700e9bcfe33e5be3725bd24b212b3a77ad139b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="osinfo-structure"></a><span data-ttu-id="c7164-102">Estrutura OSINFO</span><span class="sxs-lookup"><span data-stu-id="c7164-102">OSINFO Structure</span></span>
<span data-ttu-id="c7164-103">Contém detalhes sobre o sistema operacional para um assembly ou módulo.</span><span class="sxs-lookup"><span data-stu-id="c7164-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7164-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c7164-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c7164-105">Membros</span><span class="sxs-lookup"><span data-stu-id="c7164-105">Members</span></span>  
  
|<span data-ttu-id="c7164-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c7164-106">Member</span></span>|<span data-ttu-id="c7164-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7164-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="c7164-108">Um dos valores de identificador definidos pela função de plataforma do Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="c7164-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="c7164-109">Há suporte para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c7164-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="c7164-110">-VER_PLATFORM_WIN32s, ou 0x0000, para especificar o Microsoft Windows 3.1.</span><span class="sxs-lookup"><span data-stu-id="c7164-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="c7164-111">-VER_PLATFORM_WIN32_WINDOWS, ou 0x0001, para especificar o Windows 95, Windows 98 ou sistemas operacionais descendentes do-los.</span><span class="sxs-lookup"><span data-stu-id="c7164-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="c7164-112">-VER_PLATFORM_WIN32_NT, ou 0x0010, para especificar o Windows NT ou sistemas operacionais descendentes dele.</span><span class="sxs-lookup"><span data-stu-id="c7164-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="c7164-113">A versão principal do sistema operacional, ou um valor nulo para indicar qualquer versão.</span><span class="sxs-lookup"><span data-stu-id="c7164-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="c7164-114">A versão secundária do sistema operacional, ou um valor nulo para indicar qualquer versão.</span><span class="sxs-lookup"><span data-stu-id="c7164-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7164-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="c7164-115">Remarks</span></span>  
 <span data-ttu-id="c7164-116">`OSINFO`se baseia o `OSVERSIONINFOEX` estrutura que é usado em chamadas para a função de plataforma do Microsoft Windows `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="c7164-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="c7164-117">Essa estrutura é usada pela estrutura ASSEMBLYMETADATA para indicar o suporte do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c7164-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7164-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7164-118">Requirements</span></span>  
 <span data-ttu-id="c7164-119">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7164-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7164-120">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c7164-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7164-121">**Biblioteca:** usado como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="c7164-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7164-122">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7164-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7164-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c7164-123">See Also</span></span>  
 [<span data-ttu-id="c7164-124">Estruturas de metadados</span><span class="sxs-lookup"><span data-stu-id="c7164-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="c7164-125">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c7164-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)