---
title: 'Procedura: Eseguire il debug di set di risultati vuoti di query (C#)'
ms.date: 07/20/2015
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 0503c09bbdd28276ea4fdc1147e0bca5471fa6e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723183"
---
# <a name="how-to-debug-empty-query-results-sets-c"></a><span data-ttu-id="cadc8-102">Procedura: Eseguire il debug di set di risultati vuoti di query (C#)</span><span class="sxs-lookup"><span data-stu-id="cadc8-102">How to: Debug Empty Query Results Sets (C#)</span></span>
<span data-ttu-id="cadc8-103">Uno dei problemi più comuni che viene riscontrato durante l'esecuzione di query su alberi XML è che, se l'albero XML include uno spazio dei nomi predefinito, lo sviluppatore scrive talvolta la query come se il codice XML non fosse incluso in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="cadc8-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="cadc8-104">Nel primo set di esempi riportati in questo argomento viene illustrato il tipico caricamento del codice XML in uno spazio dei nomi predefinito e l'esecuzione errata di query su tale codice.</span><span class="sxs-lookup"><span data-stu-id="cadc8-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>  
  
 <span data-ttu-id="cadc8-105">Nel secondo set di esempi sono illustrate le correzioni necessarie da effettuare per poter eseguire query su codice XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="cadc8-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
 <span data-ttu-id="cadc8-106">Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="cadc8-106">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cadc8-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="cadc8-107">Example</span></span>  
 <span data-ttu-id="cadc8-108">In questo esempio è illustrata la creazione di codice XML in uno spazio dei nomi e una query che restituisce un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="cadc8-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="cadc8-109">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="cadc8-109">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="cadc8-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="cadc8-110">Example</span></span>  
 <span data-ttu-id="cadc8-111">In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi, nonché una query codificata correttamente.</span><span class="sxs-lookup"><span data-stu-id="cadc8-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="cadc8-112">La soluzione consiste nel dichiarare e inizializzare un oggetto <xref:System.Xml.Linq.XNamespace> e usarlo quando si specificano oggetti <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="cadc8-112">The solution is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="cadc8-113">In questo caso l'argomento del metodo <xref:System.Xml.Linq.XElement.Elements%2A> è un oggetto <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="cadc8-113">In this case, the argument to the <xref:System.Xml.Linq.XElement.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="cadc8-114">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="cadc8-114">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="cadc8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cadc8-115">See also</span></span>

- [<span data-ttu-id="cadc8-116">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cadc8-116">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
