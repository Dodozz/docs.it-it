---
title: Messaggi di messaggistica affidabile ignorati al secondo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916032"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="e9fd5-102">Messaggi di messaggistica affidabile ignorati al secondo</span><span class="sxs-lookup"><span data-stu-id="e9fd5-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="e9fd5-103">Nome contatore: Sessioni di messaggistica affidabile eliminati al secondo.</span><span class="sxs-lookup"><span data-stu-id="e9fd5-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e9fd5-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fd5-104">Description</span></span>  
 <span data-ttu-id="e9fd5-105">Numero complessivo di messaggi di messaggistica affidabile rilasciati in questo servizio in un secondo.</span><span class="sxs-lookup"><span data-stu-id="e9fd5-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="e9fd5-106">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="e9fd5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e9fd5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e9fd5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
