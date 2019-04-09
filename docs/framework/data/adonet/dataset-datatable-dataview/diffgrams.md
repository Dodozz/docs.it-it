---
title: DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 1324e6536390b598ca9ef1f0cd3102f8ec49d45a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197997"
---
# <a name="diffgrams"></a>DiffGram
DiffGram è un formato XML che consente di identificare le versioni correnti e originali degli elementi di dati. Il formato DiffGram viene usato dal tipo <xref:System.Data.DataSet> per caricare e conservare il contenuto e per serializzare tale contenuto in modo da consentirne il trasporto tramite una connessione di rete. Quando un <xref:System.Data.DataSet> viene scritto come DiffGram, tale DiffGram viene compilato con tutte le informazioni necessarie per ricreare accuratamente il contenuto, anche se non lo schema, del <xref:System.Data.DataSet>, inclusi sia i valori della colonna di **originale** e **corrente** versioni delle righe, le informazioni sull'errore di riga e l'ordine delle righe.  
  
 Quando si invia e si recupera un tipo <xref:System.Data.DataSet> da un servizio Web XML, il formato DiffGram viene usato implicitamente. Inoltre, quando si carica il contenuto di un <xref:System.Data.DataSet> da XML usando il **ReadXml** (metodo), o quando si scrive il contenuto di un <xref:System.Data.DataSet> in XML usando il **WriteXml** metodo, è possibile specificare che il contenuto è essere letto o scritto come DiffGram. Per altre informazioni, vedere [caricamento di un DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) e [scrittura di contenuti di DataSet come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Benché il formato DiffGram venga usato principalmente da .NET Framework come formato di serializzazione per il contenuto di un tipo <xref:System.Data.DataSet>, è possibile usare i DiffGram per modificare i dati delle tabelle di un database Microsoft SQL Server.  
  
 Un Diffgram viene generato scrivendo il contenuto di tutte le tabelle in un  **\<diffgram >** elemento.  
  
### <a name="to-generate-a-diffgram"></a>Per generare un Diffgram  
  
1.  Generare un elenco di tabelle radice, ovvero senza elementi padre.  
  
2.  Per ogni tabella e per i relativi discendenti nell'elenco, scrivere la versione corrente di tutte le righe nella prima sezione del Diffgram.  
  
3.  Per ogni tabella nel <xref:System.Data.DataSet>, scrivere la versione originale di tutte le righe, se disponibile, nella  **\<prima >** sezione del Diffgram.  
  
4.  Per le righe che contengono errori, scrivere il contenuto dell'errore nella  **\<errori >** sezione del Diffgram.  
  
 Un Diffgram viene elaborato nell'ordine a partire dal file XML fino alla fine.  
  
### <a name="to-process-a-diffgram"></a>Per elaborare un Diffgram  
  
1.  Elaborare la prima sezione del Diffgram che contiene la versione corrente delle righe.  
  
2.  Elaborare la seconda o le  **\<prima di >** sezione che contiene la versione originale delle righe modificate ed eliminate.  
  
    > [!NOTE]
    >  Se una riga è contrassegnata come eliminata, con l'operazione di eliminazione è possibile che vengano rimossi anche i relativi discendenti, a seconda della proprietà `Cascade` dell'oggetto <xref:System.Data.DataSet> corrente.  
  
3.  Processo di  **\<errori >** sezione. Impostare le informazioni sull'errore per la riga e la colonna specificate per ogni elemento di questa sezione.  
  
> [!NOTE]
>  Se si imposta <xref:System.Data.XmlWriteMode> su Diffgram, il contenuto dell'oggetto <xref:System.Data.DataSet> di destinazione può essere diverso da quello dell'oggetto <xref:System.Data.DataSet> originale.  
  
## <a name="diffgram-format"></a>Formato DiffGram  
 Il formato DiffGram è suddiviso in tre sezioni: i dati correnti, i dati originali (o "precedenti") e una sezione relativa agli errori, come illustrato nell'esempio seguente.  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 Il formato DiffGram è costituito dai seguenti blocchi di dati:  
  
 **\<**  ***DataInstance***  **>**  
 Il nome di questo elemento ***DataInstance***, viene usato a scopo esplicativo nella presente documentazione. Oggetto ***DataInstance*** elemento rappresenta un <xref:System.Data.DataSet> o una riga di un <xref:System.Data.DataTable>. Invece di *DataInstance*, l'elemento contiene il nome delle <xref:System.Data.DataSet> o <xref:System.Data.DataTable>. In questo blocco del formato DiffGram sono contenuti i dati correnti, indipendentemente dalle eventuali modifiche a tali dati. Un elemento o una riga, che è stato modificato viene identificato con il **diffgr: HasChanges** annotazione.  
  
 **\<diffgr:before>**  
 In questo blocco del formato DiffGram è contenuta la versione originale di una riga. Gli elementi in questo blocco corrispondono agli elementi nel ***DataInstance*** bloccato tramite il **diffgr: ID** annotazione.  
  
 **\<diffgr:errors>**  
 Questo blocco del formato DiffGram contiene informazioni sull'errore per una determinata riga nella ***DataInstance*** blocco. Gli elementi in questo blocco corrispondono agli elementi nel ***DataInstance*** bloccato tramite il **diffgr: ID** annotazione.  
  
## <a name="diffgram-annotations"></a>Annotazioni DiffGram  
 I DiffGram usano diverse annotazioni per correlare elementi presenti nei vari blocchi di DiffGram, che rappresentano diverse versioni di riga o informazioni relative agli errori nel tipo <xref:System.Data.DataSet>.  
  
 Nella tabella seguente vengono descritte le annotazioni DiffGram definite nello spazio dei nomi DiffGram **urn: schemas-microsoft-com: xml-diffgram-v1**.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**ID**|Consente di accoppiare gli elementi nel  **\<diffgr: prima >** e  **\<diffgr: Errors >** blocchi agli elementi nel **\<** ***DataInstance*** **>** blocco. I valori con il **diffgr: ID** annotazione sono nel formato *[NomeTabella] [IdentificatoreRiga]*. Ad esempio: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Identifica quale elemento dal **\<** ***DataInstance*** **>** blocco è l'elemento padre dell'elemento corrente. I valori con il **diffgr: parentId** annotazione sono nel formato *[NomeTabella] [IdentificatoreRiga]*. Ad esempio: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifica una riga nel **\<** ***DataInstance*** **>** bloccare come modificata. Il **hasChanges** annotazione può avere uno dei due valori seguenti:<br /><br /> **inserted**<br /> Identifica un **Added** riga.<br /><br /> **modified**<br /> Identifica un **Modified** riga che contiene un' **originale** versione di riga nel  **\<diffgr: prima >** blocco. Si noti che **Deleted** righe avranno un **originale** versione di riga nel  **\<diffgr: prima >** blocco, ma non è presente alcun elemento annotato nel **\<** ***DataInstance*** **>** blocco.|  
|**hasErrors**|Identifica una riga nel **\<** ***DataInstance*** **>** blocco con un **RowError**. L'elemento di errore viene inserito nel  **\<diffgr: Errors >** blocco.|  
|**Error**|Contiene il testo del **RowError** per un particolare elemento le  **\<diffgr: Errors >** blocco.|  
  
 Quando legge o scrive il proprio contenuto come DiffGram, il tipo <xref:System.Data.DataSet> include ulteriori annotazioni. La tabella seguente descrive tali annotazioni, che sono definiti nello spazio dei nomi **urn: schemas-microsoft-com: xml-msdata**.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**RowOrder**|Conserva l'ordine di riga dei dati originali e identifica l'indice di una riga in un particolare tipo <xref:System.Data.DataTable>.|  
|**Hidden**|Identifica una colonna con un **ColumnMapping** impostata su **MappingType**. L'attributo viene scritto nel formato **msdata: hidden** *[NomeColonna]*= "*valore*". Ad esempio: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Notare che le colonne nascoste vengono scritte come attributo DiffGram solo se in tali colonne sono presenti dati. In caso contrario, vengono ignorate.|  
  
## <a name="sample-diffgram"></a>Esempio di DiffGram  
 Di seguito viene riportato un esempio di formato DiffGram. Questo esempio mostra il risultato di un aggiornamento a una riga prima della conferma delle modifiche. La riga con CustomerID pari a "ALFKI" è stata modificata, ma non aggiornata. Di conseguenza, è presente una **correnti** riga con un **diffgr: ID** pari a "Customers1" nel **\<** ***DataInstance*** **>** blocco e un **originale** riga con un **diffgr: ID** pari a "Customers1" nel  **\<diffgr: prima >** blocco. La riga con CustomerID "ANATR" include un **RowError**, quindi è annotata con `diffgr:hasErrors="true"` e si trova un elemento correlato nel  **\<diffgr: Errors >** blocco.  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di XML in un dataset](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Caricamento di un dataset da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Scrittura del contenuto di dataset come dati XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
