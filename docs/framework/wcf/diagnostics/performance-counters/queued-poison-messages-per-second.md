---
title: Messaggi non elaborabili in coda al secondo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d4c921b105dfd1c1a364d2c86f54ab920078dd4a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916149"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="9b534-102">Messaggi non elaborabili in coda al secondo</span><span class="sxs-lookup"><span data-stu-id="9b534-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="9b534-103">Nome contatore: Messaggi non elaborabili in coda al secondo.</span><span class="sxs-lookup"><span data-stu-id="9b534-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9b534-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b534-104">Description</span></span>  
 <span data-ttu-id="9b534-105">Numero di messaggi al secondo contrassegnati come non elaborabili dal trasporto in coda in questo servizio.</span><span class="sxs-lookup"><span data-stu-id="9b534-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="9b534-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="9b534-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9b534-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9b534-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
