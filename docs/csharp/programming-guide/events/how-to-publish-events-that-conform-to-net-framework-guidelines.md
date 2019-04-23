---
title: 'Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 3ea5f5fb3b94c3edfd129a08a57c4c584b1412aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306586"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="eef22-102">Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="eef22-102">How to: Publish Events that Conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="eef22-103">La procedura seguente illustra come aggiungere a classi e struct gli eventi che seguono il modello standard [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eef22-103">The following procedure demonstrates how to add events that follow the standard [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pattern to your classes and structs.</span></span> <span data-ttu-id="eef22-104">Tutti gli eventi della libreria di classi [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] si basano sul delegato <xref:System.EventHandler>, che viene definito come segue:</span><span class="sxs-lookup"><span data-stu-id="eef22-104">All events in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  <span data-ttu-id="eef22-105">[!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] introduce una versione generica di questo delegato, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="eef22-105">The [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="eef22-106">Negli esempi seguenti viene illustrato l'uso di entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="eef22-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="eef22-107">Anche se gli eventi nelle classi che vengono definite possono essere basati su qualsiasi tipo di delegato valido, inclusi i delegati che restituiscono un valore, è in genere consigliabile basare gli eventi sullo schema [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] usando <xref:System.EventHandler>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="eef22-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="eef22-108">Per pubblicare eventi basati sul modello EventHandler</span><span class="sxs-lookup"><span data-stu-id="eef22-108">To publish events based on the EventHandler pattern</span></span>  
  
1. <span data-ttu-id="eef22-109">Ignorare questo passaggio e andare al passaggio 3a se non è necessario inviare i dati personalizzati con l'evento. Dichiarare la classe per i dati personalizzati in un ambito che sia visibile sia per la classe dell'editore che per quella del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="eef22-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="eef22-110">Aggiungere i membri necessari per contenere i dati di evento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="eef22-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="eef22-111">In questo esempio viene restituita una semplice stringa.</span><span class="sxs-lookup"><span data-stu-id="eef22-111">In this example, a simple string is returned.</span></span>  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }   
    }  
    ```  
  
2. <span data-ttu-id="eef22-112">Ignorare questo passaggio se si sta usando la versione generica di <xref:System.EventHandler%601>. Dichiarare un delegato nella classe di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="eef22-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="eef22-113">Assegnargli un nome che termini con *EventHandler*.</span><span class="sxs-lookup"><span data-stu-id="eef22-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="eef22-114">Il secondo parametro specifica il tipo EventArgs personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eef22-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3. <span data-ttu-id="eef22-115">Dichiarare l'evento nella classe di pubblicazione usando uno dei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="eef22-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1.  <span data-ttu-id="eef22-116">Se non si ha una classe EventArgs personalizzata, il tipo di evento sarà il delegato EventHandler non generico.</span><span class="sxs-lookup"><span data-stu-id="eef22-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="eef22-117">Non è necessario dichiarare il delegato perché è già dichiarato nello spazio dei nomi <xref:System>, incluso quando si crea il progetto C#.</span><span class="sxs-lookup"><span data-stu-id="eef22-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="eef22-118">Aggiungere il codice seguente alla classe dell'editore.</span><span class="sxs-lookup"><span data-stu-id="eef22-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  <span data-ttu-id="eef22-119">Se si usa la versione non generica di <xref:System.EventHandler> e si ha una classe personalizzata derivata da <xref:System.EventArgs>, dichiarare l'evento all'interno della classe di pubblicazione e usare il delegato del passaggio 2 come tipo.</span><span class="sxs-lookup"><span data-stu-id="eef22-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3.  <span data-ttu-id="eef22-120">Se si usa la versione generica, non è necessario un delegato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eef22-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="eef22-121">Al contrario, nella classe di pubblicazione specificare il tipo di evento come `EventHandler<CustomEventArgs>`, sostituendo il nome della classe racchiuso tra parentesi acute.</span><span class="sxs-lookup"><span data-stu-id="eef22-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="eef22-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="eef22-122">Example</span></span>  
 <span data-ttu-id="eef22-123">L'esempio seguente illustra i passaggi precedenti usando una classe EventArgs personalizzata e <xref:System.EventHandler%601> come tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="eef22-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="eef22-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eef22-124">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="eef22-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="eef22-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="eef22-126">Eventi</span><span class="sxs-lookup"><span data-stu-id="eef22-126">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="eef22-127">Delegati</span><span class="sxs-lookup"><span data-stu-id="eef22-127">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
