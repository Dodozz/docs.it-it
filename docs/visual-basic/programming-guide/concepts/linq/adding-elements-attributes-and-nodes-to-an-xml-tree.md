---
title: Aggiunta di elementi, attributi e nodi a un albero XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
ms.openlocfilehash: 35d3bdb27342dd7a871778ad4749db4d6849bd60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814316"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="de499-102">Aggiunta di elementi, attributi e nodi a un albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de499-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="de499-103">È possibile aggiungere contenuto (elementi, attributi, commenti, istruzioni di elaborazione, testo e CDATA) a un albero XML esistente.</span><span class="sxs-lookup"><span data-stu-id="de499-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="de499-104">Metodi per l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="de499-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="de499-105">I metodi seguenti consentono di aggiungere contenuto figlio a un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="de499-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="de499-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="de499-106">Method</span></span>|<span data-ttu-id="de499-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de499-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="de499-108">Consente di aggiungere il contenuto alla fine del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="de499-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="de499-109">Consente di aggiungere il contenuto all'inizio del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="de499-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="de499-110">I seguenti metodi consentono di aggiungere contenuto come nodi di pari livello di un oggetto <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="de499-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="de499-111">Il nodo più comune al quale viene aggiunto contenuto di pari livello è <xref:System.Xml.Linq.XElement>, anche se è possibile aggiungere contenuto di pari livello valido ad altri tipi di nodi, tra cui <xref:System.Xml.Linq.XText> o <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="de499-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="de499-112">Metodo</span><span class="sxs-lookup"><span data-stu-id="de499-112">Method</span></span>|<span data-ttu-id="de499-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de499-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="de499-114">Consente di aggiungere contenuto dopo <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="de499-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="de499-115">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="de499-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de499-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="de499-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="de499-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de499-117">Description</span></span>  
 <span data-ttu-id="de499-118">Nell'esempio seguente vengono create due strutture ad albero XML e quindi ne viene modificata una.</span><span class="sxs-lookup"><span data-stu-id="de499-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="de499-119">Codice</span><span class="sxs-lookup"><span data-stu-id="de499-119">Code</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
```  
  
### <a name="comments"></a><span data-ttu-id="de499-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="de499-120">Comments</span></span>  
 <span data-ttu-id="de499-121">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="de499-121">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="de499-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de499-122">See also</span></span>

- [<span data-ttu-id="de499-123">Modifica degli alberi XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de499-123">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
