---
title: Interpolazione di stringhe - Esercitazione su C#
description: Questa esercitazione mostra come usare la funzionalità di interpolazione di stringhe di C# per includere risultati di espressioni formattate in una stringa più grande.
author: rpetrusha
ms.author: ronpet
ms.date: 10/23/2018
ms.openlocfilehash: 97773659ea7dd00c291aa6a96401cac531adfdc8
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2019
ms.locfileid: "58921373"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a><span data-ttu-id="31698-103">Usare l'interpolazione di stringhe per la costruzione di stringhe formattate</span><span class="sxs-lookup"><span data-stu-id="31698-103">Use string interpolation to construct formatted strings</span></span>

<span data-ttu-id="31698-104">Questa esercitazione descrive come usare l'[interpolazione di stringhe](../../language-reference/tokens/interpolated.md) in C# per inserire i valori in un'unica stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="31698-104">This tutorial teaches you how to use C# [string interpolation](../../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="31698-105">Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="31698-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="31698-106">L'esercitazione contiene una serie di lezioni che descrivono come inserire valori in una stringa e formattare questi valori in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="31698-106">The tutorial contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="31698-107">Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="31698-107">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="31698-108">L'argomento [Get started with .NET in 10 minutes](https://www.microsoft.com/net/core) (Iniziare a usare .NET in 10 minuti) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="31698-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="31698-109">È anche possibile completare la [versione interattiva](interpolated-strings.yml) di questa esercitazione nel browser.</span><span class="sxs-lookup"><span data-stu-id="31698-109">You also can complete the [interactive version](interpolated-strings.yml) of this tutorial in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="31698-110">Creare una stringa interpolata</span><span class="sxs-lookup"><span data-stu-id="31698-110">Create an interpolated string</span></span>

<span data-ttu-id="31698-111">Creare una directory denominata **interpolated**.</span><span class="sxs-lookup"><span data-stu-id="31698-111">Create a directory named **interpolated**.</span></span> <span data-ttu-id="31698-112">Impostarla come directory corrente ed eseguire il comando seguente da una finestra della console:</span><span class="sxs-lookup"><span data-stu-id="31698-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="31698-113">Questo comando crea una nuova applicazione console .NET Core nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="31698-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="31698-114">Aprire **Program.cs** nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente, sostituendo `<name>` con il nome:</span><span class="sxs-lookup"><span data-stu-id="31698-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="31698-115">Per provare questo codice, digitare `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="31698-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="31698-116">Quando si esegue il programma viene visualizzata un'unica stringa contenente un messaggio di saluto che include il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="31698-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="31698-117">La stringa inclusa nella chiamata al metodo <xref:System.Console.WriteLine%2A> è una *stringa interpolata*.</span><span class="sxs-lookup"><span data-stu-id="31698-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="31698-118">Si tratta di un tipo di modello che consente di costruire un'unica stringa detta *stringa di risultato* da una stringa che include codice incorporato.</span><span class="sxs-lookup"><span data-stu-id="31698-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="31698-119">Le stringhe interpolate sono particolarmente utili per inserire valori in una stringa o per concatenare (unire) più stringhe.</span><span class="sxs-lookup"><span data-stu-id="31698-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="31698-120">Questo semplice esempio contiene i due elementi che devono essere presenti in ogni stringa interpolata:</span><span class="sxs-lookup"><span data-stu-id="31698-120">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="31698-121">Un valore letterale stringa che inizia con il carattere `$` prima delle virgolette inglesi aperte.</span><span class="sxs-lookup"><span data-stu-id="31698-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="31698-122">Tra il simbolo `$` e le virgolette non devono essere presenti spazi.</span><span class="sxs-lookup"><span data-stu-id="31698-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="31698-123">Se si vuole vedere cosa accade se ne viene incluso uno, inserire uno spazio dopo il carattere `$`, salvare il file ed eseguire nuovamente il programma digitando `dotnet run` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="31698-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="31698-124">Il compilatore C# visualizza un messaggio di errore CS1056 per segnalare che il carattere "$" non è previsto.</span><span class="sxs-lookup"><span data-stu-id="31698-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="31698-125">Una o più *espressioni interpolate*.</span><span class="sxs-lookup"><span data-stu-id="31698-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="31698-126">Un'espressione interpolata è indicata tra parentesi graffe di apertura e chiusura (`{` e `}`).</span><span class="sxs-lookup"><span data-stu-id="31698-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="31698-127">All'interno delle parentesi graffe è possibile inserire qualsiasi espressione C# che restituisce un valore, incluso `null`.</span><span class="sxs-lookup"><span data-stu-id="31698-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="31698-128">Ora si proveranno altri esempi di interpolazione di stringhe con altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="31698-128">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="31698-129">Includere tipi di dati diversi</span><span class="sxs-lookup"><span data-stu-id="31698-129">Include different data types</span></span>

<span data-ttu-id="31698-130">Nella sezione precedente è stata usata l'interpolazione di stringhe per inserire una stringa in un'altra.</span><span class="sxs-lookup"><span data-stu-id="31698-130">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="31698-131">Il risultato di un'espressione interpolata può avere qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="31698-131">The result of an interpolated expression can be of any data type, though.</span></span> <span data-ttu-id="31698-132">Includiamo valori di vari tipi di dati in una stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="31698-132">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="31698-133">Nell'esempio seguente viene definito prima di tutto un tipo di dati [class](../../programming-guide/classes-and-structs/classes.md) `Vegetable` con la [proprietà](../../properties.md) `Name` e un [metodo](../../methods.md) `ToString` che esegue l'[override](../../language-reference/keywords/override.md) del comportamento del metodo <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31698-133">In the following example, we first define a [class](../../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has a `Name` [property](../../properties.md) and a `ToString` [method](../../methods.md), which [overrides](../../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="31698-134">Il [modificatore di accesso `public`](../../language-reference/keywords/public.md)rende tale metodo disponibile per qualsiasi codice client per ottenere la rappresentazione stringa di un'istanza di `Vegetable`.</span><span class="sxs-lookup"><span data-stu-id="31698-134">The [`public` access modifier](../../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="31698-135">Nell'esempio il metodo `Vegetable.ToString` restituisce il valore della proprietà `Name` inizializzata nel [costruttore](../../programming-guide/classes-and-structs/constructors.md) `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="31698-135">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="31698-136">Viene quindi creata un'istanza della classe `Vegetable` denominata `item` usando la [parola chiave `new`](../../language-reference/keywords/new-operator.md) e specificando un nome per il costruttore `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="31698-136">Then we create an instance of the `Vegetable` class named `item` by using the [`new` keyword](../../language-reference/keywords/new-operator.md) and providing a name for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="31698-137">Infine, includere la variabile `item` in una stringa interpolata che contenga anche un valore <xref:System.DateTime>, un valore <xref:System.Decimal> e un valore di [enumerazione](../../programming-guide/enumeration-types.md)`Unit`.</span><span class="sxs-lookup"><span data-stu-id="31698-137">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="31698-138">Sostituire tutto il codice C# in un editor con il codice seguente e usare il comando `dotnet run` per l'eseguirlo:</span><span class="sxs-lookup"><span data-stu-id="31698-138">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```

<span data-ttu-id="31698-139">L'espressione interpolata `item` nella stringa interpolata restituisce il testo "eggplant" nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="31698-139">Note that the interpolated expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="31698-140">Questo accade perché, quando il tipo di risultato dell'espressione non è una stringa, il risultato restituisce una stringa nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="31698-140">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="31698-141">Se l'espressione interpolata restituisce `null`, viene usata una stringa vuota ("" o <xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="31698-141">If the interpolated expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="31698-142">Se l'espressione interpolata non restituisce `null`, in genere viene chiamato il metodo `ToString` del tipo di risultato.</span><span class="sxs-lookup"><span data-stu-id="31698-142">If the interpolated expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="31698-143">È possibile testare questo processo aggiornando l'implementazione del metodo `Vegetable.ToString`.</span><span class="sxs-lookup"><span data-stu-id="31698-143">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="31698-144">Potrebbe anche non essere necessario implementare il metodo `ToString`, poiché ogni tipo prevede un'implementazione di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="31698-144">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="31698-145">Per il test di questo funzionamento, impostare come commento la definizione del metodo `Vegetable.ToString` nell'esempio (facendola precedere dal simbolo di commento `//`).</span><span class="sxs-lookup"><span data-stu-id="31698-145">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="31698-146">Nell'output la stringa "eggplant" viene sostituita dal nome completo del tipo ("Vegetable" in questo esempio), ovvero il comportamento predefinito del metodo <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31698-146">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="31698-147">Il comportamento predefinito del metodo `ToString` per un tipo di enumerazione prevede la restituzione della rappresentazione stringa di un valore usato nella definizione dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="31698-147">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="31698-148">Nell'output di questo esempio la data è troppo precisa (il prezzo delle melanzane non varia ogni secondo) e il valore del prezzo non indica una valuta.</span><span class="sxs-lookup"><span data-stu-id="31698-148">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="31698-149">Nella sezione successiva si apprenderà come risolvere questi problemi controllando la formattazione delle rappresentazioni di stringa dei risultati delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="31698-149">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="31698-150">Controllare la formattazione delle espressioni interpolate</span><span class="sxs-lookup"><span data-stu-id="31698-150">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="31698-151">Nella sezione precedente sono state inserite nella stringa di risultato due stringhe con formattazione non valida.</span><span class="sxs-lookup"><span data-stu-id="31698-151">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="31698-152">Il primo problema è un valore di data e ora nel quale solo la data risultava corretta.</span><span class="sxs-lookup"><span data-stu-id="31698-152">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="31698-153">Il secondo è un prezzo che non indica la valuta.</span><span class="sxs-lookup"><span data-stu-id="31698-153">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="31698-154">Entrambi i problemi sono di facile risoluzione.</span><span class="sxs-lookup"><span data-stu-id="31698-154">Both issues are easy to address.</span></span> <span data-ttu-id="31698-155">L'interpolazione di stringhe consente di specificare *stringhe di formato* che controllano la formattazione di determinati tipi.</span><span class="sxs-lookup"><span data-stu-id="31698-155">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="31698-156">Modificare la chiamata in `Console.WriteLine` dell'esempio precedente in modo da includere le stringhe di formato per le espressioni di data e prezzo, come indicato nella riga seguente:</span><span class="sxs-lookup"><span data-stu-id="31698-156">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="31698-157">Per specificare una stringa di formato, far seguire all'espressione interpolata i due punti (":") e la stringa di formato desiderata.</span><span class="sxs-lookup"><span data-stu-id="31698-157">You specify a format string by following the interpolated expression with a colon (":") and the format string.</span></span> <span data-ttu-id="31698-158">"d" è un [stringa di formato data e ora standard](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) che rappresenta il formato di data breve.</span><span class="sxs-lookup"><span data-stu-id="31698-158">"d" is a [standard date and time format string](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="31698-159">"C2" è un [stringa di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) che rappresenta un numero come valore di valuta con due cifre dopo il separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="31698-159">"C2" is a  [standard numeric format string](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="31698-160">Molti tipi delle librerie .NET supportano un set predefinito di stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="31698-160">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="31698-161">Tali tipi includono tutti i tipi numerici e i tipi data e ora.</span><span class="sxs-lookup"><span data-stu-id="31698-161">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="31698-162">Per l'elenco completo dei tipi che supportano le stringhe di formato, vedere [Stringhe di formato e tipi della libreria di classe .NET](../../../standard/base-types/formatting-types.md#stringRef) nell'articolo [Formattazione di tipi in .NET](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="31698-162">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="31698-163">Provare a modificare le stringhe di formato nell'editor di testo ed eseguire nuovamente il programma ogni volta che si apporta una modifica, per verificare l'effetto delle modifiche sulla formattazione di data, ora e valore numerico.</span><span class="sxs-lookup"><span data-stu-id="31698-163">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="31698-164">Modificare il valore "d" in `{date:d}` inserendo i valori "t" (per visualizzare il formato ora breve), "y" (per visualizzare anno e mese) e "yyyy" (per visualizzare l'anno come numero a quattro cifre).</span><span class="sxs-lookup"><span data-stu-id="31698-164">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="31698-165">Modificare "C2" in `{price:C2}` inserendo "e" (per la notazione esponenziale) e "F3" (per un valore numerico con tre cifre dopo il separatore decimale).</span><span class="sxs-lookup"><span data-stu-id="31698-165">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="31698-166">Oltre alla formattazione è possibile controllare la larghezza del campo e l'allineamento delle stringhe formattate incluse nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="31698-166">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="31698-167">La sezione successiva spiega come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="31698-167">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="31698-168">Controllare la larghezza del campo e l'allineamento delle espressioni interpolate</span><span class="sxs-lookup"><span data-stu-id="31698-168">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="31698-169">In genere quando il risultato di un'espressione interpolata è formattato in una stringa, questa viene inclusa in una stringa di risultato senza spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="31698-169">Ordinarily, when the result of an interpolated expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="31698-170">In particolare quando si usa un set di dati, la possibilità di controllare la larghezza di un campo e l'allineamento del testo consente di generare un output più leggibile.</span><span class="sxs-lookup"><span data-stu-id="31698-170">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="31698-171">Per verificare, sostituire tutto il codice nell'editor di testo con il codice seguente e digitare `dotnet run` per eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="31698-171">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

<span data-ttu-id="31698-172">I nomi degli autori vengono allineati a sinistra e i titoli da loro scritti sono allineati a destra.</span><span class="sxs-lookup"><span data-stu-id="31698-172">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="31698-173">Per specificare l'allineamento, aggiungere una virgola (",") dopo un'espressione interpolata e indicare la larghezza *minima* del campo.</span><span class="sxs-lookup"><span data-stu-id="31698-173">You specify the alignment by adding a comma (",") after an interpolated expression and designating the *minimum* field width.</span></span> <span data-ttu-id="31698-174">Se il valore specificato è un numero positivo, il campo è allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="31698-174">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="31698-175">Se è un numero negativo, il campo è allineato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="31698-175">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="31698-176">Provare a rimuovere il segno negativo dal codice `{"Author",-25}` e `{title.Key,-25}` ed eseguire di nuovo l'esempio, come indicato dal codice seguente:</span><span class="sxs-lookup"><span data-stu-id="31698-176">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="31698-177">Questa volta le informazioni sull'autore sono allineate a destra.</span><span class="sxs-lookup"><span data-stu-id="31698-177">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="31698-178">È possibile combinare un identificatore di allineamento e una stringa di formato per un'unica espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="31698-178">You can combine an alignment specifier and a format string for a single interpolated expression.</span></span> <span data-ttu-id="31698-179">A tale scopo, specificare prima l'allineamento, seguito da due punti e dalla stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="31698-179">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="31698-180">Sostituire tutto il codice nel metodo `Main` con il codice seguente, che consente di visualizzare tre stringhe formattate con le larghezze di campo definite.</span><span class="sxs-lookup"><span data-stu-id="31698-180">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="31698-181">A questo punto eseguire il programma immettendo il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="31698-181">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="31698-182">L'output è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="31698-182">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="31698-183">È stata completata l'esercitazione sull'interpolazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="31698-183">You've completed the string interpolation tutorial.</span></span>

<span data-ttu-id="31698-184">Per altre informazioni, vedere l'argomento [Interpolazione di stringhe](../../language-reference/tokens/interpolated.md) e l'esercitazione [Interpolazione di stringhe in C#](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="31698-184">For more information, see the [String interpolation](../../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial.</span></span>