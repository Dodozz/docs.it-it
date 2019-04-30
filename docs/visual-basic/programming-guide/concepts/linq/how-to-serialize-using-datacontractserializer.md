---
title: 'Procedura: Serializzare tramite DataContractSerializer (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: ecaea518-8a0f-4249-b4e5-9b3fb0cdd8ad
ms.openlocfilehash: 9593dede3eb29aadc7ffb494e1d728cb8e679f0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054432"
---
# <a name="how-to-serialize-using-datacontractserializer-visual-basic"></a><span data-ttu-id="eef3a-102">Procedura: Serializzare tramite DataContractSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eef3a-102">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>
<span data-ttu-id="eef3a-103">In questo argomento viene illustrato un esempio in cui viene usato <xref:System.Runtime.Serialization.DataContractSerializer> per eseguire la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="eef3a-103">This topic shows an example that serializes and deserializes using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eef3a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="eef3a-104">Example</span></span>  
 <span data-ttu-id="eef3a-105">Nell'esempio seguente vengono creati diversi oggetti contenenti oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="eef3a-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="eef3a-106">Tali oggetti vengono quindi serializzati in file di testo e successivamente deserializzati dagli stessi file di testo.</span><span class="sxs-lookup"><span data-stu-id="eef3a-106">It then serializes them to text files, and then deserializes them from the text files.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Linq  
Imports System.IO  
Imports System.Runtime.Serialization  
  
Public Class XLinqTest  
    Shared Sub Main()  
        Test(Of XElement)(CreateXElement())  
        Test(Of XElementContainer)(New XElementContainer())  
        Test(Of XElementNullContainer)(New XElementNullContainer())  
    End Sub  
  
    Public Shared Sub Test(Of T)(ByRef obj)  
        Dim s As DataContractSerializer = New DataContractSerializer(GetType(T))  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Create)  
            Console.WriteLine("Testing for type: {0}", GetType(T))  
            s.WriteObject(fs, obj)  
        End Using  
  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Open)  
            Dim s2 As Object = s.ReadObject(fs)  
            If s2 Is Nothing Then  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)")  
            Else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType())  
            End If  
        End Using  
    End Sub  
  
    Public Shared Function CreateXElement() As XElement  
        Return New XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"))  
    End Function  
End Class  
  
<DataContract()> _  
Public Class XElementContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementContainer()  
        member = XLinqTest.CreateXElement()  
    End Sub  
End Class  
  
<DataContract()> _  
Public Class XElementNullContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementNullContainer()  
        member = Nothing  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="eef3a-107">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="eef3a-107">This example produces the following output:</span></span>  
  
```  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="eef3a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eef3a-108">See also</span></span>

- [<span data-ttu-id="eef3a-109">Serializzazione di oggetti grafici contenenti oggetti XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eef3a-109">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)
