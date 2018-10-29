---
title: 'Procedura: implementare funzioni di accesso a eventi personalizzati (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 759a7a4518a371449723a23669816bbc0fbc0dee
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836709"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="e7fe6-102">Procedura: implementare funzioni di accesso a eventi personalizzati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e7fe6-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="e7fe6-103">Un evento è un tipo speciale di delegato multicast che può essere richiamato solo dall'interno della classe in cui è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="e7fe6-104">Il codice client sottoscrive l'evento fornendo un riferimento a un metodo che deve essere richiamato quando l'evento viene generato.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="e7fe6-105">Questi metodi vengono aggiunti all'elenco di chiamate del delegato tramite funzioni di accesso agli eventi, che sono simili alle funzioni di accesso alle proprietà, ad eccezione del fatto che sono denominate `add` e `remove`.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="e7fe6-106">Nella maggior parte dei casi, non è necessario fornire funzioni di accesso agli eventi personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="e7fe6-107">Se nel codice non vengono fornite funzioni di accesso agli eventi personalizzate, il compilatore le aggiunge automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="e7fe6-108">In alcuni casi tuttavia può essere necessario fornire un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="e7fe6-109">Uno di questi casi è illustrato nell'argomento [Procedura: Implementare gli eventi di interfaccia ](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="e7fe6-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7fe6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7fe6-110">Example</span></span>  
 <span data-ttu-id="e7fe6-111">L'esempio seguente mostra come implementare le funzioni di accesso agli eventi add e remove personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="e7fe6-112">Anche se è possibile sostituire qualsiasi parte di codice nelle funzioni di accesso, si consiglia di bloccare l'evento prima di aggiungere o rimuovere un nuovo metodo del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e7fe6-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](codesnippet/CSharp/how-to-implement-interface-events_1.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="e7fe6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7fe6-113">See Also</span></span>

- [<span data-ttu-id="e7fe6-114">Eventi</span><span class="sxs-lookup"><span data-stu-id="e7fe6-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="e7fe6-115">event</span><span class="sxs-lookup"><span data-stu-id="e7fe6-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)