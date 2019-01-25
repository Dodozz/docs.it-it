---
title: 'Procedura: Scrivere una Query per trovare elementi in base al contesto (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
ms.openlocfilehash: 4921652b5b9c59f767e0477e26987edaf4655897
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708142"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="e52ee-102">Procedura: Scrivere una Query per trovare elementi in base al contesto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e52ee-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="e52ee-103">A volte può essere necessario scrivere una query per selezionare gli elementi in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="e52ee-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="e52ee-104">In questo caso è anche possibile scegliere un filtro basato sugli elementi di pari livello precedenti o successivi</span><span class="sxs-lookup"><span data-stu-id="e52ee-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="e52ee-105">oppure sugli elementi figlio o sui predecessori.</span><span class="sxs-lookup"><span data-stu-id="e52ee-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="e52ee-106">Per ottenere questo risultato, scrivere una query e usare i relativi risultati nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="e52ee-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="e52ee-107">Se è necessario verificare innanzitutto la presenza di valori Null e quindi testare il valore, è preferibile eseguire la query in una clausola `let` e poi usare i risultati nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="e52ee-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e52ee-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e52ee-108">Example</span></span>  
 <span data-ttu-id="e52ee-109">Nell'esempio seguente vengono selezionati tutti gli elementi `p` immediatamente seguiti da un elemento `ul`.</span><span class="sxs-lookup"><span data-stu-id="e52ee-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
```  
  
 <span data-ttu-id="e52ee-110">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e52ee-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="e52ee-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e52ee-111">Example</span></span>  
 <span data-ttu-id="e52ee-112">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e52ee-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e52ee-113">Per altre informazioni, vedere [uso di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="e52ee-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e52ee-114">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e52ee-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="e52ee-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e52ee-115">See also</span></span>
- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
- [<span data-ttu-id="e52ee-116">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e52ee-116">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
