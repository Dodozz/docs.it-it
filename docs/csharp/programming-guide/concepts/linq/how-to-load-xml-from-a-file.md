---
title: 'Procedura: Caricare XML da un file (C#)'
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: f97e99a3d5fb2dd5628e1dc00909b6608255a967
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688132"
---
# <a name="how-to-load-xml-from-a-file-c"></a><span data-ttu-id="398fb-102">Procedura: Caricare XML da un file (C#)</span><span class="sxs-lookup"><span data-stu-id="398fb-102">How to: Load XML from a File (C#)</span></span>
<span data-ttu-id="398fb-103">In questo argomento viene illustrato come caricare XML da un URI tramite il metodo <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="398fb-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="398fb-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="398fb-104">Example</span></span>  
 <span data-ttu-id="398fb-105">Nell'esempio seguente viene illustrato come caricare un documento XML da un file.</span><span class="sxs-lookup"><span data-stu-id="398fb-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="398fb-106">Viene caricato il file books.xml e viene restituito l'albero XML alla console.</span><span class="sxs-lookup"><span data-stu-id="398fb-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="398fb-107">Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: libri (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="398fb-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 <span data-ttu-id="398fb-108">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="398fb-108">This code produces the following output:</span></span>  
  
```xml  
<Catalog>  
  <Book id="bk101">  
    <Author>Garghentini, Davide</Author>  
    <Title>XML Developer's Guide</Title>  
    <Genre>Computer</Genre>  
    <Price>44.95</Price>  
    <PublishDate>2000-10-01</PublishDate>  
    <Description>An in-depth look at creating applications   
      with XML.</Description>  
  </Book>  
  <Book id="bk102">  
    <Author>Garcia, Debra</Author>  
    <Title>Midnight Rain</Title>  
    <Genre>Fantasy</Genre>  
    <Price>5.95</Price>  
    <PublishDate>2000-12-16</PublishDate>  
    <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
  </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="398fb-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="398fb-109">See also</span></span>

- [<span data-ttu-id="398fb-110">Analisi di codice XML (C#)</span><span class="sxs-lookup"><span data-stu-id="398fb-110">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
