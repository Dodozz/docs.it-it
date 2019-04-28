---
title: Funzione CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7820b33dcfacae5ede5235607e40d95940fc474
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771904"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="db9a8-102">Funzione CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="db9a8-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="db9a8-103">Ottiene un puntatore a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) istanza che rappresenta un elenco di riferimenti di un'applicazione per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="db9a8-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db9a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db9a8-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="db9a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db9a8-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="db9a8-106">[out] L'oggetto restituito `IInstallReferenceEnum` puntatore.</span><span class="sxs-lookup"><span data-stu-id="db9a8-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="db9a8-107">[in] Il [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) che identifica l'assembly per cui si desidera enumerare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="db9a8-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="db9a8-108">[in] Flag che influenzano il comportamento dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="db9a8-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="db9a8-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="db9a8-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="db9a8-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="db9a8-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db9a8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db9a8-111">Requirements</span></span>  
 <span data-ttu-id="db9a8-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db9a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db9a8-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="db9a8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="db9a8-114">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="db9a8-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="db9a8-115">Usare Fusion. dll invece di Mscorwks. dll per verificare che da usare come destinazione la versione corretta di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db9a8-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="db9a8-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db9a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db9a8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db9a8-117">See also</span></span>

- [<span data-ttu-id="db9a8-118">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="db9a8-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [<span data-ttu-id="db9a8-119">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="db9a8-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="db9a8-120">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="db9a8-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
