---
title: Funzione LoadFromHistory (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 155b83b8b904350bd6faf73ea21d1db4f83085b7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376130"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a466c-102">Funzione LoadFromHistory (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="a466c-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a466c-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="a466c-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a466c-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="a466c-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a466c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a466c-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a466c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a466c-106">Parameters</span></span>  
 <span data-ttu-id="a466c-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="a466c-107">pHistoryStream</span></span>  
 <span data-ttu-id="a466c-108">Puntatore a un flusso di informazioni di cronologia.</span><span class="sxs-lookup"><span data-stu-id="a466c-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="a466c-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="a466c-109">pBindCtx</span></span>  
 <span data-ttu-id="a466c-110">Puntatore a un contesto di associazione.</span><span class="sxs-lookup"><span data-stu-id="a466c-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a466c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a466c-111">Requirements</span></span>  
 <span data-ttu-id="a466c-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a466c-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a466c-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="a466c-113">**DLL:**</span></span>  
  
 <span data-ttu-id="a466c-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a466c-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a466c-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a466c-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a466c-116">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a466c-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a466c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a466c-117">See also</span></span>
- [<span data-ttu-id="a466c-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="a466c-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
