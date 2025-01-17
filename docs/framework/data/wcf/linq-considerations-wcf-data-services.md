---
title: Considerazioni su LINQ (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: 05919f0e3cd873d3f6afe9a45736ab38d0da878b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645591"
---
# <a name="linq-considerations-wcf-data-services"></a>Considerazioni su LINQ (WCF Data Services)
In questo argomento vengono fornite informazioni sulla modalità con cui le query LINQ vengono composte ed eseguite quando si usa il client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] e sulle limitazioni dell'utilizzo di LINQ per eseguire una query su un servizio dati che implementa [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]. Per altre informazioni sulla composizione e l'esecuzione di query su un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basato su servizio dati, vedere [query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="composing-linq-queries"></a>Composizione di query LINQ  
 LINQ consente di comporre query per una raccolta di oggetti che implementa <xref:System.Collections.Generic.IEnumerable%601>. Entrambi i **Aggiungi riferimento al servizio** finestra di dialogo in Visual Studio e lo strumento DataSvcUtil.exe vengono usati per generare una rappresentazione di un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] servizio come classe di contenitore di entità che eredita da <xref:System.Data.Services.Client.DataServiceContext>, nonché oggetti che rappresentano le entità restituite nei feed. Questi strumenti generano anche le proprietà per la classe contenitore di entità delle raccolte esposte come feed dal servizio. Ognuna di queste proprietà della classe che incapsula il servizio dati restituisce un elemento <xref:System.Data.Services.Client.DataServiceQuery%601>. Dal momento che la classe <xref:System.Data.Services.Client.DataServiceQuery%601> implementa l'interfaccia <xref:System.Linq.IQueryable%601> definita da LINQ, è possibile comporre una query LINQ per i feed esposti dal servizio dati che vengono convertiti dalla libreria client in un URI di richiesta query inviato al servizio dati in esecuzione.  
  
> [!IMPORTANT]
>  La sintassi LINQ consente di esprimere un set di query più ampio di quello consentito dalla sintassi URI usata dai servizi dati [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Quando non è possibile eseguire il mapping della query a un URI nel servizio dati di destinazione, viene generato un oggetto <xref:System.NotSupportedException>. Per altre informazioni, vedere la [metodi LINQ non supportati](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md#unsupportedMethods) in questo argomento.  
  
 Nell'esempio seguente viene riportata una query LINQ che restituisce `Orders` con un costo di spedizione maggiore di 30 dollari e ordina i risultati in base alla data di spedizione, partendo da quella più recente:  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]    
  
 Questa query LINQ viene convertita nella query seguente URI che viene eseguita a fronte di basato su Northwind [Guida introduttiva](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) servizio dati:  
  
```  
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 Per informazioni più generali su LINQ, vedere [Language-Integrated Query (LINQ) - C# ](../../../csharp/programming-guide/concepts/linq/index.md) oppure [Language Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).  
  
 LINQ consente di comporre query tramite la sintassi di query dichiarativa specifica della lingua, mostrata nell'esempio precedente, e un set di metodi di query noti come operatori di query standard. Una query equivalente a quella dell'esempio precedente può essere composta solo tramite la sintassi basata sul metodo, come indicato nell'esempio seguente:  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]    
  
 Il client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] è in grado di convertire entrambi tipi di query composte in un URI di query ed è possibile estendere una query LINQ aggiungendo i metodi di query a un'espressione di query. Quando si compongono query LINQ aggiungendo la sintassi del metodo a un'espressione di query o un elemento <xref:System.Data.Services.Client.DataServiceQuery%601>, le operazioni vengono aggiunte all'URI della query nell'ordine di chiamata dei metodi. Equivale alla chiamata del metodo <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> per aggiungere ogni opzione di query all'URI della query.  
  
## <a name="executing-linq-queries"></a>Esecuzione di query LINQ  
 Alcuni metodi di query LINQ, ad esempio <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> o <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, quando vengono aggiunti alla query ne causano l'esecuzione. Una query viene eseguita anche quando i risultati vengono enumerati in modo implicito, ad esempio durante un ciclo `foreach` o quando la query è assegnata a una raccolta `List`. Per altre informazioni, vedere [l'esecuzione di query al servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Il client esegue una query LINQ in due parti. Ogni qualvolta possibile, le espressioni LINQ di una query vengono prima valutate sul client e quindi viene generata una query basata sull'URI che viene inviata al servizio dati per la valutazione rispetto ai dati del servizio. Per altre informazioni, vedere la sezione [Client e l'esecuzione del Server del](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md#executingQueries) nelle [l'esecuzione di query al servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Quando non è possibile convertire una query LINQ in un URI di query conforme a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], viene generata un'eccezione quando viene tentata l'esecuzione. Per altre informazioni, vedere [l'esecuzione di query al servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="linq-query-examples"></a>Esempi di query LINQ  
 Negli esempi delle sezioni seguenti vengono illustrati i tipi di query LINQ che possono essere eseguiti su un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
<a name="filtering"></a>   
### <a name="filtering"></a>Filtro  
 Negli esempi di query LINQ in questa sezione vengono filtrati i dati nel feed restituito dal servizio.  
  
 Negli esempi seguenti vengono illustrate query equivalenti che filtrano le entità `Orders` restituite in modo che vengano restituiti solo gli ordini con un costo di spedizione maggiore di $30:  
  
- Utilizzo della sintassi di query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]     
  
- Utilizzo dei metodi di query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]       
  
- Opzione `$filter` della stringa di query:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]       
  
 Tutti gli esempi precedenti vengono convertiti nell'URI di query: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.  
  
<a name="sorting"></a>   
### <a name="sorting"></a>Ordinamento  
 Negli esempi seguenti vengono illustrate query equivalenti che ordinano i dati restituiti in base al nome dell'azienda e al codice postale, in ordine decrescente:  
  
- Utilizzo della sintassi di query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]        
  
- Utilizzo dei metodi di query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]        
  
- Opzione `$orderby` della stringa di query:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]         
  
 Tutti gli esempi precedenti vengono convertiti nell'URI di query: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.  
  
<a name="projection"></a>   
### <a name="projection"></a>Proiezione  
 Negli esempi seguenti vengono illustrate query equivalenti che ordinano i dati restituiti dal progetto nel tipo `CustomerAddress` più ristretto:  
  
- Utilizzo della sintassi di query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]         
  
- Utilizzo dei metodi di query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]         

> [!NOTE]
>  L'opzione di query `$select` non può essere aggiunta a un URI di query tramite il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Si consiglia di usare il metodo LINQ <xref:System.Linq.Enumerable.Select%2A> in modo che il client generi l'opzione di query `$select` nell'URI della richiesta.  
  
 Entrambi gli esempi precedenti vengono convertiti nell'URI di query: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.  
  
<a name="paging"></a>   
### <a name="client-paging"></a>Paging del client  
 Negli esempi seguenti vengono illustrate query equivalenti che richiedono una pagina delle entità ordinate che include 25 ordini, ignorando i primi 50 ordini:  
  
- Applicazione di metodi di query a una query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]     
  
- Opzioni `$skip` e `$top` della stringa di query dell'URI:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]     
  
 Entrambi gli esempi precedenti vengono convertiti nell'URI di query: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.  
  
<a name="expand"></a>   
### <a name="expand"></a>Expand  
 Quando si esegue una query su un servizio dati [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], è possibile richiedere che le entità relative all'entità di destinazione della query siano incluse nel feed restituito. Il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> viene chiamato su <xref:System.Data.Services.Client.DataServiceQuery%601> per il set di entità indirizzato dalla query LINQ, con il relativo nome del set di entità fornito come parametro `path`. Per altre informazioni, vedere [caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Negli esempi seguenti vengono mostrate modalità equivalenti per usare il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> in una query:  
  
- Nella sintassi della query LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]      
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- Con i metodi di query LINQ:  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]       
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]       

 Entrambi gli esempi precedenti vengono convertiti nell'URI di query: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a>Metodi LINQ non supportati  
 Nella tabella seguente sono riportate le classi dei metodi LINQ non supportati che non possono essere incluse in una query eseguita su un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
|Tipo di operazione|Metodo non supportato|  
|--------------------|------------------------|  
|Operatori Set|Tutti gli operatori Set non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>, compresi quelli indicati di seguito:<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|Operatori di ordinamento|Gli operatori di ordinamento seguenti che richiedono <xref:System.Collections.Generic.IComparer%601> non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|Operatori di proiezione e di filtro|I seguenti operatori di proiezione e filtro che accettano un argomento posizionale non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|Operatori di raggruppamento|Tutti gli operatori di raggruppamento non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>, compresi quelli indicati di seguito:<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> È necessario eseguire le operazioni di raggruppamento sul client.|  
|Operatori di aggregazione|Tutti gli operatori di aggregazione non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>, compresi quelli indicati di seguito:<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> Le operazioni di aggregazione devono essere eseguite sul client o devono essere incapsulate da un'operazione del servizio.|  
|Operatori di paging|Gli operatori di paging seguenti non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A> **Nota:**  Gli operatori di paging eseguiti in una sequenza vuota restituiscono Null.|  
|Altri operatori|Gli operatori seguenti non sono supportati con <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> 1.  <xref:System.Linq.Enumerable.Empty%2A><br />2.  <xref:System.Linq.Enumerable.Range%2A><br />3.  <xref:System.Linq.Enumerable.Repeat%2A><br />4.  <xref:System.Linq.Enumerable.ToDictionary%2A><br />5.  <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a>Funzioni di espressione non supportate  
 Le proprietà e i metodi Common Language Runtime (CLR) riportati di seguito sono supportati perché possono essere convertiti in un'espressione di query per l'inclusione nell'URI della richiesta a un servizio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
|<xref:System.String> Membro|Funzione [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supportata|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<xref:System.DateTime> Membro<sup>1</sup>|Funzione [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supportata|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup>l'equivalente proprietà data e ora del <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType>, nonché il <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> metodo in Visual Basic sono inoltre supportati.  
  
|<xref:System.Math> Membro|Funzione [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supportata|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<xref:System.Linq.Expressions.Expression> Membro|Funzione [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supportata|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 È possibile che il client sia anche in grado di valutare funzioni CLR aggiuntive sul client. Viene generata un'eccezione <xref:System.NotSupportedException> per qualsiasi espressione che non può essere valutata sul client e non può essere convertita in un URI della richiesta valido per la valutazione sul server.  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
- [Proiezioni di query](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)
- [Materializzazione di oggetti](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)
- [OData: Convenzioni URI](https://go.microsoft.com/fwlink/?LinkID=185564)
