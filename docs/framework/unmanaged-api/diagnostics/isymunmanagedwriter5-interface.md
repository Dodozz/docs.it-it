---
title: Interfaccia ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962339"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="ac05a-102">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="ac05a-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="ac05a-103">Interfaccia ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="ac05a-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac05a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac05a-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="ac05a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ac05a-105">Methods</span></span>  
 <span data-ttu-id="ac05a-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="ac05a-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="ac05a-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="ac05a-107">Method</span></span>|<span data-ttu-id="ac05a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac05a-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac05a-109">Metodo CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="ac05a-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="ac05a-110">Chiudere la sezione di dati personalizzati speciali per l'intervallo di origine-token-per informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="ac05a-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="ac05a-111">Dopo la chiusura, è possibile aggiungere alcuna informazione sul mapping di più.</span><span class="sxs-lookup"><span data-stu-id="ac05a-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="ac05a-112">Metodo MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="ac05a-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="ac05a-113">Mappe estendono il token di metadati specificati alla riga di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="ac05a-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="ac05a-114">Deve essere chiamato tra le chiamate a [metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e [metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="ac05a-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="ac05a-115">Metodo OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="ac05a-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="ac05a-116">Aprire una sezione di dati personalizzati speciali per generare informazioni sul mapping dell'intervallo token-to-source in.</span><span class="sxs-lookup"><span data-stu-id="ac05a-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="ac05a-117">Apertura di questa sezione quando un metodo è già aperto, o viceversa, è un errore.</span><span class="sxs-lookup"><span data-stu-id="ac05a-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac05a-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac05a-118">Requirements</span></span>  
 <span data-ttu-id="ac05a-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac05a-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac05a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac05a-120">See also</span></span>

- [<span data-ttu-id="ac05a-121">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ac05a-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ac05a-122">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="ac05a-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
