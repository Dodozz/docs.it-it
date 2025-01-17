---
title: 'Procedura: Generare un flusso di frammenti XML con accesso a informazioni di intestazione (C#)'
ms.date: 07/20/2015
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: 4ecf20134c0d5897418c7667908f80511a962871
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484849"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a>Procedura: Generare un flusso di frammenti XML con accesso a informazioni di intestazione (C#)
A volte è necessario leggere file XML arbitrariamente grandi e scrivere l'applicazione in modo tale che il footprint di memoria dell'applicazione sia prevedibile. Se si tenta di popolare un albero XML con un file XML di grandi dimensioni, l'uso della memoria sarà proporzionale alla dimensione del file (ovvero, eccessivo). Pertanto, è necessario usare una tecnica di flusso in sostituzione.  
  
 Una delle opzioni disponibili consiste nello scrivere l'applicazione usando <xref:System.Xml.XmlReader>. Può tuttavia essere necessario usare [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per eseguire una query nell'albero XML. In questo caso, è possibile scrivere un metodo dell'asse personalizzato. Per altre informazioni, vedere [Procedura: Scrivere un metodo dell'asse LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).  
  
 Per scrivere metodo dell'asse, scrivere un piccolo metodo che usa <xref:System.Xml.XmlReader> per leggere i nodi fino a raggiungere uno dei nodi di interesse. Il metodo chiama quindi <xref:System.Xml.Linq.XNode.ReadFrom%2A>, che legge da <xref:System.Xml.XmlReader> e crea un'istanza di un frammento XML. Restituisce quindi ogni frammento tramite `yield return` al metodo che sta enumerando il metodo dell'asse personalizzato. È quindi possibile scrivere query LINQ sul metodo dell'asse personalizzato.  
  
 Le tecniche di flusso sono maggiormente indicate nelle situazioni in cui è necessario elaborare solo una volta il documento di origine ed è possibile elaborare gli elementi in base all'ordine in cui sono riportati nel documento. Determinati operatori di query standard, ad esempio <xref:System.Linq.Enumerable.OrderBy%2A>, scorrono l'origine, raccolgono tutti i dati, li ordinano e infine restituiscono il primo elemento nella sequenza. Si noti che se si usa un operatore di query che materializza l'origine prima di restituire il primo elemento, non verrà mantenuto un footprint di memoria ridotto.  
  
## <a name="example"></a>Esempio  
 A volte il problema diventa più interessante. Nel documento XML seguente, il consumer del metodo dell'asse personalizzato deve conoscere anche il nome del cliente cui appartiene ogni elemento.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
 L'approccio adottato in questo esempio prevede anche di cercare queste informazioni di intestazione, salvarle e quindi compilare un piccolo albero XML che contiene sia le informazioni di intestazione che i dettagli enumerati. Il metodo dell'asse restituisce questo nuovo, piccolo albero XML. La query ha quindi accesso alle informazioni di intestazione oltre a quelle sui dettagli.  
  
 Questo approccio prevede un footprint di memoria ridotto. Quando viene restituito un frammento XML, non viene mantenuto alcun riferimento al frammento precedente, che diventa disponibile per Garbage Collection. Si noti che con questa tecnica vengono creati molti oggetti temporanei sull'heap.  
  
 Nell'esempio seguente viene illustrato come implementare e usare un metodo dell'asse personalizzato che genera un flusso di frammenti XML dal file specificato dall'URI. Il metodo dell'asse personalizzato è stato scritto in modo tale da prevedere un documento contenente gli elementi `Customer`, `Name` e `Item`, disposti come nel documento `Source.xml` precedente. Si tratta di un'implementazione semplicistica. Un'implementazione più solida sarebbe in grado di analizzare un documento non valido.  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XElement xmlTree = new XElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    Console.WriteLine(xmlTree);  
}  
```  
  
 L'output del codice è il seguente:  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
</Root>  
```  
  