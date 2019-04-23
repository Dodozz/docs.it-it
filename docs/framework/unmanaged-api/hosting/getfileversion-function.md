---
title: Funzione GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d25a3ccdd66ff7acb70f1f5e6c60157b53cc97c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123730"
---
# <a name="getfileversion-function"></a><span data-ttu-id="82f24-102">Funzione GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="82f24-102">GetFileVersion Function</span></span>
<span data-ttu-id="82f24-103">Ottiene informazioni sulla versione di common language runtime (CLR) del file specificato, utilizzando il buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="82f24-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="82f24-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82f24-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f24-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82f24-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82f24-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="82f24-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="82f24-107">[in] Il percorso del file da esaminare.</span><span class="sxs-lookup"><span data-stu-id="82f24-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="82f24-108">[in, out] Il buffer allocato per le informazioni sulla versione che viene restituiti.</span><span class="sxs-lookup"><span data-stu-id="82f24-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="82f24-109">[in] Le dimensioni, in caratteri "wide", di `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82f24-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="82f24-110">[out] Le dimensioni, in byte, del valore restituito `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="82f24-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f24-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82f24-111">Requirements</span></span>  
 <span data-ttu-id="82f24-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82f24-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f24-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82f24-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82f24-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82f24-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82f24-115">See also</span></span>

- [<span data-ttu-id="82f24-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="82f24-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
