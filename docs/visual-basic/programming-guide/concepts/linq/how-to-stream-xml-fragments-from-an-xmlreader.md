---
title: 'Procedura: Stream frammenti XML da un XmlReader (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
ms.openlocfilehash: 8c5aa1afff983f3763bbf7c74268eba622df7751
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614896"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>Procedura: Stream frammenti XML da un XmlReader (Visual Basic)
Quando è necessario elaborare file XML di grandi dimensioni, potrebbe risultare impossibile caricare in memoria l'intero albero XML. In questo argomento viene illustrato come generare il flusso di frammenti tramite <xref:System.Xml.XmlReader>.  
  
 Uno dei modi più efficaci per usare un oggetto <xref:System.Xml.XmlReader> per leggere oggetti <xref:System.Xml.Linq.XElement> consiste nello scrivere un metodo dell'asse personalizzato. Un metodo dell'asse restituisce in genere una raccolta, ad esempio <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, come illustrato nell'esempio di questo argomento. Nel metodo dell'asse personalizzato, dopo avere creato il frammento XML chiamando il metodo <xref:System.Xml.Linq.XNode.ReadFrom%2A>, restituire la raccolta usando `yield return`. In questo modo si fornisce la semantica di esecuzione posticipata al metodo dell'asse personalizzato.  
  
 Quando si crea un albero XML da un oggetto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> deve essere posizionato su un elemento. Il metodo <xref:System.Xml.Linq.XNode.ReadFrom%2A> restituisce risultati solo dopo aver letto il tag di chiusura dell'elemento.  
  
 Se si desidera creare un albero parziale, è possibile creare un'istanza di <xref:System.Xml.XmlReader>, posizionare il lettore sul nodo da convertire in un albero <xref:System.Xml.Linq.XElement> e quindi creare l'oggetto <xref:System.Xml.Linq.XElement>.  
  
 L'argomento [Procedura: Stream frammenti XML con accesso a informazioni di intestazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contiene informazioni e un esempio su come trasmettere un documento più complesso.  
  
 L'argomento [Procedura: Eseguire lo Streaming trasformare di grandi dimensioni documenti XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un esempio dell'utilizzo di LINQ to XML per trasformare documenti XML di dimensioni estremamente grandi mantenendo un footprint di memoria di piccole dimensioni.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene creato un metodo dell'asse personalizzato. È possibile sottoporlo a query tramite una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Il metodo dell'asse personalizzato `StreamRootChildDoc` è progettato specificamente per leggere un documento contenente un elemento `Child` ripetuto.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim markup = "<Root>" &  
                     "  <Child Key=""01"">" &  
                     "    <GrandChild>aaa</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""02"">" &  
                     "    <GrandChild>bbb</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""03"">" &  
                     "    <GrandChild>ccc</GrandChild>" &  
                     "  </Child>" &  
                     "</Root>"  
  
        Dim grandChildData =  
             From el In New StreamRootChildDoc(New IO.StringReader(markup))  
             Where CInt(el.@Key) > 1  
             Select el.<GrandChild>.Value  
  
        For Each s In grandChildData  
            Console.WriteLine(s)  
        Next  
    End Sub  
End Module  
  
Public Class StreamRootChildDoc  
    Implements IEnumerable(Of XElement)  
  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamChildEnumerator(_stringReader)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamChildEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _reader As Xml.XmlReader  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        While _reader.Read()  
            Select Case _reader.NodeType  
                Case Xml.XmlNodeType.Element  
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)  
                    If el IsNot Nothing Then  
                        _current = el  
                        Return True  
                    End If  
            End Select  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 Questo esempio produce il seguente output:  
  
```  
bbb  
ccc  
```  
  
 In questo esempio il documento di origine è molto piccolo. Tuttavia, anche contenesse milioni di elementi `Child`, il footprint di memoria di questo esempio sarebbe comunque ridotto.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Implementazione IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)
- [Analisi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
