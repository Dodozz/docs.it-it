---
title: Enumerazione CorOpenFlags
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55934ef08b10764bb705d7c166621ec7cfcadd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992680"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="aadc9-102">Enumerazione CorOpenFlags</span><span class="sxs-lookup"><span data-stu-id="aadc9-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="aadc9-103">Contiene valori di flag che controllano il comportamento dei metadati all'apertura di file manifesto.</span><span class="sxs-lookup"><span data-stu-id="aadc9-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aadc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aadc9-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="aadc9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="aadc9-105">Members</span></span>  
  
|<span data-ttu-id="aadc9-106">Member</span><span class="sxs-lookup"><span data-stu-id="aadc9-106">Member</span></span>|<span data-ttu-id="aadc9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aadc9-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="aadc9-108">Indica che il file deve essere aperto in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="aadc9-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="aadc9-109">Indica che il file deve essere aperto in scrittura.</span><span class="sxs-lookup"><span data-stu-id="aadc9-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="aadc9-110">Se si usa il flag `ofWrite` quando si apre un file con estensione winmd, è anche necessario passare il flag `ofNoTransform`.</span><span class="sxs-lookup"><span data-stu-id="aadc9-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="aadc9-111">Maschera per la lettura e la scrittura.</span><span class="sxs-lookup"><span data-stu-id="aadc9-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="aadc9-112">Indica che il file deve essere letto in memoria.</span><span class="sxs-lookup"><span data-stu-id="aadc9-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="aadc9-113">I metadati devono mantenere la propria copia.</span><span class="sxs-lookup"><span data-stu-id="aadc9-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="aadc9-114">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="aadc9-114">Obsolete.</span></span> <span data-ttu-id="aadc9-115">Questo flag viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="aadc9-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="aadc9-116">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="aadc9-116">Obsolete.</span></span> <span data-ttu-id="aadc9-117">Questo flag viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="aadc9-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="aadc9-118">Indica che il file deve essere aperto per la lettura e che una chiamata a `QueryInterface` per un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) non può essere effettuata.</span><span class="sxs-lookup"><span data-stu-id="aadc9-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="aadc9-119">Indica che la memoria allocata tramite una chiamata a [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) e verrà liberata dai metadati.</span><span class="sxs-lookup"><span data-stu-id="aadc9-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="aadc9-120">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="aadc9-120">Obsolete.</span></span> <span data-ttu-id="aadc9-121">Questo flag viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="aadc9-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="aadc9-122">Indica che le trasformazioni automatiche dei file con estensione winmd devono essere disabilitate.</span><span class="sxs-lookup"><span data-stu-id="aadc9-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="aadc9-123">In altre parole, la proiezione di un tipo di Windows Runtime in un tipo di .NET Framework deve essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="aadc9-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="aadc9-124">Per altre informazioni, vedere [Windows Runtime e CLR - sotto controllo con .NET e Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span><span class="sxs-lookup"><span data-stu-id="aadc9-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="aadc9-125">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="aadc9-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="aadc9-126">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="aadc9-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="aadc9-127">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="aadc9-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aadc9-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aadc9-128">Requirements</span></span>  
 <span data-ttu-id="aadc9-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aadc9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aadc9-130">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="aadc9-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="aadc9-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aadc9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadc9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aadc9-132">See also</span></span>

- [<span data-ttu-id="aadc9-133">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="aadc9-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
