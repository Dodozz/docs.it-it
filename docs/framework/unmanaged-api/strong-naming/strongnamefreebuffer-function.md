---
title: Funzione StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bfc6491a1d18c81a44a7d9c5084f744c9b76281
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072577"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="4cf97-102">Funzione StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4cf97-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="4cf97-103">Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="4cf97-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="4cf97-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="4cf97-104">This function has been deprecated.</span></span> <span data-ttu-id="4cf97-105">Usare la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="4cf97-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf97-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cf97-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cf97-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cf97-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="4cf97-108">[in] Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="4cf97-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf97-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cf97-109">Requirements</span></span>  
 <span data-ttu-id="4cf97-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cf97-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cf97-111">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4cf97-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4cf97-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4cf97-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="4cf97-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4cf97-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4cf97-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cf97-114">See also</span></span>

- [<span data-ttu-id="4cf97-115">Metodo StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4cf97-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="4cf97-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4cf97-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
