---
title: Async (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: ad6d671a45cee7d534347d23963bb5035ecc8dac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802712"
---
# <a name="async-visual-basic"></a>Async (Visual Basic)
Il `Async` modificatore indica che il metodo oppure [espressione lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) che ha modificato è asincrono. Tali metodi sono dette *metodi asincroni*.  
  
 Un metodo asincrono è un modo pratico per eseguire le operazioni potenzialmente di lunga durata senza bloccare il thread del chiamante. Il chiamante del metodo async può riprendere un'operazione senza attendere il fine del metodo async.  
  
> [!NOTE]
>  Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012. Per un'introduzione alla programmazione asincrona, vedere [programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Nell'esempio seguente viene illustrata la struttura di un metodo async. Per convenzione, i nomi dei metodi async terminano con "Async".  
  
```vb  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 In genere, un metodo modificato dal `Async` parola chiave contiene almeno uno [Await](../../../visual-basic/language-reference/modifiers/async.md) espressione o istruzione. Il metodo funziona in modo sincrono fino al primo `Await`, a quel punto viene sospeso finché l'attività di cui si è in attesa non viene completata. Nel frattempo, il controllo viene restituito al chiamante del metodo. Se il metodo non contiene un'espressione o un'istruzione `Await`, il metodo non viene sospeso e viene eseguito come un metodo sincrono. Un avviso del compilatore segnala eventuali metodi asincroni che non contengono `Await` perché questa situazione potrebbe indicare un errore. Per altre informazioni, vedere la [errore del compilatore](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 La parola chiave `Async` è una parola chiave non riservata. È una parola chiave quando si modifica un metodo o un'espressione lambda. In tutti gli altri contesti, viene interpretata come identificatore.  
  
## <a name="return-types"></a>Tipi restituiti  
 Un metodo asincrono è un [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, o un [funzione](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) routine che ha un tipo restituito di <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Il metodo non può dichiarare [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parametri.  
  
 Si specifica `Task(Of TResult)` per il tipo restituito del metodo async se il [restituire](../../../visual-basic/language-reference/statements/return-statement.md) istruzione del metodo include un operando di tipo TResult. Utilizzare `Task` se non viene restituito alcun valore significativo al completamento del metodo. In altre parole, una chiamata al metodo restituisce `Task`, ma quando `Task` viene completato, ogni istruzione `Await` in attesa di `Task` non produce un valore risultante.  
  
 Le subroutine async vengono utilizzate principalmente per definire i gestori eventi in cui è richiesta una procedura `Sub`. Il chiamante di una subroutine async non può attendere il metodo e non può intercettare le eccezioni generate dal metodo.  
  
 Per altre informazioni ed esempi, vedere [Tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene illustrato un gestore eventi async, un'espressione lambda async e un metodo async. Per un esempio completo che usa questi elementi, vedere [procedura dettagliata: Accesso al Web con Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). È possibile scaricare il codice della procedura dettagliata dalla pagina [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per sviluppatori).  
  
```vb  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [Operatore Await](../../../visual-basic/language-reference/operators/await-operator.md)
- [Programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Procedura dettagliata: Accesso al Web con Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
