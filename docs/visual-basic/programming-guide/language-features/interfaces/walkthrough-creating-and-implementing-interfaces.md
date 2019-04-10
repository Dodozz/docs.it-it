---
title: Creazione e implementazione di interfacce (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322030"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="a6406-102">Procedura dettagliata: Creazione e implementazione di interfacce (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6406-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="a6406-103">Le interfacce vengono descritte le caratteristiche della proprietà, metodi ed eventi, ma lasciare i dettagli di implementazione fino a strutture o classi.</span><span class="sxs-lookup"><span data-stu-id="a6406-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="a6406-104">Questa procedura dettagliata illustra come dichiarare e implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a6406-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6406-105">Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a6406-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="a6406-106">Per definire un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="a6406-106">To define an interface</span></span>
  
1. <span data-ttu-id="a6406-107">Aprire un nuovo progetto Applicazione Windows in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a6406-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="a6406-108">Aggiungere un nuovo modulo al progetto facendo clic **Aggiungi modulo** nel **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="a6406-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="a6406-109">Denominare il nuovo modulo `Module1.vb` e fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="a6406-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="a6406-110">Viene visualizzato il codice per il nuovo modulo.</span><span class="sxs-lookup"><span data-stu-id="a6406-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="a6406-111">Definire un'interfaccia denominata `TestInterface` all'interno `Module1` digitando `Interface TestInterface` tra il `Module` e `End Module` istruzioni e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a6406-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="a6406-112">Il **Editor di codice** rientri le `Interface` parola chiave e aggiunge un `End Interface` istruzione in modo da formare un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="a6406-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="a6406-113">Definire una proprietà, metodo ed eventi per l'interfaccia inserendo il codice seguente tra i `Interface` e `End Interface` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="a6406-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="a6406-114">Implementazione</span><span class="sxs-lookup"><span data-stu-id="a6406-114">Implementation</span></span>

 <span data-ttu-id="a6406-115">È possibile notare che la sintassi usata per dichiarare i membri di interfaccia è diversa da quella utilizzata per dichiarare i membri della classe.</span><span class="sxs-lookup"><span data-stu-id="a6406-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="a6406-116">La differenza è dovuta al fatto che le interfacce non possono contenere codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="a6406-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="a6406-117">Per implementare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="a6406-117">To implement the interface</span></span>
  
1. <span data-ttu-id="a6406-118">Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente alle `Module1`, dopo il `End Interface` istruzione ma prima di `End Module` istruzione e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="a6406-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="a6406-119">Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** fornisce un oggetto corrispondente `End Class` istruzione quando si preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="a6406-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="a6406-120">Aggiungere il codice seguente `Implements` dell'istruzione `ImplementationClass`, quali nome dell'interfaccia implementata dalla classe:</span><span class="sxs-lookup"><span data-stu-id="a6406-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="a6406-121">Quando elencati separatamente dagli altri elementi nella parte superiore di una classe o struttura, il `Implements` istruzione indica che la classe o struttura implementa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a6406-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="a6406-122">Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** implementa i membri della classe richiesti da `TestInterface` quando si preme INVIO, e si può ignorare il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a6406-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="a6406-123">Se non si lavora all'interno dell'ambiente di sviluppo integrato, è necessario implementare tutti i membri dell'interfaccia `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="a6406-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="a6406-124">Aggiungere il codice seguente a `ImplementationClass` implementare `Event1`, `Method1`, e `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="a6406-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="a6406-125">Il `Implements` l'istruzione viene assegnato l'interfaccia e un membro di interfaccia implementato.</span><span class="sxs-lookup"><span data-stu-id="a6406-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="a6406-126">Completare la definizione di `Prop1` aggiungendo un campo privato per la classe che è archiviato il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="a6406-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="a6406-127">Restituire il valore di `pval` dalla proprietà di funzione di accesso get.</span><span class="sxs-lookup"><span data-stu-id="a6406-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="a6406-128">Impostare il valore di `pval` nel set di proprietà della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="a6406-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="a6406-129">Completare la definizione di `Method1` aggiungendo il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a6406-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="a6406-130">Per testare l'implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="a6406-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="a6406-131">Fare doppio clic su form di avvio per il progetto nel **Esplora soluzioni**, fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="a6406-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="a6406-132">L'editor consente di visualizzare la classe del form di avvio.</span><span class="sxs-lookup"><span data-stu-id="a6406-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="a6406-133">Per impostazione predefinita, viene chiamato il modulo di avvio `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a6406-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="a6406-134">Aggiungere il codice seguente `testInstance` campo per il `Form1` classe:</span><span class="sxs-lookup"><span data-stu-id="a6406-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="a6406-135">Dichiarando `testInstance` come `WithEvents`, il `Form1` classe può gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="a6406-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="a6406-136">Aggiungere il seguente gestore eventi per il `Form1` classe per gestire gli eventi generati da `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="a6406-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="a6406-137">Aggiungere una subroutine denominata `Test` per il `Form1` classe per testare la classe di implementazione:</span><span class="sxs-lookup"><span data-stu-id="a6406-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="a6406-138">Il `Test` routine crea un'istanza della classe che implementa `MyInterface`, assegna tale istanza per il `testInstance` imposta una proprietà, campo e viene eseguito un metodo tramite l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a6406-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="a6406-139">Aggiungere il codice per chiamare il `Test` procedure dal `Form1 Load` routine del form di avvio:</span><span class="sxs-lookup"><span data-stu-id="a6406-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="a6406-140">Eseguire il `Test` procedura premendo F5.</span><span class="sxs-lookup"><span data-stu-id="a6406-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="a6406-141">Viene visualizzato il messaggio "Prop1 è stato impostato su 9".</span><span class="sxs-lookup"><span data-stu-id="a6406-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="a6406-142">Viene visualizzato dopo aver selezionato OK, il messaggio "il parametro X per Method1 is 5".</span><span class="sxs-lookup"><span data-stu-id="a6406-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="a6406-143">Fare clic su OK e viene visualizzato il messaggio "il gestore dell'evento rilevato l'evento".</span><span class="sxs-lookup"><span data-stu-id="a6406-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6406-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6406-144">See also</span></span>

- [<span data-ttu-id="a6406-145">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="a6406-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="a6406-146">Interfacce</span><span class="sxs-lookup"><span data-stu-id="a6406-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="a6406-147">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="a6406-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="a6406-148">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="a6406-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
