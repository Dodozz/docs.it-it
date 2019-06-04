---
title: Funzione CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9597b12b0da6df807b2d4eaa42c2035c518b71d9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490634"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="df626-102">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="df626-102">CoInitializeEE Function</span></span>
<span data-ttu-id="df626-103">Garantisce che il motore di esecuzione di common language runtime è caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="df626-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="df626-104">Questa funzione è obsoleta in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="df626-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="df626-105">Usare la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="df626-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df626-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df626-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df626-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="df626-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="df626-108">[in] Uno dei [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="df626-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df626-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="df626-109">Return Value</span></span>  
 <span data-ttu-id="df626-110">Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror. h e i valori nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="df626-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="df626-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="df626-111">Return code</span></span>|<span data-ttu-id="df626-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df626-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="df626-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="df626-113">S_OK</span></span>|<span data-ttu-id="df626-114">Il motore di esecuzione è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="df626-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="df626-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="df626-115">S_FALSE</span></span>|<span data-ttu-id="df626-116">Il motore di esecuzione è già caricato.</span><span class="sxs-lookup"><span data-stu-id="df626-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="df626-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df626-117">E_FAIL</span></span>|<span data-ttu-id="df626-118">Non è stato possibile caricare il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="df626-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df626-119">Note</span><span class="sxs-lookup"><span data-stu-id="df626-119">Remarks</span></span>  
 <span data-ttu-id="df626-120">Questo metodo carica il motore di esecuzione se non è stato caricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="df626-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df626-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df626-121">Requirements</span></span>  
 <span data-ttu-id="df626-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df626-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df626-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="df626-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df626-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="df626-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df626-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df626-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df626-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df626-126">See also</span></span>

- [<span data-ttu-id="df626-127">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="df626-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
