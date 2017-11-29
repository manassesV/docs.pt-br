---
title: "Função CloneEnumWbemClassObject (referência de API não gerenciada)"
description: "A função CloneEnumWbemClassObject faz uma cópia lógica de um enumerador."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CloneEnumWbemClassObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CloneEnumWbemClassObject
helpviewer_keywords: CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a4103a0103a334a0e5eace32d8fcf1b365917b8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="d98f8-103">Função CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="d98f8-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="d98f8-104">Faz uma cópia lógica de um enumerador, mantendo sua posição atual em uma enumeração.</span><span class="sxs-lookup"><span data-stu-id="d98f8-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d98f8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d98f8-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d98f8-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d98f8-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="d98f8-107">[out] Recebe um ponteiro para um novo [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="d98f8-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="d98f8-108">[in] O nível de autorização.</span><span class="sxs-lookup"><span data-stu-id="d98f8-108">[in] The authorization level.</span></span>

<span data-ttu-id="d98f8-109">`impLevel`[in] O nível de representação.</span><span class="sxs-lookup"><span data-stu-id="d98f8-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="d98f8-110">[out] Um ponteiro para o [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instância a ser clonado.</span><span class="sxs-lookup"><span data-stu-id="d98f8-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="d98f8-111">[in] O nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="d98f8-111">[in] The user name.</span></span> <span data-ttu-id="d98f8-112">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d98f8-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="d98f8-113">[in] A senha.</span><span class="sxs-lookup"><span data-stu-id="d98f8-113">[in] The password.</span></span> <span data-ttu-id="d98f8-114">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d98f8-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="d98f8-115">[in] O nome de domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="d98f8-115">[in] The domain name of the user.</span></span> <span data-ttu-id="d98f8-116">Consulte o [ConnectServerWmi](connectserverwmi.md) função para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d98f8-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="d98f8-117">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="d98f8-117">Return value</span></span>

<span data-ttu-id="d98f8-118">Os seguintes valores retornados por essa função são definidos no *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="d98f8-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d98f8-119">Constante</span><span class="sxs-lookup"><span data-stu-id="d98f8-119">Constant</span></span>  |<span data-ttu-id="d98f8-120">Valor</span><span class="sxs-lookup"><span data-stu-id="d98f8-120">Value</span></span>  |<span data-ttu-id="d98f8-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="d98f8-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="d98f8-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d98f8-122">0x80041001</span></span> | <span data-ttu-id="d98f8-123">Houve uma falha geral.</span><span class="sxs-lookup"><span data-stu-id="d98f8-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d98f8-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d98f8-124">0x80041008</span></span> | <span data-ttu-id="d98f8-125">Um parâmetro é inválido.</span><span class="sxs-lookup"><span data-stu-id="d98f8-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d98f8-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d98f8-126">0x80041006</span></span> | <span data-ttu-id="d98f8-127">Não há memória suficiente está disponível concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="d98f8-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="d98f8-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="d98f8-128">0x80041015</span></span> | <span data-ttu-id="d98f8-129">O link RPC (chamada) de procedimento remoto entre o processo atual e a WMI falhou.</span><span class="sxs-lookup"><span data-stu-id="d98f8-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d98f8-130">0</span><span class="sxs-lookup"><span data-stu-id="d98f8-130">0</span></span> | <span data-ttu-id="d98f8-131">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="d98f8-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d98f8-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="d98f8-132">Remarks</span></span>

<span data-ttu-id="d98f8-133">Essa função encapsula uma chamada para o [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="d98f8-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="d98f8-134">Esse método torna apenas uma cópia de "melhor esforço".</span><span class="sxs-lookup"><span data-stu-id="d98f8-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="d98f8-135">Devido à natureza dinâmica dos muitos objetos CIM, é possível que o novo enumerador não enumerar o mesmo conjunto de objetos que o enumerador de fonte.</span><span class="sxs-lookup"><span data-stu-id="d98f8-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="d98f8-136">Se a chamada de função falhar, você pode obter informações adicionais sobre erros chamando o [GetErrorInfo](geterrorinfo.md) função.</span><span class="sxs-lookup"><span data-stu-id="d98f8-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="d98f8-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d98f8-137">Example</span></span>

<span data-ttu-id="d98f8-138">Para obter um exemplo, consulte o [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="d98f8-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d98f8-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d98f8-139">Requirements</span></span>  
 <span data-ttu-id="d98f8-140">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d98f8-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d98f8-141">**Cabeçalho:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d98f8-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d98f8-142">**Versões do .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d98f8-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d98f8-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d98f8-143">See also</span></span>  
[<span data-ttu-id="d98f8-144">WMI e contadores de desempenho (referência de API não gerenciada)</span><span class="sxs-lookup"><span data-stu-id="d98f8-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)