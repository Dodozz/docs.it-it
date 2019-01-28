---
title: Serializzazione con una dichiarazione XML (C#)
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 4f5dd9a7e392acff30814db4a483b297494b68b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702405"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="5b14f-102">Serializzazione con una dichiarazione XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5b14f-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="5b14f-103">In questo argomento viene descritto come controllare se la serializzazione genera una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="5b14f-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="5b14f-104">Generazione della dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="5b14f-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="5b14f-105">La serializzazione di <xref:System.IO.File> o <xref:System.IO.TextWriter> tramite il metodo <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> o il metodo <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> genera una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="5b14f-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="5b14f-106">Quando si serializza in <xref:System.Xml.XmlWriter>, le impostazioni del writer (specificate in un oggetto <xref:System.Xml.XmlWriterSettings>) determinano se una dichiarazione XML viene generata o meno.</span><span class="sxs-lookup"><span data-stu-id="5b14f-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="5b14f-107">Se si serializza in una stringa tramite il metodo `ToString`, l'XML risultante non includerà una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="5b14f-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="5b14f-108">Serializzazione con una dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="5b14f-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="5b14f-109">Nell'esempio seguente viene creato un oggetto <xref:System.Xml.Linq.XElement>, viene salvato il documento in un file e quindi stampato il file nella console.</span><span class="sxs-lookup"><span data-stu-id="5b14f-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5b14f-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="5b14f-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="5b14f-111">Serializzazione senza una dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="5b14f-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="5b14f-112">Nell'esempio seguente viene illustrato come salvare <xref:System.Xml.Linq.XElement> in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="5b14f-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="5b14f-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="5b14f-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b14f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b14f-114">See also</span></span>

- [<span data-ttu-id="5b14f-115">Serializzazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5b14f-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
