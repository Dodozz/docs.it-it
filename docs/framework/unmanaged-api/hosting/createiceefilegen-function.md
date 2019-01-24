---
title: Funzione CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e367ab3c966cea2d875b1de5b4244db5c4b813e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702223"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="7da19-102">Funzione CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="7da19-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="7da19-103">Crea un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="7da19-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="7da19-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7da19-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da19-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7da19-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7da19-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7da19-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="7da19-107">[out] Un puntatore all'indirizzo di un nuovo `ICeeFileGen` oggetto.</span><span class="sxs-lookup"><span data-stu-id="7da19-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7da19-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7da19-108">Return Value</span></span>  
 <span data-ttu-id="7da19-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="7da19-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7da19-110">Note</span><span class="sxs-lookup"><span data-stu-id="7da19-110">Remarks</span></span>  
 <span data-ttu-id="7da19-111">Il `ICeeFileGen` oggetto viene usato per creare common language runtime (CLR) i file eseguibili portabili (PE).</span><span class="sxs-lookup"><span data-stu-id="7da19-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="7da19-112">Chiamare il [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) funzione eliminare definitivamente il `ICeeFileGen` al termine dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7da19-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7da19-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7da19-113">Requirements</span></span>  
 <span data-ttu-id="7da19-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da19-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da19-115">**Intestazione:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="7da19-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="7da19-116">**Libreria:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="7da19-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="7da19-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da19-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da19-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7da19-118">See also</span></span>
- [<span data-ttu-id="7da19-119">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="7da19-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
