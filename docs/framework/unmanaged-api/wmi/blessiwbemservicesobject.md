---
title: "Função BlessIWbemServicesObject (referência de API não gerenciada)"
description: "A função BlessIWbemServicesObject indica se as credenciais do usuário permitirem o acesso a um objeto IWbemServices"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BlessIWbemServicesObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BlessIWbemServicesObject
helpviewer_keywords: BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebba6df29b814315180e9c8e936e5e1ad175ecf8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="fcd1d-103">Função BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="fcd1d-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="fcd1d-104">Indica se as credenciais do usuário permitirem o acesso a determinado [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-104">Indicates whether the user credentials permit access to a specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fcd1d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fcd1d-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="fcd1d-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fcd1d-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="fcd1d-107">[in] Um ponteiro para um objeto de serviço do WMI.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-107">[in] A pointer to a WMI service object.</span></span>

`strUser`  
<span data-ttu-id="fcd1d-108">[in] O nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="fcd1d-109">[in] A senha associada com `strUser`.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="fcd1d-110">`strAuthority`[in] O nome de domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="fcd1d-111">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="fcd1d-112">`impLevel`[in] O nível de representação.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="fcd1d-113">`authnLevel`[in] O nível de autorização.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="fcd1d-114">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="fcd1d-114">Return value</span></span>

<span data-ttu-id="fcd1d-115">Os seguintes valores retornados por essa função são definidos no *Winerror. H* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="fcd1d-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fcd1d-116">Constante</span><span class="sxs-lookup"><span data-stu-id="fcd1d-116">Constant</span></span>  |<span data-ttu-id="fcd1d-117">Valor</span><span class="sxs-lookup"><span data-stu-id="fcd1d-117">Value</span></span>  |<span data-ttu-id="fcd1d-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcd1d-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="fcd1d-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="fcd1d-119">0x80070057</span></span> | <span data-ttu-id="fcd1d-120">Um ou mais argumentos são inválidos.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="fcd1d-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="fcd1d-121">0x80004003</span></span> | <span data-ttu-id="fcd1d-122">`pIWbemServices` é `null`.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="fcd1d-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="fcd1d-123">0x80000008</span></span> | <span data-ttu-id="fcd1d-124">Ocorreu um erro não especificado.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="fcd1d-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="fcd1d-125">0x80000002</span></span> | <span data-ttu-id="fcd1d-126">Memória disponível é insuficiente para executar a operação.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="fcd1d-127">0</span><span class="sxs-lookup"><span data-stu-id="fcd1d-127">0</span></span> | <span data-ttu-id="fcd1d-128">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="fcd1d-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="fcd1d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcd1d-129">Requirements</span></span>  
 <span data-ttu-id="fcd1d-130">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcd1d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd1d-131">**Cabeçalho:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fcd1d-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fcd1d-132">**Versões do .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd1d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd1d-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fcd1d-133">See also</span></span>  
[<span data-ttu-id="fcd1d-134">WMI e contadores de desempenho (referência de API não gerenciada)</span><span class="sxs-lookup"><span data-stu-id="fcd1d-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)