---
title: 'Procedura: Analizzare una stringa (C#)'
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: c4d26f534c718d69c84a30b11de22249b241e084
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629787"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="30fdd-102">Procedura: Analizzare una stringa (C#)</span><span class="sxs-lookup"><span data-stu-id="30fdd-102">How to: Parse a String (C#)</span></span>
<span data-ttu-id="30fdd-103">Questo argomento illustra come analizzare una stringa per creare una struttura ad albero XML in C#.</span><span class="sxs-lookup"><span data-stu-id="30fdd-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30fdd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="30fdd-104">Example</span></span>  
 <span data-ttu-id="30fdd-105">Nel codice C# seguente viene illustrato come analizzare una stringa.</span><span class="sxs-lookup"><span data-stu-id="30fdd-105">The following C# code shows how to parse a string.</span></span>  
  
```csharp  
XElement contacts = XElement.Parse(  
    @"<Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type=""home"">206-555-0144</Phone>  
            <Phone type=""work"">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type=""mobile"">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>");  
Console.WriteLine(contacts);  
```  
  
## <a name="see-also"></a><span data-ttu-id="30fdd-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30fdd-106">See also</span></span>

- [<span data-ttu-id="30fdd-107">Analisi di codice XML (C#)</span><span class="sxs-lookup"><span data-stu-id="30fdd-107">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
