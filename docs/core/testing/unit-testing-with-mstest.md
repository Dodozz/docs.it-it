---
title: Testing unità di C# con MSTest e .NET Core
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e MSTest.
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.openlocfilehash: 1c2b0bdd4bf76a17217db0c98b8f951f7d58f2ea
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183776"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="3f9c7-103">Testing unità di C# con MSTest e .NET Core</span><span class="sxs-lookup"><span data-stu-id="3f9c7-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="3f9c7-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="3f9c7-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="3f9c7-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="3f9c7-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="3f9c7-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="3f9c7-107">Creating the source project</span></span>

<span data-ttu-id="3f9c7-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-108">Open a shell window.</span></span> <span data-ttu-id="3f9c7-109">Creare una directory denominata *unit-testing-using-mstest* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="3f9c7-110">In questa nuova directory, eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare un nuovo file di soluzione per la libreria di classi e il progetto di test.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="3f9c7-111">Creare quindi una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="3f9c7-112">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-112">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="3f9c7-113">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="3f9c7-114">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="3f9c7-115">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-115">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

<span data-ttu-id="3f9c7-116">Tornare alla directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="3f9c7-117">Eseguire [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="3f9c7-118">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="3f9c7-118">Creating the test project</span></span>

<span data-ttu-id="3f9c7-119">Creare quindi la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="3f9c7-120">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="3f9c7-121">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="3f9c7-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="3f9c7-122">Il comando dotnet new crea un progetto di test che usa MSTest come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-122">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="3f9c7-123">Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="3f9c7-124">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="3f9c7-125">Nel passaggio precedente `dotnet new` ha aggiunto l'SDK MSTest, il framework di test MSTest e il Test Runner MSTest.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="3f9c7-126">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="3f9c7-127">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="3f9c7-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="3f9c7-128">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="3f9c7-129">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-129">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="3f9c7-130">Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="3f9c7-131">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="3f9c7-131">Creating the first test</span></span>

<span data-ttu-id="3f9c7-132">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="3f9c7-133">Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="3f9c7-134">L'attributo `[TestClass]` indica una classe che contiene unit test.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-134">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="3f9c7-135">L'attributo `[TestMethod]` indica che il metodo è un metodo di test.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-135">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="3f9c7-136">Salvare questo file ed eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="3f9c7-137">Il Test Runner di MSTest include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="3f9c7-138">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="3f9c7-139">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-139">Your test fails.</span></span> <span data-ttu-id="3f9c7-140">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="3f9c7-141">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="3f9c7-142">Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="3f9c7-143">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="3f9c7-144">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="3f9c7-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="3f9c7-145">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-145">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="3f9c7-146">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="3f9c7-146">Adding more features</span></span>

<span data-ttu-id="3f9c7-147">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="3f9c7-148">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="3f9c7-149">È possibile aggiungere nuovi test con l'attributo `[TestMethod]`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-149">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="3f9c7-150">Sono disponibili altri attributi di MSTest che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="3f9c7-151">Un attributo `[DataTestMethod]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-151">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="3f9c7-152">È possibile usare l'attributo `[DataRow]` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-152">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="3f9c7-153">Anziché creare nuovi test, applicare questi due attributi per creare un singolo test basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="3f9c7-154">Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="3f9c7-155">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="3f9c7-156">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="3f9c7-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="3f9c7-157">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="3f9c7-158">Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="3f9c7-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="3f9c7-159">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="3f9c7-160">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="3f9c7-161">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3f9c7-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
