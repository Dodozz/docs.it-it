---
title: Chiamate non riuscite al secondo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: ff9320b0990a0543bbb1da553d040ff5a4b4fed9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178620"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="283a0-102">Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="283a0-102">Calls Failed Per Second</span></span>
<span data-ttu-id="283a0-103">Nome contatore: Chiamate non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="283a0-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="283a0-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="283a0-104">Description</span></span>  
 <span data-ttu-id="283a0-105">Numero di chiamate al secondo con eccezioni non gestite presenti in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="283a0-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="283a0-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="283a0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="283a0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="283a0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="283a0-108">Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questa operazione.</span><span class="sxs-lookup"><span data-stu-id="283a0-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="283a0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="283a0-109">See also</span></span>

- [<span data-ttu-id="283a0-110">Specifica e gestione di errori in contratti e servizi</span><span class="sxs-lookup"><span data-stu-id="283a0-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
