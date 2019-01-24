---
title: 'Procedura: Proiettare un nuovo tipo (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: 5d0679c3c6f1fa26408905799f5b7a5d0cef6266
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592098"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="8a5da-102">Procedura: Proiettare un nuovo tipo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a5da-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="8a5da-103">Negli altri esempi di questa sezione sono state illustrate query che restituiscono risultati sotto forma di <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> di `string` e <xref:System.Collections.Generic.IEnumerable%601> di `int`.</span><span class="sxs-lookup"><span data-stu-id="8a5da-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="8a5da-104">Si tratta di tipi di risultati comuni, ma non sono appropriati per tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="8a5da-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="8a5da-105">In molti casi le query dovranno restituire un oggetto <xref:System.Collections.Generic.IEnumerable%601> di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="8a5da-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a5da-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a5da-106">Example</span></span>  
 <span data-ttu-id="8a5da-107">In questo esempio viene illustrato come creare istanze di oggetti nella clausola `Select`.</span><span class="sxs-lookup"><span data-stu-id="8a5da-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="8a5da-108">Nel codice viene innanzitutto definita una nuova classe con un costruttore, quindi viene modificata l'istruzione `Select` in modo che l'espressione sia una nuova istanza della nuova classe.</span><span class="sxs-lookup"><span data-stu-id="8a5da-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="8a5da-109">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: Ordine di acquisto tipico (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8a5da-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="8a5da-110">Questo esempio Usa la `M:System.Xml.Linq.XElement.Element` metodo che è stato introdotto nell'argomento [come: Recuperare un singolo elemento figlio (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8a5da-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="8a5da-111">Vengono inoltre usati i cast per recuperare i valori degli elementi restituiti dal metodo `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="8a5da-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="8a5da-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8a5da-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a5da-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a5da-113">See also</span></span>
- [<span data-ttu-id="8a5da-114">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a5da-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
