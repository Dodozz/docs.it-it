---
title: Interfaccia IXCLRDataMethodInstance
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 03be79e6300afa6d25a005b0a21b8c2bf15d27be
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202275"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="73d8d-102">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="73d8d-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="73d8d-103">Fornisce metodi per la ricerca delle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="73d8d-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="73d8d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="73d8d-104">Methods</span></span>

| <span data-ttu-id="73d8d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="73d8d-105">Method</span></span>                                                                                                                  | <span data-ttu-id="73d8d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73d8d-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="73d8d-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="73d8d-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="73d8d-108">Ottiene il livello di integrità per le informazioni di mapping di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="73d8d-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="73d8d-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="73d8d-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="73d8d-110">Ottiene l'indirizzo del punto di ingresso più significativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.</span><span class="sxs-lookup"><span data-stu-id="73d8d-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |


## <a name="remarks"></a><span data-ttu-id="73d8d-111">Note</span><span class="sxs-lookup"><span data-stu-id="73d8d-111">Remarks</span></span>

<span data-ttu-id="73d8d-112">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="73d8d-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="73d8d-113">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="73d8d-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="73d8d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73d8d-114">Requirements</span></span>

<span data-ttu-id="73d8d-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73d8d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="73d8d-116">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="73d8d-116">**Header:** None</span></span>  
<span data-ttu-id="73d8d-117">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="73d8d-117">**Library:** None</span></span>  
<span data-ttu-id="73d8d-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="73d8d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="73d8d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73d8d-119">See also</span></span>

- [<span data-ttu-id="73d8d-120">Debug</span><span class="sxs-lookup"><span data-stu-id="73d8d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="73d8d-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="73d8d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
