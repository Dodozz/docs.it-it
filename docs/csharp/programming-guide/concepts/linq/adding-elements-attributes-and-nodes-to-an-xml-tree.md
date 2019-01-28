---
title: Aggiunta di elementi, attributi e nodi a un albero XML (C#)
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 87b63df1011af9594ff44bed6385f9d82dee08a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585877"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="94d50-102">Aggiunta di elementi, attributi e nodi a un albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="94d50-102">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="94d50-103">È possibile aggiungere contenuto (elementi, attributi, commenti, istruzioni di elaborazione, testo e CDATA) a un albero XML esistente.</span><span class="sxs-lookup"><span data-stu-id="94d50-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="94d50-104">Metodi per l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="94d50-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="94d50-105">I metodi seguenti consentono di aggiungere contenuto figlio a un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="94d50-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="94d50-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="94d50-106">Method</span></span>|<span data-ttu-id="94d50-107">Description</span><span class="sxs-lookup"><span data-stu-id="94d50-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="94d50-108">Consente di aggiungere il contenuto alla fine del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="94d50-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="94d50-109">Consente di aggiungere il contenuto all'inizio del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="94d50-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="94d50-110">I seguenti metodi consentono di aggiungere contenuto come nodi di pari livello di un oggetto <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="94d50-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="94d50-111">Il nodo più comune al quale viene aggiunto contenuto di pari livello è <xref:System.Xml.Linq.XElement>, anche se è possibile aggiungere contenuto di pari livello valido ad altri tipi di nodi, tra cui <xref:System.Xml.Linq.XText> o <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="94d50-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="94d50-112">Metodo</span><span class="sxs-lookup"><span data-stu-id="94d50-112">Method</span></span>|<span data-ttu-id="94d50-113">Description</span><span class="sxs-lookup"><span data-stu-id="94d50-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="94d50-114">Consente di aggiungere contenuto dopo <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="94d50-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="94d50-115">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="94d50-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94d50-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="94d50-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="94d50-117">Description</span><span class="sxs-lookup"><span data-stu-id="94d50-117">Description</span></span>  
 <span data-ttu-id="94d50-118">Nell'esempio seguente vengono create due strutture ad albero XML e quindi ne viene modificata una.</span><span class="sxs-lookup"><span data-stu-id="94d50-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="94d50-119">Codice</span><span class="sxs-lookup"><span data-stu-id="94d50-119">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",   
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="94d50-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="94d50-120">Comments</span></span>  
 <span data-ttu-id="94d50-121">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="94d50-121">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94d50-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94d50-122">See also</span></span>

- [<span data-ttu-id="94d50-123">Modifica degli alberi XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="94d50-123">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
