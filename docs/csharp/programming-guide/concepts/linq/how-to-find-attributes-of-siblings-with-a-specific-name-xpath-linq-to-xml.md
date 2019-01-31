---
title: 'Procedura: Trovare attributi di elementi di pari livello con un nome specifico (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 562f3a40e1670a76778a64570f980326d946a4c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584675"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a>Procedura: Trovare attributi di elementi di pari livello con un nome specifico (XPath-LINQ to XML) (C#)
In questo argomento viene illustrato come trovare tutti gli attributi degli elementi di pari livello del nodo di contesto. Nella raccolta vengono restituiti solo gli attributi con un nome specifico.  
  
 L'espressione XPath è:  
  
 `../Book/@id`  
  
## <a name="example"></a>Esempio  
 In questo esempio viene dapprima ricercato un elemento `Book`, quindi tutti gli elementi di pari livello denominati `Book` e infine tutti gli attributi denominati `id`. Il risultato è una raccolta di attributi.  
  
 Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: libri (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML per gli utenti di XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
