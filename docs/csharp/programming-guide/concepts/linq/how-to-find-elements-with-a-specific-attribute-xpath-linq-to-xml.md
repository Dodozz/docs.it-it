---
title: 'Procedura: Trovare elementi con un attributo specifico (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: fc1bc285a066dcb1843dcb626b1b3b354f28da74
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486812"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="ba32c-102">Procedura: Trovare elementi con un attributo specifico (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ba32c-102">How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="ba32c-103">Talvolta si desidera individuare tutti gli elementi con un attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="ba32c-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="ba32c-104">Il contenuto dell'attributo non è rilevante</span><span class="sxs-lookup"><span data-stu-id="ba32c-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="ba32c-105">perché si desidera solo individuare gli elementi in cui tale attributo è presente.</span><span class="sxs-lookup"><span data-stu-id="ba32c-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="ba32c-106">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="ba32c-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="ba32c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba32c-107">Example</span></span>  
 <span data-ttu-id="ba32c-108">Nel codice seguente vengono selezionati solo gli elementi con attributo `Select`.</span><span class="sxs-lookup"><span data-stu-id="ba32c-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="ba32c-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ba32c-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  