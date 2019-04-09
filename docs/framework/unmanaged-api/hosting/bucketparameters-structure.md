---
title: Struttura BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5998ce684726b2386d8f1e05eb7eaeccf455747c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110456"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="33d11-102">Struttura BucketParameters</span><span class="sxs-lookup"><span data-stu-id="33d11-102">BucketParameters Structure</span></span>
<span data-ttu-id="33d11-103">Archivia il nome del tipo di un evento e i parametri per l'eccezione corrente viene associato all'evento.</span><span class="sxs-lookup"><span data-stu-id="33d11-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33d11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33d11-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="33d11-105">Membri</span><span class="sxs-lookup"><span data-stu-id="33d11-105">Members</span></span>  
  
|<span data-ttu-id="33d11-106">Member</span><span class="sxs-lookup"><span data-stu-id="33d11-106">Member</span></span>|<span data-ttu-id="33d11-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33d11-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|`true`<span data-ttu-id="33d11-108">, se il resto di questa struttura è valido. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="33d11-108">, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="33d11-109">Nome del tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="33d11-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="33d11-110">Matrice di stringhe, ognuna delle quali specifica un parametro per l'eccezione corrente associato all'evento.</span><span class="sxs-lookup"><span data-stu-id="33d11-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33d11-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33d11-111">Requirements</span></span>  
 <span data-ttu-id="33d11-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33d11-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33d11-113">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="33d11-113">**Header:** MSCorEE.idl</span></span>  
  
 **<span data-ttu-id="33d11-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="33d11-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33d11-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33d11-115">See also</span></span>

- [<span data-ttu-id="33d11-116">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="33d11-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
