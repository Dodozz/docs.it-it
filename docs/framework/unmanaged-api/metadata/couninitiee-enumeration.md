---
title: Enumerazione COUNINITIEE
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045058"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="6d80c-102">Enumerazione COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="6d80c-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="6d80c-103">Specifica le costanti usate da [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="6d80c-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d80c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d80c-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="6d80c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6d80c-105">Members</span></span>  
  
|<span data-ttu-id="6d80c-106">Member</span><span class="sxs-lookup"><span data-stu-id="6d80c-106">Member</span></span>|<span data-ttu-id="6d80c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d80c-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="6d80c-108">Indica la modalità di annullamento dell'inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d80c-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="6d80c-109">Indica la modalità di annullamento dell'inizializzazione per lo scaricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="6d80c-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d80c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d80c-110">Requirements</span></span>  
 <span data-ttu-id="6d80c-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d80c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d80c-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6d80c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d80c-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6d80c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d80c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d80c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d80c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d80c-115">See also</span></span>

- [<span data-ttu-id="6d80c-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6d80c-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
