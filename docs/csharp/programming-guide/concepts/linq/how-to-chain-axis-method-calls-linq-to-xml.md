---
title: "Procedura: Concatenare chiamate al metodo dell'asse (LINQ to XML) (C#)"
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: 39113c1b96ea7376d61c606aaa5f79715dbe3cab
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485927"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a>Procedura: Concatenare chiamate al metodo dell'asse (LINQ to XML) (C#)
Uno schema comune da usare nel codice consiste nel chiamare un metodo dell'asse e quindi chiamare uno degli assi del metodo di estensione.  
  
 Sono disponibili due assi denominati `Elements` che restituiscono una raccolta di elementi: il metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> e il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>. È possibile combinare questi due assi per individuare tutti gli elementi con un nome specificato a una data profondità dell'albero.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono usati <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> e <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> per individuare tutti gli elementi `Name` inclusi in tutti gli elementi `Address` di tutti gli elementi `PurchaseOrder`.  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 Questo esempio viene eseguito correttamente perché una delle implementazioni dell'asse `Elements` è un metodo di estensione su <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XContainer>. <xref:System.Xml.Linq.XElement> deriva da <xref:System.Xml.Linq.XContainer>, pertanto è possibile chiamare il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> sui risultati di una chiamata al metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Talvolta si desidera recuperare tutti gli elementi presenti a una data profondità dell'elemento in cui possono o meno esistere elementi predecessori intermedi. Ad esempio, nel documento seguente può essere necessario recuperare tutti gli elementi `ConfigParameter` che sono elementi figli dell'elemento `Customer`, ma non `ConfigParameter` che è un elemento figlio dell'elemento `Root`.  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 A tale scopo, è possibile usare l'asse <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> nel modo seguente:  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è illustrata la stessa tecnica per XML in uno spazio dei nomi. Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
