---
title: Iteratori (Visual Basic)
ms.date: 07/20/2015
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
ms.openlocfilehash: 73561cf5bed583e2dbf853b7771b9e949a5c0267
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642279"
---
# <a name="iterators-visual-basic"></a>Iteratori (Visual Basic)
Un *iteratore* può essere usato per scorrere le raccolte come gli elenchi e le matrici.  
  
 Un metodo iteratore o funzione di accesso `get` esegue un'iterazione personalizzata su una raccolta. Un iteratore Usa il [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento uno alla volta. Quando viene raggiunta un'istruzione `Yield`, la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Si usa un metodo iteratore dal codice client usando un [For Each... Avanti](../../../visual-basic/language-reference/statements/for-each-next-statement.md) istruzione, oppure usando una query LINQ.  
  
 Nell'esempio seguente, la prima iterazione del ciclo `For Each` fa procedere l'esecuzione nel metodo iteratore `SomeNumbers` fino al raggiungimento della prima istruzione `Yield`. Questa iterazione restituisce un valore pari a 3 e viene mantenuta la posizione corrente nel metodo iteratore. All'iterazione successiva del ciclo, l'esecuzione nel metodo iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`. Questa iterazione restituisce un valore pari a 5 e viene ancora mantenuta la posizione corrente nel metodo iteratore. Il ciclo termina quando si raggiunge la fine del metodo iteratore.  
  
```vb  
Sub Main()  
    For Each number As Integer In SomeNumbers()  
        Console.Write(number & " ")  
    Next  
    ' Output: 3 5 8  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function SomeNumbers() As System.Collections.IEnumerable  
    Yield 3  
    Yield 5  
    Yield 8  
End Function  
```  
  
 Il tipo restituito di un metodo iteratore o di una funzione di accesso `get` può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 È possibile usare un `Exit Function` o `Return` istruzione per terminare l'iterazione.  
  
 Una funzione di iteratore di Visual Basic o `get` dichiarazione di funzione di accesso include un' [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) modificatore.  
  
 Gli iteratori sono stati introdotti in Visual Basic in Visual Studio 2012.  
  
 **In questo argomento**  
  
- [Iteratore semplice](#BKMK_SimpleIterator)  
  
- [Creazione di una classe Collection](#BKMK_CollectionClass)  
  
- [Blocchi try](#BKMK_TryBlocks)  
  
- [Metodi anonimi](#BKMK_AnonymousMethods)  
  
- [Uso di iteratori con un elenco generico](#BKMK_GenericList)  
  
- [Informazioni sulla sintassi](#BKMK_SyntaxInformation)  
  
- [Implementazione tecnica](#BKMK_Technical)  
  
- [Uso degli iteratori](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  Per tutti gli esempi in questo argomento, ad eccezione di esempio di iteratore semplice, includere [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) istruzioni per il `System.Collections` e `System.Collections.Generic` gli spazi dei nomi.  
  
## <a name="BKMK_SimpleIterator"></a> Iteratore semplice  
 Nell'esempio seguente ha un unico `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo. In `Main` ogni iterazione del corpo dell'istruzione `For Each` crea una chiamata alla funzione iteratore, che procede all'istruzione `Yield` successiva.  
  
```vb  
Sub Main()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    ' Output: 6 8 10 12 14 16 18  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As System.Collections.Generic.IEnumerable(Of Integer)  
  
    ' Yield even numbers in the range.  
    For number As Integer = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
## <a name="BKMK_CollectionClass"></a> Creazione di una classe Collection  
 Nell'esempio seguente la classe `DaysOfTheWeek` implementa l'interfaccia <xref:System.Collections.IEnumerable>, che richiede un metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Il compilatore chiama implicitamente il metodo `GetEnumerator`, che restituisce un <xref:System.Collections.IEnumerator>.  
  
 Il `GetEnumerator` metodo restituisce una stringa alla volta usando il `Yield` istruzione e un `Iterator` modificatore è nella dichiarazione di funzione.  
  
```vb  
Sub Main()  
    Dim days As New DaysOfTheWeek()  
    For Each day As String In days  
        Console.Write(day & " ")  
    Next  
    ' Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey()  
End Sub  
  
Private Class DaysOfTheWeek  
    Implements IEnumerable  
  
    Public days =  
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        ' Yield each day of the week.  
        For i As Integer = 0 To days.Length - 1  
            Yield days(i)  
        Next  
    End Function  
End Class  
```  
  
 Nell'esempio seguente viene creata una classe `Zoo` che contiene una raccolta di animali.  
  
 L'istruzione `For Each` che fa riferimento all'istanza della classe (`theZoo`) chiama implicitamente il metodo `GetEnumerator`. Le istruzioni `For Each` che fanno riferimento alle proprietà `Birds` e `Mammals` usano il metodo iteratore denominato `AnimalsForType`.  
  
```vb  
Sub Main()  
    Dim theZoo As New Zoo()  
  
    theZoo.AddMammal("Whale")  
    theZoo.AddMammal("Rhinoceros")  
    theZoo.AddBird("Penguin")  
    theZoo.AddBird("Warbler")  
  
    For Each name As String In theZoo  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros Penguin Warbler  
  
    For Each name As String In theZoo.Birds  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Penguin Warbler  
  
    For Each name As String In theZoo.Mammals  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros  
  
    Console.ReadKey()  
End Sub  
  
Public Class Zoo  
    Implements IEnumerable  
  
    ' Private members.  
    Private animals As New List(Of Animal)  
  
    ' Public methods.  
    Public Sub AddMammal(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})  
    End Sub  
  
    Public Sub AddBird(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})  
    End Sub  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        For Each theAnimal As Animal In animals  
            Yield theAnimal.Name  
        Next  
    End Function  
  
    ' Public members.  
    Public ReadOnly Property Mammals As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Mammal)  
        End Get  
    End Property  
  
    Public ReadOnly Property Birds As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Bird)  
        End Get  
    End Property  
  
    ' Private methods.  
    Private Iterator Function AnimalsForType( _  
    ByVal type As Animal.TypeEnum) As IEnumerable  
        For Each theAnimal As Animal In animals  
            If (theAnimal.Type = type) Then  
                Yield theAnimal.Name  
            End If  
        Next  
    End Function  
  
    ' Private class.  
    Private Class Animal  
        Public Enum TypeEnum  
            Bird  
            Mammal  
        End Enum  
  
        Public Property Name As String  
        Public Property Type As TypeEnum  
    End Class  
End Class  
```  
  
## <a name="BKMK_TryBlocks"></a> Blocchi try  
 Visual Basic consente una `Yield` istruzione nel `Try` blocco di un [prova... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Oggetto `Try` blocco che ha un `Yield` istruzione può avere `Catch` blocca e può avere un `Finally` blocco.  
  
 L'esempio seguente include `Try`, `Catch`, e `Finally` blocchi in una funzione iteratore. Il `Finally` blocco nella funzione iteratore viene eseguito prima il `For Each` al termine dell'iterazione.  
  
```vb  
Sub Main()  
    For Each number As Integer In Test()  
        Console.WriteLine(number)  
    Next  
    Console.WriteLine("For Each is done.")  
  
    ' Output:  
    '  3  
    '  4  
    '  Something happened. Yields are done.  
    '  Finally is called.  
    '  For Each is done.  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function Test() As IEnumerable(Of Integer)  
    Try  
        Yield 3  
        Yield 4  
        Throw New Exception("Something happened. Yields are done.")  
        Yield 5  
        Yield 6  
    Catch ex As Exception  
        Console.WriteLine(ex.Message)  
    Finally  
        Console.WriteLine("Finally is called.")  
    End Try  
End Function  
```  
  
 Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.  
  
 Se il `For Each` corpo (anziché il metodo iteratore) genera un'eccezione, una `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` try nella funzione iteratore. Oggetto `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.  
  
## <a name="BKMK_AnonymousMethods"></a> Metodi anonimi  
 In Visual Basic, una funzione anonima può essere una funzione iteratore. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim iterateSequence = Iterator Function() _  
                      As IEnumerable(Of Integer)  
                          Yield 1  
                          Yield 2  
                      End Function  
  
For Each number As Integer In iterateSequence()  
    Console.Write(number & " ")  
Next  
' Output: 1 2  
Console.ReadKey()  
```  
  
 L'esempio seguente include un metodo iteratore non convalida gli argomenti. Il metodo restituisce il risultato di un iteratore di tipo anonimo che descrive gli elementi della raccolta.  
  
```vb  
Sub Main()  
    For Each number As Integer In GetSequence(5, 10)  
        Console.Write(number & " ")  
    Next  
    ' Output: 5 6 7 8 9 10  
    Console.ReadKey()  
End Sub  
  
Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _  
As IEnumerable  
    ' Validate the arguments.  
    If low < 1 Then  
        Throw New ArgumentException("low is too low")  
    End If  
    If high > 140 Then  
        Throw New ArgumentException("high is too high")  
    End If  
  
    ' Return an anonymous iterator function.  
    Dim iterateSequence = Iterator Function() As IEnumerable  
                              For index = low To high  
                                  Yield index  
                              Next  
                          End Function  
    Return iterateSequence()  
End Function  
```  
  
 Se la convalida è invece all'interno della funzione iteratore, la convalida non può essere eseguita fino all'avvio della prima iterazione del `For Each` corpo.  
  
## <a name="BKMK_GenericList"></a> Uso di iteratori con un elenco generico  
 Nell'esempio seguente la classe generica `Stack(Of T)` implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>. Il metodo `Push` assegna valori a una matrice di tipo `T`. Il metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> restituisce i valori della matrice tramite l'istruzione `Yield`.  
  
 Oltre al metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> generico, è necessario implementare anche il metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A> non generico, poiché <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable>. L'implementazione non generica rinvia all'implementazione generica.  
  
 L'esempio usa iteratori denominati per supportare diversi modi di iterazione nella stessa raccolta dati. Questi iteratori denominati sono le proprietà `TopToBottom` e `BottomToTop` e il metodo `TopN`.  
  
 Il `BottomToTop` dichiarazione di proprietà contiene il `Iterator` (parola chiave).  
  
```vb  
Sub Main()  
    Dim theStack As New Stack(Of Integer)  
  
    ' Add items to the stack.  
    For number As Integer = 0 To 9  
        theStack.Push(number)  
    Next  
  
    ' Retrieve items from the stack.  
    ' For Each is allowed because theStack implements  
    ' IEnumerable(Of Integer).  
    For Each number As Integer In theStack  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    ' For Each is allowed, because theStack.TopToBottom  
    ' returns IEnumerable(Of Integer).  
    For Each number As Integer In theStack.TopToBottom  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    For Each number As Integer In theStack.BottomToTop  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 0 1 2 3 4 5 6 7 8 9   
  
    For Each number As Integer In theStack.TopN(7)  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey()  
End Sub  
  
Public Class Stack(Of T)  
    Implements IEnumerable(Of T)  
  
    Private values As T() = New T(99) {}  
    Private top As Integer = 0  
  
    Public Sub Push(ByVal t As T)  
        values(top) = t  
        top = top + 1  
    End Sub  
  
    Public Function Pop() As T  
        top = top - 1  
        Return values(top)  
    End Function  
  
    ' This function implements the GetEnumerator method. It allows  
    ' an instance of the class to be used in a For Each statement.  
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _  
        Implements IEnumerable(Of T).GetEnumerator  
  
        For index As Integer = top - 1 To 0 Step -1  
            Yield values(index)  
        Next  
    End Function  
  
    Public Iterator Function GetEnumerator1() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        Yield GetEnumerator()  
    End Function  
  
    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)  
        Get  
            Return Me  
        End Get  
    End Property  
  
    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)  
        Get  
            For index As Integer = 0 To top - 1  
                Yield values(index)  
            Next  
        End Get  
    End Property  
  
    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _  
        As IEnumerable(Of T)  
  
        ' Return less than itemsFromTop if necessary.  
        Dim startIndex As Integer =  
            If(itemsFromTop >= top, 0, top - itemsFromTop)  
  
        For index As Integer = top - 1 To startIndex Step -1  
            Yield values(index)  
        Next  
    End Function  
End Class  
```  
  
## <a name="BKMK_SyntaxInformation"></a> Informazioni sulla sintassi  
 Un iteratore può verificarsi come metodo o funzione di accesso `get`. Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.  
  
 Deve esistere una conversione implicita dal tipo di espressione nell'istruzione `Yield` al tipo restituito dell'iteratore.  
  
 In Visual Basic, un metodo iteratore non può contenere `ByRef` parametri.  
  
 In Visual Basic "Yield" non è una parola riservata e ha un significato speciale solo quando viene usata in un' `Iterator` metodo o `get` della funzione di accesso.  
  
## <a name="BKMK_Technical"></a> Implementazione tecnica  
 Anche se si scrive un iteratore come metodo, il compilatore lo traduce in una classe annidata che, in pratica, è una macchina a stati. Questa classe tiene traccia della posizione dell'iteratore purché il ciclo `For Each...Next` nel codice client sia continuo.  
  
 Per verificare le operazioni eseguite dal compilatore, è possibile usare lo strumento Ildsam.exe per visualizzare il codice Microsoft Intermediate Language generato per un metodo iteratore.  
  
 Quando si crea un iteratore per una [classe](../../../csharp/language-reference/keywords/class.md) oppure [struct](../../../csharp/language-reference/keywords/struct.md), non è necessario implementare l'intera <xref:System.Collections.IEnumerator> interfaccia. Quando il compilatore rileva l'iteratore, genera automaticamente i metodi `Current`, `MoveNext` e `Dispose` dell'interfaccia <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 In ogni iterazione successiva del ciclo `For Each…Next` (o alla chiamata diretta a `IEnumerator.MoveNext`), il corpo di codice iteratore successivo riprende dopo la precedente istruzione `Yield`. L'App continuerà a quella successiva `Yield` istruzione fino a quando non viene raggiunta la fine del corpo dell'iteratore, o fino a un `Exit Function` o `Return` viene rilevata l'istruzione.  
  
 Gli iteratori non supportano il <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> (metodo). Per eseguire di nuovo l'iterazione dall'inizio, è necessario ottenere un nuovo iteratore.  
  
 Per altre informazioni, vedere la [specifiche del linguaggio Visual Basic](../../../visual-basic/reference/language-specification/index.md).  
  
## <a name="BKMK_UseOfIterators"></a> Uso degli iteratori  
 Gli iteratori consentono di mantenere la semplicità di un ciclo `For Each` quando è necessario usare codice complesso per popolare una sequenza di elenco. Ciò può risultare utile per eseguire le operazioni seguenti:  
  
- Modificare la sequenza di elenco dopo la prima iterazione del ciclo `For Each`.  
  
- Evitare il caricamento completo di un elenco di grandi dimensioni prima della prima iterazione di un ciclo `For Each`. Un esempio è un'operazione di recupero di paging per caricare un batch di righe della tabella. Un altro esempio è il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, che implementa gli iteratori all'interno di .NET Framework.  
  
- Incapsulare la generazione dell'elenco nell'iteratore. Nel metodo iteratore è possibile compilare l'elenco e restituire quindi ogni risultato in un ciclo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Istruzione Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
- [Iteratore](../../../visual-basic/language-reference/modifiers/iterator.md)
