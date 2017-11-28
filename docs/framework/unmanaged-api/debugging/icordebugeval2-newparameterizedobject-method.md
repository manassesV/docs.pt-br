---
title: "Método ICorDebugEval2::NewParameterizedObject"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29b2470f50e96307ad91428fe1c712e7340baa32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="d9bdd-102">Método ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="d9bdd-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="d9bdd-103">Cria um novo objeto de tipo parametrizado e chama o método de construtor do objeto.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9bdd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d9bdd-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9bdd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d9bdd-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="d9bdd-106">[in] Um ponteiro para um objeto ICorDebugFunction que representa o construtor do objeto a ser instanciado.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="d9bdd-107">[in] O número de argumentos de tipo passado.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="d9bdd-108">[in] Uma matriz de ponteiros, cada um deles aponta para um objeto ICorDebugType que representa um argumento de tipo para o objeto que está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="d9bdd-109">[in] O número de argumentos passados para o construtor.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="d9bdd-110">[in] Uma matriz de ponteiros, cada um deles aponta para um objeto ICorDebugValue que representa um valor de argumento que é passado para o construtor.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9bdd-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="d9bdd-111">Remarks</span></span>  
 <span data-ttu-id="d9bdd-112">O construtor do objeto pode levar <xref:System.Type> parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9bdd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9bdd-113">Requirements</span></span>  
 <span data-ttu-id="d9bdd-114">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9bdd-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9bdd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9bdd-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9bdd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9bdd-117">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9bdd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>