---
title: Enumerazione HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfb1cff3e95c5ff86d22913745b7d14982766b48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175227"
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="a9c64-102">Enumerazione HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="a9c64-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="a9c64-103">Contiene valori che specificano il tipo di host che esegue un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a9c64-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c64-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9c64-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a9c64-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a9c64-105">Members</span></span>  
  
|<span data-ttu-id="a9c64-106">Member</span><span class="sxs-lookup"><span data-stu-id="a9c64-106">Member</span></span>|<span data-ttu-id="a9c64-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9c64-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="a9c64-108">Avviare l'applicazione da AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="a9c64-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="a9c64-109">Utilizzare questo valore per le applicazioni parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="a9c64-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="a9c64-110">Avviare l'applicazione direttamente.</span><span class="sxs-lookup"><span data-stu-id="a9c64-110">Launch the application directly.</span></span> <span data-ttu-id="a9c64-111">Vale a dire, avviare l'applicazione da un proprio file .exe.</span><span class="sxs-lookup"><span data-stu-id="a9c64-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="a9c64-112">Utilizzare questo valore per le applicazioni completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="a9c64-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="a9c64-113">Uguale a HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="a9c64-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9c64-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9c64-114">Requirements</span></span>  
 <span data-ttu-id="a9c64-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9c64-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c64-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9c64-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9c64-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9c64-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a9c64-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a9c64-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9c64-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9c64-119">See also</span></span>

- [<span data-ttu-id="a9c64-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="a9c64-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
