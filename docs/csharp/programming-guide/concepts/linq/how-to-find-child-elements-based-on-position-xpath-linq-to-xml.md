---
title: 'Procedura: Trovare elementi figlio in base alla posizione (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
ms.openlocfilehash: 967d9cf80b5d5edfe995196751b4f769ed6088d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577438"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a><span data-ttu-id="6c12f-102">Procedura: Trovare elementi figlio in base alla posizione (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c12f-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="6c12f-103">Talvolta si desidera individuare elementi in base alla posizione,</span><span class="sxs-lookup"><span data-stu-id="6c12f-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="6c12f-104">ad esempio il secondo elemento oppure dal terzo al quinto elemento.</span><span class="sxs-lookup"><span data-stu-id="6c12f-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="6c12f-105">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="6c12f-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="6c12f-106">Sono disponibili due approcci per la scrittura di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in modalità lazy.</span><span class="sxs-lookup"><span data-stu-id="6c12f-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="6c12f-107">È possibile usare gli operatori <xref:System.Linq.Enumerable.Skip%2A> e <xref:System.Linq.Enumerable.Take%2A> oppure l'overload <xref:System.Linq.Enumerable.Where%2A> che accetta un indice.</span><span class="sxs-lookup"><span data-stu-id="6c12f-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="6c12f-108">Quando si usa l'overload <xref:System.Linq.Enumerable.Where%2A>, viene usata un'espressione lambda che accetta due argomenti.</span><span class="sxs-lookup"><span data-stu-id="6c12f-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="6c12f-109">Nell'esempio seguente sono illustrati entrambi i metodi di selezione basata sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="6c12f-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c12f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c12f-110">Example</span></span>  
 <span data-ttu-id="6c12f-111">In questo esempio vengono individuati gli elementi `Test` compresi tra il secondo e il quarto.</span><span class="sxs-lookup"><span data-stu-id="6c12f-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="6c12f-112">Il risultato è una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="6c12f-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="6c12f-113">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: configurazione di test (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6c12f-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="6c12f-114">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="6c12f-114">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c12f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c12f-115">See also</span></span>

- [<span data-ttu-id="6c12f-116">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="6c12f-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
