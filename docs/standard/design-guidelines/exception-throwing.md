---
title: Generazione di eccezioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: KrzysztofCwalina
ms.openlocfilehash: 016a42ee7a772a3268e823e75b6239467e13b315
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148042"
---
# <a name="exception-throwing"></a><span data-ttu-id="595e0-102">Generazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="595e0-102">Exception Throwing</span></span>
<span data-ttu-id="595e0-103">Linee guida che generano eccezioni descritte in questa sezione richiedono una buona definizione del significato dell'errore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="595e0-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="595e0-104">Errore di esecuzione si verifica ogni volta che un membro non è possibile fare ciò che è stato progettato per eseguire operazioni (quali il nome del membro implica).</span><span class="sxs-lookup"><span data-stu-id="595e0-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="595e0-105">Ad esempio, se il `OpenFile` metodo non può restituire un handle di file aperto al chiamante, possa essere considerato un errore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="595e0-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="595e0-106">La maggior parte degli sviluppatori acquisita familiarità con l'utilizzo di eccezioni per gli errori di utilizzo, ad esempio divisione per zero o riferimenti null.</span><span class="sxs-lookup"><span data-stu-id="595e0-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="595e0-107">In Framework, le eccezioni vengono usate per tutte le condizioni di errore, compresi gli errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="595e0-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="595e0-108">**X DO NOT** restituiscono codici di errore.</span><span class="sxs-lookup"><span data-stu-id="595e0-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="595e0-109">Le eccezioni sono il mezzo principale per la segnalazione degli errori nei Framework.</span><span class="sxs-lookup"><span data-stu-id="595e0-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="595e0-110">**✓ DO** segnalare errori di esecuzione mediante la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="595e0-111">**✓ CONSIDER** il processo verrà terminato chiamando `System.Environment.FailFast` (funzionalità di .NET Framework 2.0) anziché generare un'eccezione se il codice rileva una situazione in cui non è sicuro per l'esecuzione di un'ulteriore.</span><span class="sxs-lookup"><span data-stu-id="595e0-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="595e0-112">**X DO NOT** utilizza le eccezioni per il normale flusso di controllo, se possibile.</span><span class="sxs-lookup"><span data-stu-id="595e0-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="595e0-113">Ad eccezione di errori di sistema e le operazioni con potenziali race condition, progettisti del framework devono progettare le API in modo che gli utenti possono scrivere codice che non genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="595e0-114">Ad esempio, è possibile fornire un modo per controllare le condizioni preliminari prima di chiamare un membro in modo che gli utenti possono scrivere codice che non genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="595e0-115">Il membro usato per controllare le precondizioni di un altro membro è noto anche come un tester e il membro che effettivamente esegue il lavoro viene chiamato agente.</span><span class="sxs-lookup"><span data-stu-id="595e0-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="595e0-116">Vi sono alcuni casi il Tester-Doer (modello) può produrre un overhead di prestazioni inaccettabili.</span><span class="sxs-lookup"><span data-stu-id="595e0-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="595e0-117">In questi casi, deve essere considerato il cosiddetto modello Try-Parse (vedere [eccezioni e prestazioni](../../../docs/standard/design-guidelines/exceptions-and-performance.md) per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="595e0-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="595e0-118">**✓ CONSIDER** le implicazioni sulle prestazioni di generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="595e0-119">Velocità di generazione superiore a 100 al secondo probabile compromettere notevolmente le prestazioni della maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="595e0-120">**✓ DO** documento tutte le eccezioni generate dai membri pubblicamente disponibile per la chiamata a causa di una violazione del membro del contratto (anziché un errore di sistema) e li considerano come parte del contratto.</span><span class="sxs-lookup"><span data-stu-id="595e0-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="595e0-121">Le eccezioni che fanno parte del contratto non devono modificare da una versione a quella successiva (ad esempio, non deve cambiare tipo di eccezione e non devono essere aggiunte nuove eccezioni).</span><span class="sxs-lookup"><span data-stu-id="595e0-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="595e0-122">**X DO NOT** disporre i membri pubblici che possono generare o non in base a un'opzione.</span><span class="sxs-lookup"><span data-stu-id="595e0-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="595e0-123">**X DO NOT** esistono membri pubblici che restituiscono eccezioni come valore restituito o un `out` parametro.</span><span class="sxs-lookup"><span data-stu-id="595e0-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="595e0-124">Restituzione di eccezioni da API pubbliche anziché generare li vanifica molti dei vantaggi di segnalazione degli errori basata sulle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="595e0-125">**✓ CONSIDER** utilizzando metodi del generatore di eccezione.</span><span class="sxs-lookup"><span data-stu-id="595e0-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="595e0-126">È comune per la stessa eccezione da posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="595e0-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="595e0-127">Per evitare il sovraccarico del codice, utilizzare i metodi di supporto che creano le eccezioni e inizializzano le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="595e0-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="595e0-128">Inoltre, i membri che vengono generate eccezioni non vengono resi inline.</span><span class="sxs-lookup"><span data-stu-id="595e0-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="595e0-129">Spostare l'istruzione throw all'interno del generatore potrebbe consentire il membro sia impostato come inline.</span><span class="sxs-lookup"><span data-stu-id="595e0-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="595e0-130">**X DO NOT** generare eccezioni da blocchi di filtro eccezioni.</span><span class="sxs-lookup"><span data-stu-id="595e0-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="595e0-131">Quando un filtro eccezioni genera un'eccezione, l'eccezione viene intercettata da CLR e il filtro restituisce false.</span><span class="sxs-lookup"><span data-stu-id="595e0-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="595e0-132">Questo comportamento non è distinguibile dal filtro di esecuzione e la restituzione di false in modo esplicito ed è pertanto molto difficile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="595e0-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="595e0-133">**X AVOID** in modo esplicito la generazione di eccezioni da blocchi finally.</span><span class="sxs-lookup"><span data-stu-id="595e0-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="595e0-134">Le eccezioni generate in modo implicito risultante dalla chiamata ai metodi che generano sono accettabili.</span><span class="sxs-lookup"><span data-stu-id="595e0-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="595e0-135">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="595e0-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="595e0-136">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="595e0-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595e0-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="595e0-137">See also</span></span>

- [<span data-ttu-id="595e0-138">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="595e0-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="595e0-139">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="595e0-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
