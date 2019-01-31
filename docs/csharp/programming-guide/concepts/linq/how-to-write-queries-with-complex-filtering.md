---
title: 'Procedura: Scrivere query con filtri complessi (C#)'
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 847e50cf0c1cf91f8b731457d351bb0d01d725c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700585"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="a63f2-102">Procedura: Scrivere query con filtri complessi (C#)</span><span class="sxs-lookup"><span data-stu-id="a63f2-102">How to: Write Queries with Complex Filtering (C#)</span></span>
<span data-ttu-id="a63f2-103">A volte si desidera scrivere query LINQ to XML con filtri complessi.</span><span class="sxs-lookup"><span data-stu-id="a63f2-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="a63f2-104">Può ad esempio essere necessario trovare tutti gli elementi che hanno un elemento figlio con un determinato nome e valore.</span><span class="sxs-lookup"><span data-stu-id="a63f2-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="a63f2-105">In questo argomento viene illustrato come scrivere una query di esempio con filtri complessi.</span><span class="sxs-lookup"><span data-stu-id="a63f2-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a63f2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a63f2-106">Example</span></span>  
 <span data-ttu-id="a63f2-107">Nell'esempio viene illustrato come trovare tutti gli elementi `PurchaseOrder` che includono un elemento figlio `Address` con un attributo `Type` uguale a "Shipping" e un elemento figlio `State` uguale a "NY".</span><span class="sxs-lookup"><span data-stu-id="a63f2-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="a63f2-108">Viene usata una query annidata nella clausola `Where` e l'operatore `Any` restituisce `true` se la raccolta contiene elementi.</span><span class="sxs-lookup"><span data-stu-id="a63f2-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="a63f2-109">Per informazioni sull'uso della sintassi delle query basate su metodo, vedere [Sintassi di query e sintassi di metodi in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="a63f2-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="a63f2-110">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a63f2-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="a63f2-111">Per altre informazioni sull'operatore `Any`, vedere [Operazioni del quantificatore (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a63f2-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="a63f2-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a63f2-112">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="a63f2-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a63f2-113">Example</span></span>  
 <span data-ttu-id="a63f2-114">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a63f2-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="a63f2-115">Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="a63f2-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="a63f2-116">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="a63f2-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="a63f2-117">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a63f2-117">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="a63f2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a63f2-118">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="a63f2-119">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a63f2-119">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="a63f2-120">Operazioni di proiezione (C#)</span><span class="sxs-lookup"><span data-stu-id="a63f2-120">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="a63f2-121">Operazioni del quantificatore (C#)</span><span class="sxs-lookup"><span data-stu-id="a63f2-121">Quantifier Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
