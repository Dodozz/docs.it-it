---
title: Funzione CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17143a6cac750e20c1e6ebb7874e10fb64e37edc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587489"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="4178a-102">Funzione CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="4178a-102">CorExitProcess Function</span></span>
<span data-ttu-id="4178a-103">Arresta il processo non gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="4178a-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="4178a-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4178a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="4178a-105">Usare la [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="4178a-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4178a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4178a-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4178a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4178a-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="4178a-108">Valore intero che specifica il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="4178a-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4178a-109">Note</span><span class="sxs-lookup"><span data-stu-id="4178a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4178a-110">Inizia con la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` chiude ogni runtime avviato il processo, non solo il runtime a cui sono state associate le API legacy.</span><span class="sxs-lookup"><span data-stu-id="4178a-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4178a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4178a-111">Requirements</span></span>  
 <span data-ttu-id="4178a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4178a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4178a-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4178a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4178a-114">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4178a-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4178a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4178a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4178a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4178a-116">See also</span></span>
- [<span data-ttu-id="4178a-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="4178a-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
