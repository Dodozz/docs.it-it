---
title: Panoramica della classe XAttribute (C#)
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 0440e8271edcf54d00a56e2987235afd260f9156
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66483191"
---
# <a name="xattribute-class-overview-c"></a>Panoramica della classe XAttribute (C#)
Gli attributi sono coppie nome/valore associate a un elemento. La classe <xref:System.Xml.Linq.XAttribute> rappresenta gli attributi XML.  
  
## <a name="overview"></a>Panoramica  
 Le modalità di utilizzo degli attributi in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sono simili a quelle degli elementi. I relativi costruttori sono simili. I metodi usati per recuperare le relative raccolte sono simili. Un'espressione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] relativa a una raccolta di attributi ha un aspetto molto simile a quello di un'espressione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] relativa a una raccolta di elementi.  
  
 L'ordine con cui gli attributi vengono aggiunti a un elemento viene mantenuto. Quando si scorrono gli attributi, questi vengono visualizzati nell'ordine in cui sono stati aggiunti.  
  
## <a name="the-xattribute-constructor"></a>Costruttore XAttribute  
 Il seguente costruttore della classe <xref:System.Xml.Linq.XAttribute> è quello usato più comunemente:  
  
|Costruttore|Description|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Crea un oggetto <xref:System.Xml.Linq.XAttribute>. L'argomento `name` specifica il nome dell'attributo, mentre `content` ne specifica il contenuto.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Creazione di un elemento con un attributo  
 Nel codice seguente è illustrata l'attività comune di creazione di un elemento che contiene un attributo:  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Costruzione funzionale di attributi  
 È possibile costruire oggetti <xref:System.Xml.Linq.XAttribute> in linea con la costruzione di oggetti <xref:System.Xml.Linq.XElement>, come descritto di seguito:  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Attributi non nodi  
 Esistono alcune differenze tra attributi ed elementi. Gli oggetti <xref:System.Xml.Linq.XAttribute> non rappresentano nodi nell'albero XML, ma sono coppie nome/valore associate a un elemento XML. A differenza del modello DOM (Document Object Model), questa definizione rispecchia maggiormente la struttura del codice XML. Sebbene gli oggetti <xref:System.Xml.Linq.XAttribute> non siano effettivamente nodi dell'albero XML, le modalità di utilizzo degli oggetti <xref:System.Xml.Linq.XAttribute> sono molto simili a quelle degli oggetti <xref:System.Xml.Linq.XElement>.  
  
 Questa distinzione è di fondamentale importanza solo per gli sviluppatori che scrivono codice che riguarda gli alberi XML a livello di nodo. Non interessa quindi la maggior parte degli sviluppatori.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione con LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md)
