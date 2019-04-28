---
title: Transazioni propagate al secondo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927192"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="bf63d-102">Transazioni propagate al secondo</span><span class="sxs-lookup"><span data-stu-id="bf63d-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="bf63d-103">Nome contatore:  Transazioni propagate al secondo</span><span class="sxs-lookup"><span data-stu-id="bf63d-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf63d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf63d-104">Description</span></span>  
 <span data-ttu-id="bf63d-105">Numero di transazioni propagate a questa operazione in un secondo.</span><span class="sxs-lookup"><span data-stu-id="bf63d-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="bf63d-106">Questo contatore viene incrementato ogni volta che è presente un ID di transazione in un messaggio inviato all'operazione.</span><span class="sxs-lookup"><span data-stu-id="bf63d-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="bf63d-107">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="bf63d-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="bf63d-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="bf63d-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
