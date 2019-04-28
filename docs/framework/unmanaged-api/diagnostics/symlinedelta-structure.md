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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914641"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="18107-102">Struttura SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="18107-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="18107-103">Fornisce informazioni sul gestore di simboli sui metodi che sono state spostate in seguito a modifiche.</span><span class="sxs-lookup"><span data-stu-id="18107-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18107-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18107-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="18107-105">Membri</span><span class="sxs-lookup"><span data-stu-id="18107-105">Members</span></span>  
  
|<span data-ttu-id="18107-106">Member</span><span class="sxs-lookup"><span data-stu-id="18107-106">Member</span></span>|<span data-ttu-id="18107-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18107-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="18107-108">Token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="18107-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="18107-109">Il numero di righe che è stato spostato il metodo.</span><span class="sxs-lookup"><span data-stu-id="18107-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18107-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18107-110">Requirements</span></span>  
 <span data-ttu-id="18107-111">**Intestazione:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="18107-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18107-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18107-112">See also</span></span>

- [<span data-ttu-id="18107-113">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="18107-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
