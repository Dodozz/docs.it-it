---
title: Thread.Suspend, operazioni di Garbage Collection e punti sicuri
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3e44b81b519bcae42c2e69eff46e73b1ae631a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490804"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="1a73d-102">Thread.Suspend, operazioni di Garbage Collection e punti sicuri</span><span class="sxs-lookup"><span data-stu-id="1a73d-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="1a73d-103">Quando si chiama <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> su un thread, nel sistema viene rilevato che è stata richiesta una sospensione di thread, di cui viene consentita l'esecuzione fino al raggiungimento di un punto sicuro, prima di sospendere effettivamente il thread.</span><span class="sxs-lookup"><span data-stu-id="1a73d-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="1a73d-104">Per un thread, un punto sicuro è un punto nell'esecuzione in corrispondenza del quale è possibile eseguire operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1a73d-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="1a73d-105">Dopo aver raggiunto un punto sicuro, il runtime garantisce che il thread sospeso non effettuerà ulteriori avanzamenti nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1a73d-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="1a73d-106">Un thread in esecuzione all'esterno del codice gestito è sempre sicuro per le operazioni di Garbage Collection e l'esecuzione continua finché non tenta di riprendere l'esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1a73d-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a73d-107">Per eseguire un'operazione di Garbage Collection, è necessario che vengano sospesi tutti i thread ad eccezione di quello che esegue la raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a73d-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="1a73d-108">Ogni thread deve essere portato a un punto sicuro prima di poter essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="1a73d-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a73d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a73d-109">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.GC>
- [<span data-ttu-id="1a73d-110">Threading</span><span class="sxs-lookup"><span data-stu-id="1a73d-110">Threading</span></span>](../../../docs/standard/threading/index.md)
- [<span data-ttu-id="1a73d-111">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="1a73d-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
