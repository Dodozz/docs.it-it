---
title: Procedure consigliate per la scrittura di unit test
description: Informazioni sulle procedure consigliate per la scrittura di unit test che migliorano la qualità del codice e la resilienza
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 00a0b999c9a08b04cb33bcb3a332513292beb363
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143409"
---
# <a name="unit-testing-best-practices"></a><span data-ttu-id="9fcb2-103">Procedure consigliate per gli unit test</span><span class="sxs-lookup"><span data-stu-id="9fcb2-103">Unit testing best practices</span></span>

<span data-ttu-id="9fcb2-104">A cura di [John Reese](http://reesespieces.io) con ringraziamenti speciali a [Roy Osherove](http://osherove.com/)</span><span class="sxs-lookup"><span data-stu-id="9fcb2-104">By [John Reese](http://reesespieces.io) with special thanks to [Roy Osherove](http://osherove.com/)</span></span>

<span data-ttu-id="9fcb2-105">La scrittura di unit test offre numerosi vantaggi: facilitano la regressione, rappresentano fonti di documentazione e semplificano la progettazione ottimale.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-105">There are numerous benefits to writing unit tests; they help with regression, provide documentation, and facilitate good design.</span></span> <span data-ttu-id="9fcb2-106">Tuttavia, unit test deboli e di difficile lettura possono causare seri problemi nella base codice.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-106">However, hard to read and brittle unit tests can wreak havoc on your code base.</span></span>

<span data-ttu-id="9fcb2-107">In questa guida verranno descritte alcune procedure consigliate per scrivere unit test flessibili e di facile comprensione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-107">In this guide, you'll learn some best practices when writing unit tests to keep your tests resilient and easy to understand.</span></span>

## <a name="why-unit-test"></a><span data-ttu-id="9fcb2-108">L'utilità degli unit test</span><span class="sxs-lookup"><span data-stu-id="9fcb2-108">Why unit test?</span></span>

### <a name="less-time-performing-functional-tests"></a><span data-ttu-id="9fcb2-109">Meno tempo da dedicare all'esecuzione dei test funzionali</span><span class="sxs-lookup"><span data-stu-id="9fcb2-109">Less time performing functional tests</span></span>
<span data-ttu-id="9fcb2-110">I test funzionali sono costosi.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-110">Functional tests are expensive.</span></span> <span data-ttu-id="9fcb2-111">Comportano, in genere, l'apertura dell'applicazione e l'esecuzione di una serie di passaggi che l'utente, o chi per lui, deve eseguire per convalidare il comportamento previsto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-111">They typically involve opening up the application and performing a series of steps that you (or someone else), must follow in order to validate the expected behavior.</span></span> <span data-ttu-id="9fcb2-112">Questi passaggi potrebbero non essere sempre chiari per chi esegue il test, pertanto questi dovrà contattare qualcuno con maggiori conoscenze in materia per eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-112">These steps may not always be known to the tester, which means they will have to reach out to someone more knowledgeable in the area in order to carry out the test.</span></span> <span data-ttu-id="9fcb2-113">Il test di semplici modifiche può richiedere solo alcuni secondi, che possono diventare minuti per modifiche più significative.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-113">Testing itself could take seconds for trivial changes, or minutes for larger changes.</span></span> <span data-ttu-id="9fcb2-114">Infine, questo processo deve essere ripetuto per ogni modifica apportata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-114">Lastly, this process must be repeated for every change that you make in the system.</span></span>

<span data-ttu-id="9fcb2-115">Gli unit test, invece, durano millisecondi, possono essere eseguiti facendo clic su un pulsante e non richiedono necessariamente una conoscenza approfondita del sistema.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-115">Unit tests, on the other hand, take milliseconds, can be run at the press of a button and do not necessarily require any knowledge of the system at large.</span></span> <span data-ttu-id="9fcb2-116">L'esito positivo o negativo del test è determinato dal test runner, non dai singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-116">Whether or not the test passes or fails is up to the test runner, not the individual.</span></span>

### <a name="protection-against-regression"></a><span data-ttu-id="9fcb2-117">Protezione contro la regressione</span><span class="sxs-lookup"><span data-stu-id="9fcb2-117">Protection against regression</span></span>
<span data-ttu-id="9fcb2-118">I difetti di regressione sono i difetti che vengono introdotti quando si apporta una modifica all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-118">Regression defects are defects that are introduced when a change is made to the application.</span></span> <span data-ttu-id="9fcb2-119">È pratica comune per i tester testare non solo le nuove funzionalità, ma anche quelle già esistenti per verificare che le funzionalità implementate in precedenza continuino a funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-119">It is common for testers to not only test their new feature but also features that existed beforehand in order to verify that previously implemented features still function as expected.</span></span>

<span data-ttu-id="9fcb2-120">Con gli unit test, è possibile eseguire nuovamente l'intero gruppo di test dopo ogni compilazione o persino dopo la modifica di una sola riga di codice.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-120">With unit testing, it's possible to rerun your entire suite of tests after every build or even after you change a line of code.</span></span> <span data-ttu-id="9fcb2-121">Questo, offrendo la certezza che il nuovo codice non interferisce con le funzionalità esistenti.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-121">Giving you confidence that your new code does not break existing functionality.</span></span>

### <a name="executable-documentation"></a><span data-ttu-id="9fcb2-122">Documentazione eseguibile</span><span class="sxs-lookup"><span data-stu-id="9fcb2-122">Executable documentation</span></span>
<span data-ttu-id="9fcb2-123">Non è sempre facile sapere lo scopo di un particolare metodo o il suo comportamento con un dato input.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-123">It may not always be obvious what a particular method does or how it behaves given a certain input.</span></span> <span data-ttu-id="9fcb2-124">Ci si potrebbe chiedere: che comportamento avrebbe questo metodo se fosse associato a una stringa vuota?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-124">You may ask yourself: How does this method behave if I pass it a blank string?</span></span> <span data-ttu-id="9fcb2-125">Restituirebbe un valore null?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-125">Null?</span></span>

<span data-ttu-id="9fcb2-126">Quando si dispone di un gruppo di unit test ben identificabili, per ogni test è possibile capire chiaramente l'output previsto per un dato input.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-126">When you have a suite of well-named unit tests, each test should be able to clearly explain the expected output for a given input.</span></span> <span data-ttu-id="9fcb2-127">Inoltre, è possibile verificarne l'effettivo funzionamento.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-127">In addition, it should be able to verify that it actually works.</span></span>

### <a name="less-coupled-code"></a><span data-ttu-id="9fcb2-128">Meno codice accoppiato</span><span class="sxs-lookup"><span data-stu-id="9fcb2-128">Less coupled code</span></span>
<span data-ttu-id="9fcb2-129">Quando il codice è strettamente accoppiato, può risultare difficile eseguire unit test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-129">When code is tightly coupled, it can be difficult to unit test.</span></span> <span data-ttu-id="9fcb2-130">Senza la creazione di unit test per il codice che si sta scrivendo, l'accoppiamento potrebbe risultare meno evidente.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-130">Without creating unit tests for the code that you're writing, coupling may be less apparent.</span></span>

<span data-ttu-id="9fcb2-131">La scrittura di test per il codice ha l'effetto di disaccoppiare naturalmente il codice perché le verifiche sarebbero, in caso contrario, più difficili.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-131">Writing tests for your code will naturally decouple your code, because it would be more difficult to test otherwise.</span></span>

## <a name="characteristics-of-a-good-unit-test"></a><span data-ttu-id="9fcb2-132">Caratteristiche di un buon unit test</span><span class="sxs-lookup"><span data-stu-id="9fcb2-132">Characteristics of a good unit test</span></span>
- <span data-ttu-id="9fcb2-133">**Veloce**.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-133">**Fast**.</span></span> <span data-ttu-id="9fcb2-134">Non è insolito per i progetti maturi comprendere migliaia di unit test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-134">It is not uncommon for mature projects to have thousands of unit tests.</span></span> <span data-ttu-id="9fcb2-135">La durata dell'esecuzione degli unit test dovrebbe essere molto breve.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-135">Unit tests should take very little time to run.</span></span> <span data-ttu-id="9fcb2-136">Millisecondi.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-136">Milliseconds.</span></span>
- <span data-ttu-id="9fcb2-137">**Isolato**.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-137">**Isolated**.</span></span> <span data-ttu-id="9fcb2-138">Gli unit test sono autonomi, possono essere eseguiti in modo isolato e non hanno dipendenze verso fattori esterni, ad esempio file system o database.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-138">Unit tests are standalone, can be run in isolation, and have no dependencies on any outside factors such as a file system or database.</span></span>
- <span data-ttu-id="9fcb2-139">**Ripetibile**.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-139">**Repeatable**.</span></span> <span data-ttu-id="9fcb2-140">Uno unit test deve generare risultati costanti, vale a dire, deve restituire sempre lo stesso risultato se tra le esecuzioni non si modifica alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-140">Running a unit test should be consistent with its results, that is, it always returns the same result if you do not change anything in between runs.</span></span>
- <span data-ttu-id="9fcb2-141">**Autonomo**.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-141">**Self-Checking**.</span></span> <span data-ttu-id="9fcb2-142">Il test deve essere in grado di rilevare automaticamente se ha avuto esito positivo o meno senza alcun intervento.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-142">The test should be able to automatically detect if it passed or failed without any human interaction.</span></span>
- <span data-ttu-id="9fcb2-143">**Rispetta i tempi previsti**.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-143">**Timely**.</span></span> <span data-ttu-id="9fcb2-144">Il tempo richiesto per la scrittura di uno unit test deve essere proporzionale al tempo richiesto per la scrittura del codice sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-144">A unit test should not take a disproportionally long time to write compared to the code being tested.</span></span> <span data-ttu-id="9fcb2-145">Se il test del codice richiede una quantità di tempo molto maggiore rispetto alla scrittura del codice, prendere in considerazione una struttura che risulti più testabile.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-145">If you find testing the code taking a large amount of time compared to writing the code, consider a design that is more testable.</span></span>

## <a name="lets-speak-the-same-language"></a><span data-ttu-id="9fcb2-146">Terminologia</span><span class="sxs-lookup"><span data-stu-id="9fcb2-146">Let's speak the same language</span></span>
<span data-ttu-id="9fcb2-147">Il termine *mock* è purtroppo usato in modo improprio quando si parla di testing.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-147">The term *mock* is unfortunately very misused when talking about testing.</span></span> <span data-ttu-id="9fcb2-148">Di seguito vengono definiti i tipi più comuni di *fake* per la scrittura di unit test:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-148">The following defines the most common types of *fakes* when writing unit tests:</span></span>

<span data-ttu-id="9fcb2-149">*Fake*: è un termine generico che può essere usato per descrivere uno stub o un mock.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-149">*Fake* - A fake is a generic term which can be used to describe either a stub or a mock object.</span></span> <span data-ttu-id="9fcb2-150">Il contesto di utilizzo determina se si tratta di uno stub o di un mock.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-150">Whether it is a stub or a mock depends on the context in which it's used.</span></span> <span data-ttu-id="9fcb2-151">Quindi, in altre parole, un fake può essere uno stub o un mock.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-151">So in other words, a fake can be a stub or a mock.</span></span>

<span data-ttu-id="9fcb2-152">*Mock*: un mock è un oggetto del sistema che decide se uno unit test ha avuto esito positivo o meno.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-152">*Mock* - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed.</span></span> <span data-ttu-id="9fcb2-153">Un mock inizia come fake fino a quando non diventa l'oggetto di un'asserzione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-153">A mock starts out as a Fake until it is asserted against.</span></span>

<span data-ttu-id="9fcb2-154">*Stub*: è la sostituzione controllabile nel sistema di una dipendenza o di un collaboratore.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-154">*Stub* - A stub is a controllable replacement for an existing dependency (or collaborator) in the system.</span></span> <span data-ttu-id="9fcb2-155">Utilizzando uno stub è possibile testare il codice senza prendere direttamente in considerazione la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-155">By using a stub, you can test your code without dealing with the dependency directly.</span></span> <span data-ttu-id="9fcb2-156">Per impostazione predefinita, un fake è inizialmente uno stub.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-156">By default, a fake starts out as a stub.</span></span>

<span data-ttu-id="9fcb2-157">Si prenda in considerazione il seguente frammento di codice:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-157">Consider the following code snippet:</span></span>

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="9fcb2-158">Quanto segue è un esempio di stub che verrebbe chiamato mock.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-158">This would be an example of stub being referred to as a mock.</span></span> <span data-ttu-id="9fcb2-159">In questo caso, si tratta di stub.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-159">In this case, it is a stub.</span></span> <span data-ttu-id="9fcb2-160">Si sta passando Order solo come mezzo per creare un'istanza di `Purchase` (il sistema sottoposto a test).</span><span class="sxs-lookup"><span data-stu-id="9fcb2-160">You're just passing in the Order as a means to be able to instantiate `Purchase` (the system under test).</span></span> <span data-ttu-id="9fcb2-161">Il nome `MockOrder` è anche estremamente fuorviante perché, anche in questo caso, l'ordine non è un mock.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-161">The name `MockOrder` is also very misleading because again, the order is not a mock.</span></span>

<span data-ttu-id="9fcb2-162">Un approccio migliore sarebbe</span><span class="sxs-lookup"><span data-stu-id="9fcb2-162">A better approach would be</span></span>

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="9fcb2-163">Rinominando la classe `FakeOrder` la si rende più generica e la si rende utilizzabile come mock o stub,</span><span class="sxs-lookup"><span data-stu-id="9fcb2-163">By renaming the class to `FakeOrder`, you've made the class a lot more generic, the class can be used as a mock or a stub.</span></span> <span data-ttu-id="9fcb2-164">a seconda del valore migliore per il tipo di test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-164">Whichever is better for the test case.</span></span> <span data-ttu-id="9fcb2-165">Nell'esempio precedente, `FakeOrder` viene usato come stub.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-165">In the above example, `FakeOrder` is used as a stub.</span></span> <span data-ttu-id="9fcb2-166">`FakeOrder` non viene usato in alcun modo durante l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-166">You're not using the `FakeOrder` in any shape or form during the assert.</span></span> <span data-ttu-id="9fcb2-167">`FakeOrder` è stato passato alla classe `Purchase` unicamente per soddisfare i requisiti del costruttore.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-167">`FakeOrder` was just passed into the `Purchase` class to satisfy the requirements of the constructor.</span></span>

<span data-ttu-id="9fcb2-168">Per usarlo come mock, si potrebbe procedere così</span><span class="sxs-lookup"><span data-stu-id="9fcb2-168">To use it as a Mock, you could do something like this</span></span>

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

<span data-ttu-id="9fcb2-169">In questo caso, si verifica una proprietà del fake, con un'asserzione su di essa, pertanto nel frammento di codice precedente, `mockOrder` è un mock.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-169">In this case, you are checking a property on the Fake (asserting against it), so in the above code snippet, the `mockOrder` is a Mock.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fcb2-170">È importante usare questa terminologia in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-170">It's important to get this terminology correct.</span></span> <span data-ttu-id="9fcb2-171">Se si chiamano gli stub "mock", altri sviluppatori faranno ipotesi errate sulle intenzioni espresse.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-171">If you call your stubs "mocks", other developers are going to make false assumptions about your intent.</span></span>

<span data-ttu-id="9fcb2-172">La cosa principale da ricordare riguardo a mock e stub è che i mock sono analoghi agli stub, ma che si può rivolgere un'asserzione a un mock, ma non a uno stub.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-172">The main thing to remember about mocks versus stubs is that mocks are just like stubs, but you assert against the mock object, whereas you do not assert against a stub.</span></span>

## <a name="best-practices"></a><span data-ttu-id="9fcb2-173">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="9fcb2-173">Best practices</span></span>

### <a name="naming-your-tests"></a><span data-ttu-id="9fcb2-174">Denominare i test</span><span class="sxs-lookup"><span data-stu-id="9fcb2-174">Naming your tests</span></span>
<span data-ttu-id="9fcb2-175">Il nome del test deve essere costituito da tre parti:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-175">The name of your test should consist of three parts:</span></span>
- <span data-ttu-id="9fcb2-176">Nome del metodo testato.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-176">The name of the method being tested.</span></span>
- <span data-ttu-id="9fcb2-177">Scenario in cui si sta testando.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-177">The scenario under which it's being tested.</span></span>
- <span data-ttu-id="9fcb2-178">Comportamento previsto quando viene richiamato lo scenario.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-178">The expected behavior when the scenario is invoked.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-179">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-179">Why?</span></span>
- <span data-ttu-id="9fcb2-180">Gli standard di denominazione sono importanti perché esprimono in modo esplicito l'intento del test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-180">Naming standards are important because they explicitly express the intent of the test.</span></span>

<span data-ttu-id="9fcb2-181">I test non si limitano a verificare che il codice funzioni, ma documentano anche il risultato.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-181">Tests are more than just making sure your code works, they also provide documentation.</span></span> <span data-ttu-id="9fcb2-182">Osservando semplicemente il gruppo di unit test, sarà possibile dedurre il comportamento del codice senza neanche guardare il codice.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-182">Just by looking at the suite of unit tests, you should be able to infer the behavior of your code without even looking at the code itself.</span></span> <span data-ttu-id="9fcb2-183">Inoltre, quando i test hanno esito negativo, è possibile vedere esattamente quali scenari non soddisfano le aspettative.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-183">Additionally, when tests fail, you can see exactly which scenarios do not meet your expectations.</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-184">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-184">Bad:</span></span>
[!code-csharp[BeforeNaming](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a><span data-ttu-id="9fcb2-185">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-185">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a><span data-ttu-id="9fcb2-186">Disposizione dei test</span><span class="sxs-lookup"><span data-stu-id="9fcb2-186">Arranging your tests</span></span>
<span data-ttu-id="9fcb2-187">**Disporre, agire, asserire** è uno schema comune per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-187">**Arrange, Act, Assert** is a common pattern when unit testing.</span></span> <span data-ttu-id="9fcb2-188">Come suggerisce il nome, è costituito da tre azioni principali:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-188">As the name implies, it consists of three main actions:</span></span>
- <span data-ttu-id="9fcb2-189">*Disporre* gli oggetti, creandoli e configurandoli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-189">*Arrange* your objects, creating and setting them up as necessary.</span></span>
- <span data-ttu-id="9fcb2-190">*Agire* su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-190">*Act* on an object.</span></span>
- <span data-ttu-id="9fcb2-191">*Asserire* che un dato comportamento è come previsto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-191">*Assert* that something is as expected.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-192">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-192">Why?</span></span>
- <span data-ttu-id="9fcb2-193">Separare nettamente l'oggetto del test dai passaggi *disporre* e *asserire*.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-193">Clearly separates what is being tested from the *arrange* and *assert* steps.</span></span>
- <span data-ttu-id="9fcb2-194">Il rischio di mescolare le asserzioni con il codice "agire" è minore.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-194">Less chance to intermix assertions with "Act" code.</span></span>

<span data-ttu-id="9fcb2-195">La leggibilità è uno degli aspetti più importanti da considerare durante la scrittura di un test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-195">Readability is one of the most important aspects when writing a test.</span></span> <span data-ttu-id="9fcb2-196">La separazione di ognuna di queste azioni all'interno del test evidenzia chiaramente le dipendenze necessarie per chiamare il codice, come viene chiamato il codice e ciò che si sta tentando di asserire.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-196">Separating each of these actions within the test clearly highlight the dependencies required to call your code, how your code is being called, and what you are trying to assert.</span></span> <span data-ttu-id="9fcb2-197">Sebbene sia possibile combinare alcuni passaggi e ridurre le dimensioni del test, l'obiettivo principale rimane rendere il test più leggibile possibile.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-197">While it may be possible to combine some steps and reduce the size of your test, the primary goal is to make the test as readable as possible.</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-198">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-198">Bad:</span></span>
[!code-csharp[BeforeArranging](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a><span data-ttu-id="9fcb2-199">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-199">Better:</span></span>
[!code-csharp[AfterArranging](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a><span data-ttu-id="9fcb2-200">Scrivere test più semplici possibile</span><span class="sxs-lookup"><span data-stu-id="9fcb2-200">Write minimally passing tests</span></span>
<span data-ttu-id="9fcb2-201">L'input da usare in uno unit test deve essere il più semplice possibile per verificare il comportamento che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-201">The input to be used in a unit test should be the simplest possible in order to verify the behavior that you are currently testing.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-202">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-202">Why?</span></span>
- <span data-ttu-id="9fcb2-203">I test diventano più adattabili alle modifiche future nella base codice.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-203">Tests become more resilient to future changes in the codebase.</span></span>
- <span data-ttu-id="9fcb2-204">I test hanno un comportamento più simile a quello dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-204">Closer to testing behavior over implementation.</span></span>

<span data-ttu-id="9fcb2-205">Test che includono più informazioni rispetto a quelle necessarie per la verifica hanno maggiori probabilità di contenere errori e il loro intento risulta meno chiaro.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-205">Tests that include more information than required to pass the test have a higher chance of introducing errors into the test and can make the intent of the test less clear.</span></span> <span data-ttu-id="9fcb2-206">Durante la scrittura dei test, è necessario concentrare l'attenzione sul comportamento.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-206">When writing tests you want to focus on the behavior.</span></span> <span data-ttu-id="9fcb2-207">L'impostazione di proprietà aggiuntive per i modelli o l'uso di valori diversi da zero quando non sono necessari distoglie l'attenzione da ciò che si sta tentando di provare.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-207">Setting extra properties on models or using non-zero values when not required, only detracts from what you are trying to prove.</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-208">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-208">Bad:</span></span>
[!code-csharp[BeforeMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a><span data-ttu-id="9fcb2-209">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-209">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a><span data-ttu-id="9fcb2-210">Evitare le "stringhe magiche"</span><span class="sxs-lookup"><span data-stu-id="9fcb2-210">Avoid magic strings</span></span>
<span data-ttu-id="9fcb2-211">La denominazione delle variabili negli unit test è importante quanto la denominazione delle variabili nel codice di produzione o anche di più.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-211">Naming variables in unit tests is as important, if not more important, than naming variables in production code.</span></span> <span data-ttu-id="9fcb2-212">Gli unit test non devono contenere "stringhe magiche".</span><span class="sxs-lookup"><span data-stu-id="9fcb2-212">Unit tests should not contain magic strings.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-213">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-213">Why?</span></span>
- <span data-ttu-id="9fcb2-214">Impediscono a chi legge il test di controllare il codice di produzione per scoprire ciò che rende il valore speciale.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-214">Prevents the need for the reader of the test to inspect the production code in order to figure out what makes the value special.</span></span>
- <span data-ttu-id="9fcb2-215">Illustrano in modo esplicito ciò che si sta tentando di *dimostrare* anziché ciò che si tenta di *compiere*.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-215">Explicitly shows what you're trying to *prove* rather than trying to *accomplish*.</span></span>

<span data-ttu-id="9fcb2-216">Le "stringhe magiche" possono causare confusione a chi legge il test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-216">Magic strings can cause confusion to the reader of your tests.</span></span> <span data-ttu-id="9fcb2-217">Se una stringa appare insolita, ci si potrebbe domandare perché è stato scelto un determinato valore per un parametro o valore restituito.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-217">If a string looks out of the ordinary, they may wonder why a certain value was chosen for a parameter or return value.</span></span> <span data-ttu-id="9fcb2-218">Ciò porterebbe a esaminare i dettagli di implementazione piuttosto che il test stesso.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-218">This may lead them to take a closer look at the implementation details, rather than focus on the test.</span></span>

> [!TIP] 
> <span data-ttu-id="9fcb2-219">Quando si scrivono i test, bisogna porsi l'obiettivo di esprimere nel modo più chiaro possibile le loro finalità.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-219">When writing tests, you should aim to express as much intent as possible.</span></span> <span data-ttu-id="9fcb2-220">Nel caso delle "stringhe magiche", un buon espediente consiste nell'assegnare questi valori a costanti.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-220">In the case of magic strings, a good approach is to assign these values to constants.</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-221">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-221">Bad:</span></span>
[!code-csharp[BeforeMagicString](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a><span data-ttu-id="9fcb2-222">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-222">Better:</span></span>
[!code-csharp[AfterMagicString](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a><span data-ttu-id="9fcb2-223">Evitare la logica nei test</span><span class="sxs-lookup"><span data-stu-id="9fcb2-223">Avoid logic in tests</span></span>
<span data-ttu-id="9fcb2-224">Quando si scrivono gli unit test bisogna evitare la concatenazione manuale di stringhe e le condizioni logiche, ad esempio `if`, `while`, `for`, `switch` e così via.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-224">When writing your unit tests avoid manual string concatenation and logical conditions such as `if`, `while`, `for`, `switch`, etc.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-225">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-225">Why?</span></span>
- <span data-ttu-id="9fcb2-226">Minore possibilità di introdurre un bug nei test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-226">Less chance to introduce a bug inside of your tests.</span></span>
- <span data-ttu-id="9fcb2-227">Per concentrarsi sul risultato finale anziché sui dettagli di implementazione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-227">Focus on the end result, rather than implementation details.</span></span>

<span data-ttu-id="9fcb2-228">Se si introduce la logica nel gruppo di test, la possibilità di introdurre un bug al suo interno aumenta notevolmente.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-228">When you introduce logic into your test suite, the chance of introducing a bug into it increases dramatically.</span></span> <span data-ttu-id="9fcb2-229">L'ultimo posto in cui deve esserci un bug è il gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-229">The last place that you want to find a bug is within your test suite.</span></span> <span data-ttu-id="9fcb2-230">Si deve avere un elevato livello di fiducia riguardo al funzionamento dei test altrimenti non sarà possibile considerarli attendibili.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-230">You should have a high level of confidence that your tests work, otherwise, you will not trust them.</span></span> <span data-ttu-id="9fcb2-231">E dei test considerati non attendibili non hanno alcun valore.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-231">Tests that you do not trust, do not provide any value.</span></span> <span data-ttu-id="9fcb2-232">Quando un test ha esito negativo, è necessario avere la percezione che ci sia un problema nel codice che non può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-232">When a test fails, you want to have a sense that something is actually wrong with your code and that it cannot be ignored.</span></span>

> [!TIP]
> <span data-ttu-id="9fcb2-233">Se risulta inevitabile inserire la logica nel test, è consigliabile suddividere il test in due o più test diversi.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-233">If logic in your test seems unavoidable, consider splitting the test up into two or more different tests.</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-234">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-234">Bad:</span></span>
[!code-csharp[LogicInTests](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a><span data-ttu-id="9fcb2-235">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-235">Better:</span></span>
[!code-csharp[AfterTestLogic](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a><span data-ttu-id="9fcb2-236">Prediligere i metodi helper agli attributi Setup e Teardown</span><span class="sxs-lookup"><span data-stu-id="9fcb2-236">Prefer helper methods to setup and teardown</span></span>
<span data-ttu-id="9fcb2-237">Se si richiede un oggetto o uno stato simile per i test, prediligere un metodo helper piuttosto che utilizzare gli attributi Setup e Teardown, se presenti.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-237">If you require a similar object or state for your tests, prefer a helper method than leveraging Setup and Teardown attributes if they exist.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-238">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-238">Why?</span></span>
- <span data-ttu-id="9fcb2-239">La lettura dei test è più agevole dal momento che la totalità del codice è visibile nel test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-239">Less confusion when reading the tests since all of the code is visible from within each test.</span></span>
- <span data-ttu-id="9fcb2-240">Minore rischio di configurare troppo o troppo poco per il test specificato.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-240">Less chance of setting up too much or too little for the given test.</span></span>
- <span data-ttu-id="9fcb2-241">Minore rischio di condividere lo stato tra i test creando dipendenze non desiderate tra di essi.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-241">Less chance of sharing state between tests which creates unwanted dependencies between them.</span></span>

<span data-ttu-id="9fcb2-242">Nel framework di testing unità, `Setup` viene chiamato prima di ogni unit test all'interno del gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-242">In unit testing frameworks, `Setup` is called before each and every unit test within your test suite.</span></span> <span data-ttu-id="9fcb2-243">Mentre ad alcuni può apparire uno strumento utile, in realtà genera test troppo grandi e difficili da leggere.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-243">While some may see this as a useful tool, it generally ends up leading to bloated and hard to read tests.</span></span> <span data-ttu-id="9fcb2-244">I requisiti per rendere ogni test operativo variano da test a test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-244">Each test will generally have different requirements in order to get the test up and running.</span></span> <span data-ttu-id="9fcb2-245">Sfortunatamente, `Setup` obbliga a usare esattamente gli stessi requisiti per ogni test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-245">Unfortunately, `Setup` forces you to use the exact same requirements for each test.</span></span>

> [!NOTE] 
> <span data-ttu-id="9fcb2-246">SetUp e TearDown sono stati rimossi a partire dalla versione 2.x di xUnit</span><span class="sxs-lookup"><span data-stu-id="9fcb2-246">xUnit has removed both SetUp and TearDown as of version 2.x</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-247">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-247">Bad:</span></span>
[!code-csharp[BeforeSetup](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a><span data-ttu-id="9fcb2-248">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-248">Better:</span></span>
[!code-csharp[AfterHelperMethod](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a><span data-ttu-id="9fcb2-249">Evitare le asserzioni multiple</span><span class="sxs-lookup"><span data-stu-id="9fcb2-249">Avoid multiple asserts</span></span>
<span data-ttu-id="9fcb2-250">Quando si scrivono i test, puntare a includere una sola asserzione per ogni test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-250">When writing your tests, try to only include one Assert per test.</span></span> <span data-ttu-id="9fcb2-251">Le strategie comuni per usare una sola asserzione includono:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-251">Common approaches to using only one assert include:</span></span>
- <span data-ttu-id="9fcb2-252">Creare un test separato per ogni asserzione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-252">Create a separate test for each assert.</span></span>
- <span data-ttu-id="9fcb2-253">Usare test con parametri.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-253">Use parameterized tests.</span></span>

#### <a name="why"></a><span data-ttu-id="9fcb2-254">Perché?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-254">Why?</span></span>
- <span data-ttu-id="9fcb2-255">Se un'asserzione ha esito negativo, le asserzioni successive non verranno valutate.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-255">If one Assert fails, the subsequent Asserts will not be evaluated.</span></span>
- <span data-ttu-id="9fcb2-256">Garantisce che l'asserzione non venga applicata a più test case.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-256">Ensures you are not asserting multiple cases in your tests.</span></span>
- <span data-ttu-id="9fcb2-257">Offre il quadro completo del motivo per cui i test non sono riusciti.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-257">Gives you the entire picture as to why your tests are failing.</span></span> 

<span data-ttu-id="9fcb2-258">Quando si introducono più asserzioni in un test case, non è sicuro che tutte le asserzioni verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-258">When introducing multiple asserts into a test case, it is not guaranteed that all of the asserts will be executed.</span></span> <span data-ttu-id="9fcb2-259">Nella maggior parte dei framework di testing unità, una volta che un'asserzione ha esito negativo in uno unit test, i test successivi sono automaticamente considerati come non riusciti.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-259">In most unit testing frameworks, once an assertion fails in a unit test, the proceeding tests are automatically considered to be failing.</span></span> <span data-ttu-id="9fcb2-260">Ciò può generare confusione perché la funzionalità genererà un errore, anche se in realtà funziona.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-260">This can be confusing as functionality that is actually working, will be shown as failing.</span></span>

> [!NOTE]
> <span data-ttu-id="9fcb2-261">Un'eccezione comune a questa regola riguarda l'asserzione per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-261">A common exception to this rule is when asserting against an object.</span></span> <span data-ttu-id="9fcb2-262">In questo caso, è in genere accettabile avere più asserzioni per ogni proprietà per assicurarsi che l'oggetto sia nello stato previsto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-262">In this case, it is generally acceptable to have multiple asserts against each property to ensure the object is in the state that you expect it to be in.</span></span>

#### <a name="bad"></a><span data-ttu-id="9fcb2-263">Scadente:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-263">Bad:</span></span>
[!code-csharp[BeforeMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a><span data-ttu-id="9fcb2-264">Migliore:</span><span class="sxs-lookup"><span data-stu-id="9fcb2-264">Better:</span></span>
[!code-csharp[AfterMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a><span data-ttu-id="9fcb2-265">Convalidare i metodi privati tramite il testing unità dei metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="9fcb2-265">Validate private methods by unit testing public methods</span></span>
<span data-ttu-id="9fcb2-266">Nella maggior parte dei casi, non è necessario testare un metodo privato.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-266">In most cases, there should not be a need to test a private method.</span></span> <span data-ttu-id="9fcb2-267">I metodi privati sono un dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-267">Private methods are an implementation detail.</span></span> <span data-ttu-id="9fcb2-268">Consideriamo la cosa da questo punto di vista: i metodi privati non esistono singolarmente.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-268">You can think of it this way: private methods never exist in isolation.</span></span> <span data-ttu-id="9fcb2-269">A un certo punto, ci sarà un metodo pubblico che chiama il metodo privato come parte della sua implementazione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-269">At some point, there is going to be a public facing method that calls the private method as part of its implementation.</span></span> <span data-ttu-id="9fcb2-270">Quello che è opportuno prendere in considerazione è il risultato finale del metodo pubblico che chiama quello privato.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-270">What you should care about is the end result of the public method that calls into the private one.</span></span> 

<span data-ttu-id="9fcb2-271">Si consideri il caso seguente</span><span class="sxs-lookup"><span data-stu-id="9fcb2-271">Consider the following case</span></span>

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = trimInput(input);
    return sanitizedInput;
}

private string trimInput(string input)
{
    return input.Trim();
}
```

<span data-ttu-id="9fcb2-272">La prima reazione dell'utente potrebbe essere iniziare a scrivere un test per `trimInput` per verificare che il metodo funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-272">Your first reaction may be to start writing a test for `trimInput` because you want to make sure that the method is working as expected.</span></span> <span data-ttu-id="9fcb2-273">Tuttavia, è probabile che `ParseLogLine` manipoli `sanitizedInput` in un modo imprevisto che rende il test di `trimInput` inutile.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-273">However, it is entirely possible that `ParseLogLine` manipulates `sanitizedInput` in such a way that you do not expect, rendering a test against `trimInput` useless.</span></span> 

<span data-ttu-id="9fcb2-274">Il test reale deve essere eseguito con il metodo pubblico `ParseLogLine` perché questo è ciò che è necessario considerare.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-274">The real test should be done against the public facing method `ParseLogLine` because that is what you should ultimately care about.</span></span> 

```csharp
public void ParseLogLine_ByDefault_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

<span data-ttu-id="9fcb2-275">Tenendo presente questo aspetto, quando si vede un metodo privato, trovare il metodo pubblico e scrivere i test su tale metodo.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-275">With this viewpoint, if you see a private method, find the public method and write your tests against that method.</span></span> <span data-ttu-id="9fcb2-276">Unicamente perché un metodo privato restituisce il risultato previsto non implica che il sistema che chiama il metodo privato usi il risultato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-276">Just because a private method returns the expected result, does not mean the system that eventually calls the private method uses the result correctly.</span></span>

### <a name="stub-static-references"></a><span data-ttu-id="9fcb2-277">Riferimenti statici negli stub</span><span class="sxs-lookup"><span data-stu-id="9fcb2-277">Stub static references</span></span>
<span data-ttu-id="9fcb2-278">Uno dei principi a cui uno unit test si deve attenere è che deve avere controllo completo del sistema sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-278">One of the principles of a unit test is that it must have full control of the system under test.</span></span> <span data-ttu-id="9fcb2-279">Ciò può risultare problematico quando il codice di produzione include chiamate ai riferimenti statici (ad esempio `DateTime.Now`).</span><span class="sxs-lookup"><span data-stu-id="9fcb2-279">This can be problematic when production code includes calls to static references (e.g. `DateTime.Now`).</span></span> <span data-ttu-id="9fcb2-280">Si consideri il codice seguente</span><span class="sxs-lookup"><span data-stu-id="9fcb2-280">Consider the following code</span></span>

```csharp
public int GetDiscountedPrice(int price)
{
    if(DateTime.Now == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="9fcb2-281">In che modo questo codice può essere sottoposta a testing unità?</span><span class="sxs-lookup"><span data-stu-id="9fcb2-281">How can this code possibly be unit tested?</span></span> <span data-ttu-id="9fcb2-282">Provare una strategia di questo tipo</span><span class="sxs-lookup"><span data-stu-id="9fcb2-282">You may try an approach such as</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="9fcb2-283">Sfortunatamente, ci si renderà rapidamente conto che nel test ci sono un paio di problemi.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-283">Unfortunately, you will quickly realize that there are a couple problems with your tests.</span></span> 

- <span data-ttu-id="9fcb2-284">Se il gruppo di test viene eseguito di martedì, il secondo test avrà esito positivo, ma il primo test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-284">If the test suite is run on a Tuesday, the second test will pass, but the first test will fail.</span></span>
- <span data-ttu-id="9fcb2-285">Se il gruppo di test viene eseguito un qualsiasi altro giorno, il primo test avrà esito positivo, ma il secondo test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-285">If the test suite is run on any other day, the first test will pass, but the second test will fail.</span></span>

<span data-ttu-id="9fcb2-286">Per risolvere questi problemi, sarà necessario introdurre un *seam* nel codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-286">To solve these problems, you'll need to introduce a *seam* into your production code.</span></span> <span data-ttu-id="9fcb2-287">Una strategia consiste nell'inserire il codice da controllare in un'interfaccia e far dipendere il codice di produzione da tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-287">One approach is to wrap the code that you need to control in an interface and have the production code depend on that interface.</span></span>

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if(dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="9fcb2-288">Il gruppo di test diventa</span><span class="sxs-lookup"><span data-stu-id="9fcb2-288">Your test suite now becomes</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="9fcb2-289">Ora il gruppo di test ha pieno controllo su `DateTime.Now` ed è possibile sottoporre a stub qualsiasi valore durante la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="9fcb2-289">Now the test suite has full control over `DateTime.Now` and can stub any value when calling into the method.</span></span>
