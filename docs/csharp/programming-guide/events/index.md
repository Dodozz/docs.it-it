---
title: Eventi (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 4031ff08bee945f019974ad590e9b3df6d9c263c
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086232"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="f7ba5-102">Eventi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f7ba5-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="f7ba5-103">Tramite gli eventi, una [classe](../../../csharp/language-reference/keywords/class.md) o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="f7ba5-104">La classe che invia (o *genera*) l'evento è chiamata *autore* e le classi che ricevono (o *gestiscono*) l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="f7ba5-105">In un'applicazione C# Web o Windows Form tipica si sottoscrivono eventi generati da controlli quali pulsanti e caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="f7ba5-106">È possibile usare l'ambiente di sviluppo integrato (IDE) di Visual C# per cercare gli eventi pubblicati da un controllo e selezionare quelli che si vuole gestire.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="f7ba5-107">L'IDE aggiunge automaticamente un metodo vuoto del gestore eventi e il codice per sottoscrivere l'evento.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="f7ba5-108">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="f7ba5-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="f7ba5-109">Cenni preliminari sugli eventi</span><span class="sxs-lookup"><span data-stu-id="f7ba5-109">Events Overview</span></span>  
 <span data-ttu-id="f7ba5-110">Di seguito sono riportate le proprietà degli eventi:</span><span class="sxs-lookup"><span data-stu-id="f7ba5-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="f7ba5-111">L'autore determina quando viene generato un evento. I sottoscrittori determinano quale azione viene eseguita in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="f7ba5-112">Un evento può avere più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="f7ba5-113">Un sottoscrittore può gestire più eventi da più autori.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="f7ba5-114">Gli eventi che non hanno sottoscrittore non vengono mai generati.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="f7ba5-115">Gli eventi vengono in genere usati per segnalare azioni dell'utente, ad esempio la scelta di un pulsante o di una voce di menu nell'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="f7ba5-116">Quando un evento ha più sottoscrittori, i gestori eventi vengono richiamati in modo sincrono al momento della generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f7ba5-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="f7ba5-117">Per richiamare gli eventi in modo asincrono, vedere [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="f7ba5-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="f7ba5-118">Nella libreria di classi di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli eventi sono basati sul delegato <xref:System.EventHandler> e sulla classe di base <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="f7ba5-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f7ba5-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f7ba5-119">Related Sections</span></span>  
 <span data-ttu-id="f7ba5-120">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="f7ba5-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f7ba5-121">Procedura: Eseguire e annullare la sottoscrizione a eventi</span><span class="sxs-lookup"><span data-stu-id="f7ba5-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="f7ba5-122">Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7ba5-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="f7ba5-123">Procedura: Generare eventi di classe base nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="f7ba5-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="f7ba5-124">Procedura: Implementare eventi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="f7ba5-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="f7ba5-125">Procedura: Usare un dizionario per archiviare istanze di evento</span><span class="sxs-lookup"><span data-stu-id="f7ba5-125">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="f7ba5-126">Procedura: Implementare funzioni di accesso a eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="f7ba5-126">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f7ba5-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f7ba5-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="f7ba5-128">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="f7ba5-128">Featured Book Chapters</span></span>  
 <span data-ttu-id="f7ba5-129">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="f7ba5-129">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="f7ba5-130">[Delegati ed eventi](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="f7ba5-130">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ba5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7ba5-131">See Also</span></span>

- <xref:System.EventHandler>  
- [<span data-ttu-id="f7ba5-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f7ba5-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f7ba5-133">Delegati</span><span class="sxs-lookup"><span data-stu-id="f7ba5-133">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="f7ba5-134">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f7ba5-134">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
