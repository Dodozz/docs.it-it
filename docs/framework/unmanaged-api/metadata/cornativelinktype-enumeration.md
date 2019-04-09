---
title: Enumerazione CorNativeLinkType
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170072"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="8a898-102">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="8a898-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="8a898-103">Fornisce valori che indicano il tipo collegato nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="8a898-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a898-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a898-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="8a898-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8a898-105">Members</span></span>  
  
|<span data-ttu-id="8a898-106">Member</span><span class="sxs-lookup"><span data-stu-id="8a898-106">Member</span></span>|<span data-ttu-id="8a898-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a898-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="8a898-108">Indica che nessuna delle parole chiave sono stata specificata.</span><span class="sxs-lookup"><span data-stu-id="8a898-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="8a898-109">Indica che è specificata una parola chiave ANSI.</span><span class="sxs-lookup"><span data-stu-id="8a898-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="8a898-110">Indica che è specificata una parola chiave Unicode</span><span class="sxs-lookup"><span data-stu-id="8a898-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="8a898-111">Indica che è specificata una parola chiave auto.</span><span class="sxs-lookup"><span data-stu-id="8a898-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="8a898-112">Indica che è specificata una parola chiave OLE.</span><span class="sxs-lookup"><span data-stu-id="8a898-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="8a898-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="8a898-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a898-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a898-114">Requirements</span></span>  
 <span data-ttu-id="8a898-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a898-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a898-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8a898-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a898-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8a898-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8a898-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8a898-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a898-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a898-119">See also</span></span>

- [<span data-ttu-id="8a898-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="8a898-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
