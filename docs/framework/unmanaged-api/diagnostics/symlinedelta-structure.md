---
title: Struttura SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159484"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="bfe33-102">Struttura SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="bfe33-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="bfe33-103">Fornisce informazioni sul gestore di simboli sui metodi che sono state spostate in seguito a modifiche.</span><span class="sxs-lookup"><span data-stu-id="bfe33-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfe33-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="bfe33-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bfe33-105">Members</span></span>  
  
|<span data-ttu-id="bfe33-106">Member</span><span class="sxs-lookup"><span data-stu-id="bfe33-106">Member</span></span>|<span data-ttu-id="bfe33-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfe33-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="bfe33-108">Token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="bfe33-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="bfe33-109">Il numero di righe che è stato spostato il metodo.</span><span class="sxs-lookup"><span data-stu-id="bfe33-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfe33-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfe33-110">Requirements</span></span>  
 <span data-ttu-id="bfe33-111">**Intestazione:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="bfe33-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe33-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe33-112">See also</span></span>

- [<span data-ttu-id="bfe33-113">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="bfe33-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
