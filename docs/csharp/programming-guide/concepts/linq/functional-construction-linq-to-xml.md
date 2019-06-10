---
title: costruzione funzionale (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: 46cf4dbaf190182467cbbe1094070b2da0854c68
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486035"
---
# <a name="functional-construction-linq-to-xml-c"></a><span data-ttu-id="9a34a-102">costruzione funzionale (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9a34a-102">Functional Construction (LINQ to XML) (C#)</span></span>
<span data-ttu-id="9a34a-103">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è disponibile una potente funzionalità per la creazione di elementi XML, denominata *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="9a34a-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="9a34a-104">Per costruzione funzionale si intende la possibilità di creare una struttura ad albero XML in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="9a34a-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="9a34a-105">Diverse funzionalità importanti dell'interfaccia di programmazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono la costruzione funzionale:</span><span class="sxs-lookup"><span data-stu-id="9a34a-105">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
- <span data-ttu-id="9a34a-106">Il costruttore <xref:System.Xml.Linq.XElement> accetta vari tipi di argomenti come contenuto.</span><span class="sxs-lookup"><span data-stu-id="9a34a-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="9a34a-107">Ad esempio, è possibile passare un altro oggetto <xref:System.Xml.Linq.XElement>, che diventa un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="9a34a-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="9a34a-108">È possibile passare un oggetto <xref:System.Xml.Linq.XAttribute>, che diventa un attributo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9a34a-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="9a34a-109">Oppure è possibile passare qualsiasi altro tipo di oggetto, che viene convertito in una stringa e diventa il contenuto di testo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9a34a-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
- <span data-ttu-id="9a34a-110">Il costruttore <xref:System.Xml.Linq.XElement> accetta una matrice `params` di tipo <xref:System.Object>, quindi è possibile passare qualsiasi numero di oggetti.</span><span class="sxs-lookup"><span data-stu-id="9a34a-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="9a34a-111">In questo modo è possibile creare un elemento con contenuto complesso.</span><span class="sxs-lookup"><span data-stu-id="9a34a-111">This enables you to create an element that has complex content.</span></span>  
  
- <span data-ttu-id="9a34a-112">Se un oggetto implementa <xref:System.Collections.Generic.IEnumerable%601>, la raccolta nell'oggetto viene enumerata e vengono aggiunti tutti gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9a34a-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="9a34a-113">Se la raccolta contiene oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, ogni elemento della raccolta viene aggiunto separatamente.</span><span class="sxs-lookup"><span data-stu-id="9a34a-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="9a34a-114">Questo aspetto è importante perché consente di passare i risultati di una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] al costruttore.</span><span class="sxs-lookup"><span data-stu-id="9a34a-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="9a34a-115">Queste funzionalità consentono di scrivere codice per creare un albero XML.</span><span class="sxs-lookup"><span data-stu-id="9a34a-115">These features enable you to write code to create an XML tree.</span></span> <span data-ttu-id="9a34a-116">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="9a34a-116">The following is an example:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="9a34a-117">Queste funzionalità consentono anche di scrivere codice che usa i risultati di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per creare un albero XML. Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="9a34a-117">These features also enable you to write code that uses the results of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries when you create an XML tree, as follows:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="9a34a-118">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="9a34a-118">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  