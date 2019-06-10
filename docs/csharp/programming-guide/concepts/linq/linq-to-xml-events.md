---
title: Eventi LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 8278d3eac9d1e149cbfe64e184439ef9ac3cd39b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484332"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="09213-102">Eventi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="09213-102">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="09213-103">Gli eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono di ricevere una notifica quando un albero XML viene modificato.</span><span class="sxs-lookup"><span data-stu-id="09213-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="09213-104">È possibile aggiungere eventi a un'istanza di qualsiasi oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="09213-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="09213-105">Il gestore eventi riceverà quindi gli eventi relativi alle modifiche apportate a <xref:System.Xml.Linq.XObject> e a tutti i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="09213-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="09213-106">Ad esempio, è possibile aggiungere un gestore eventi alla radice dell'albero e gestire tutte le modifiche apportate alla struttura da tale gestore.</span><span class="sxs-lookup"><span data-stu-id="09213-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="09213-107">Per esempi di eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vedere <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="09213-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="09213-108">Tipi ed eventi</span><span class="sxs-lookup"><span data-stu-id="09213-108">Types and Events</span></span>  
 <span data-ttu-id="09213-109">Con gli eventi è possibile usare i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="09213-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="09213-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="09213-110">Type</span></span>|<span data-ttu-id="09213-111">Description</span><span class="sxs-lookup"><span data-stu-id="09213-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="09213-112">Specifica il tipo di evento quando viene generato un evento per un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="09213-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="09213-113">Fornisce i dati per gli eventi <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="09213-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="09213-114">Gli eventi seguenti vengono generati quando si modifica una struttura ad albero XML:</span><span class="sxs-lookup"><span data-stu-id="09213-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="09213-115">event</span><span class="sxs-lookup"><span data-stu-id="09213-115">Event</span></span>|<span data-ttu-id="09213-116">Description</span><span class="sxs-lookup"><span data-stu-id="09213-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="09213-117">Si verifica poco prima che l'oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti venga modificato.</span><span class="sxs-lookup"><span data-stu-id="09213-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="09213-118">Si verifica quando un oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti viene modificato.</span><span class="sxs-lookup"><span data-stu-id="09213-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="09213-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="09213-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="09213-120">Description</span><span class="sxs-lookup"><span data-stu-id="09213-120">Description</span></span>  
 <span data-ttu-id="09213-121">Gli eventi sono utili quando si desidera gestire alcune informazioni di aggregazione in un albero XML.</span><span class="sxs-lookup"><span data-stu-id="09213-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="09213-122">Ad esempio, si desidera gestire un totale di fattura che corrisponde alla somma delle voci della fattura.</span><span class="sxs-lookup"><span data-stu-id="09213-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="09213-123">In questo esempio vengono usati gli eventi per gestire il totale di tutti gli elementi figlio sotto l'elemento `Items` complesso.</span><span class="sxs-lookup"><span data-stu-id="09213-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="09213-124">Codice</span><span class="sxs-lookup"><span data-stu-id="09213-124">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="09213-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="09213-125">Comments</span></span>  
 <span data-ttu-id="09213-126">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="09213-126">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  