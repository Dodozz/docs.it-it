---
title: Funzione StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d8013d43dc14807804502e4a0820a2928f917e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499238"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="9665a-102">Funzione StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="9665a-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="9665a-103">Crea un token con nome sicuro dal file di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="9665a-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="9665a-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="9665a-104">This function has been deprecated.</span></span> <span data-ttu-id="9665a-105">Usare la [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="9665a-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9665a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9665a-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9665a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9665a-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9665a-108">[in] Il percorso del file eseguibile portabile (PE) per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9665a-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="9665a-109">[out] Il token restituito con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9665a-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="9665a-110">[out] Le dimensioni, in byte, del token con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9665a-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9665a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9665a-111">Return Value</span></span>  
 <span data-ttu-id="9665a-112">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9665a-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9665a-113">Note</span><span class="sxs-lookup"><span data-stu-id="9665a-113">Remarks</span></span>  
 <span data-ttu-id="9665a-114">Un token con nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="9665a-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="9665a-115">Il token è un hash a 64 bit che viene creato dalla chiave pubblica usata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9665a-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="9665a-116">Il token fa parte del nome sicuro dell'assembly e può essere letti dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9665a-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="9665a-117">Dopo aver creato il token, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="9665a-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="9665a-118">Se il `StrongNameTokenFromAssembly` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="9665a-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9665a-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9665a-119">Requirements</span></span>  
 <span data-ttu-id="9665a-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9665a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9665a-121">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9665a-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9665a-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9665a-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="9665a-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9665a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9665a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9665a-124">See also</span></span>
- [<span data-ttu-id="9665a-125">Metodo StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="9665a-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="9665a-126">Metodo StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="9665a-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="9665a-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9665a-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
