---
title: 'Procedura: Trovare discendenti con un nome di elemento specifico (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: c7dadec961420988a7f4cc1d6be72d7cdba5c047
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780497"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a><span data-ttu-id="c61fa-102">Procedura: Trovare discendenti con un nome di elemento specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c61fa-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>
<span data-ttu-id="c61fa-103">Talvolta si desidera individuare tutti i discendenti con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="c61fa-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="c61fa-104">È possibile scrivere codice per scorrere tutti i discendenti, tuttavia è più agevole usare l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="c61fa-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c61fa-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c61fa-105">Example</span></span>  
 <span data-ttu-id="c61fa-106">Nell'esempio seguente è illustrato come individuare discendenti in base al nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="c61fa-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```vb  
Dim root As XElement = _  
    <root>  
        <para>  
            <r>  
                <t>Some text </t>  
            </r>  
            <n>  
                <r>  
                    <t>that is broken up into </t>  
                </r>  
            </n>  
            <n>  
                <r>  
                    <t>multiple segments.</t>  
                </r>  
            </n>  
        </para>  
    </root>  
  
Dim textSegs As IEnumerable(Of String) = _  
    From seg In root...<t> _  
    Select seg.Value  
  
Dim str As String = textSegs.Aggregate( _  
    New StringBuilder, _  
    Function(sb, i) sb.Append(i), _  
    Function(sb) sb.ToString)  
  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="c61fa-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c61fa-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="c61fa-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c61fa-108">Example</span></span>  
 <span data-ttu-id="c61fa-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c61fa-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c61fa-110">Per altre informazioni, vedere [uso di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="c61fa-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <root>  
                <para>  
                    <r>  
                        <t>Some text </t>  
                    </r>  
                    <n>  
                        <r>  
                            <t>that is broken up into </t>  
                        </r>  
                    </n>  
                    <n>  
                        <r>  
                            <t>multiple segments.</t>  
                        </r>  
                    </n>  
                </para>  
            </root>  
  
        Dim textSegs As IEnumerable(Of String) = _  
            From seg In root...<t> _  
            Select seg.Value  
  
        Dim str As String = textSegs.Aggregate( _  
            New StringBuilder, _  
            Function(sb, i) sb.Append(i), _  
            Function(sb) sb.ToString)  
  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c61fa-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c61fa-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c61fa-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c61fa-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- [<span data-ttu-id="c61fa-113">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c61fa-113">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
