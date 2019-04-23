---
title: Prestazioni di DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: f0a85232b753eed891cded4b0fb1154269b30dc9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224116"
---
# <a name="dataview-performance"></a><span data-ttu-id="661b1-102">Prestazioni di DataView</span><span class="sxs-lookup"><span data-stu-id="661b1-102">DataView Performance</span></span>
<span data-ttu-id="661b1-103">In questo argomento vengono illustrati i vantaggi, in termini di prestazioni, associati all'utilizzo dei metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> della classe <xref:System.Data.DataView> e della memorizzazione nella cache di un oggetto <xref:System.Data.DataView> in un'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="661b1-103">This topic discusses the performance benefits of using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView> class, and of caching a <xref:System.Data.DataView> in a Web application.</span></span>  
  
## <a name="find-and-findrows"></a><span data-ttu-id="661b1-104">Find e FindRows</span><span class="sxs-lookup"><span data-stu-id="661b1-104">Find and FindRows</span></span>  
 <span data-ttu-id="661b1-105"><xref:System.Data.DataView> costruisce un indice</span><span class="sxs-lookup"><span data-stu-id="661b1-105"><xref:System.Data.DataView> constructs an index.</span></span> <span data-ttu-id="661b1-106">che contiene le chiavi compilate da una o più colonne della tabella o della vista.</span><span class="sxs-lookup"><span data-stu-id="661b1-106">An index contains keys built from one or more columns in the table or view.</span></span> <span data-ttu-id="661b1-107">Tali chiavi sono archiviate in una struttura che consente a <xref:System.Data.DataView> di individuare con rapidità ed efficienza la riga o le righe associate ai valori di chiave.</span><span class="sxs-lookup"><span data-stu-id="661b1-107">These keys are stored in a structure that enables the <xref:System.Data.DataView> to find the row or rows associated with the key values quickly and efficiently.</span></span> <span data-ttu-id="661b1-108">Le operazioni che utilizzano l'indice, ad esempio filtro e ordinamento, vedere notevoli miglioramenti delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="661b1-108">Operations that use the index, such as filtering and sorting, see significant performance increases.</span></span> <span data-ttu-id="661b1-109">L'indice relativo a un oggetto <xref:System.Data.DataView> viene compilato sia quando si crea <xref:System.Data.DataView> che quando si modifica una qualsiasi delle informazioni relative all'ordinamento o al filtraggio.</span><span class="sxs-lookup"><span data-stu-id="661b1-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="661b1-110">Se si crea un oggetto <xref:System.Data.DataView> e quindi si impostano le impostazioni sull'ordinamento o il filtraggio in un secondo momento, l'indice verrà compilato almeno due volte, ovvero una volta durante la creazione di <xref:System.Data.DataView> e una seconda volta quando viene modificata una qualsiasi delle proprietà di ordinamento o filtro.</span><span class="sxs-lookup"><span data-stu-id="661b1-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span> <span data-ttu-id="661b1-111">Per altre informazioni sul filtro e ordinamento con <xref:System.Data.DataView>, vedere [filtro con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) e [ordinamento con DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="661b1-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
 <span data-ttu-id="661b1-112">Per restituire i risultati di una particolare query sui dati anziché fornire una visualizzazione dinamica di un subset di dati, è possibile usare i metodi <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> di <xref:System.Data.DataView> anziché impostare la proprietà <xref:System.Data.DataView.RowFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="661b1-112">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="661b1-113">L'utilizzo della proprietà <xref:System.Data.DataView.RowFilter%2A> è consigliato in applicazioni con associazioni a dati, in cui i risultati filtrati vengono visualizzati da un controllo associato.</span><span class="sxs-lookup"><span data-stu-id="661b1-113">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="661b1-114">L'impostazione della proprietà <xref:System.Data.DataView.RowFilter%2A> provoca una ricompilazione dell'indice dei dati, aggiungendo un sovraccarico all'applicazione e riducendo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="661b1-114">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="661b1-115">I metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> si avvalgono dell'indice corrente, senza che sia necessario ricompilarlo.</span><span class="sxs-lookup"><span data-stu-id="661b1-115">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="661b1-116">Se si intende chiamare <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> solo una volta, è opportuno usare l'oggetto <xref:System.Data.DataView> esistente.</span><span class="sxs-lookup"><span data-stu-id="661b1-116">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="661b1-117">Se invece si intende chiamare <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> più volte, è opportuno creare un nuovo oggetto <xref:System.Data.DataView> per ricompilare l'indice sulla colonna da usare per la ricerca e quindi chiamare il metodo <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="661b1-117">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="661b1-118">Per altre informazioni sul <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> metodi, vedere [ricerca righe](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="661b1-118">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods, see [Finding Rows](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
 <span data-ttu-id="661b1-119">Nell'esempio seguente viene usato il metodo <xref:System.Data.DataView.Find%2A> per individuare un contatto il cui cognome è "Zhu".</span><span class="sxs-lookup"><span data-stu-id="661b1-119">The following example uses the <xref:System.Data.DataView.Find%2A> method to find a contact with the last name "Zhu".</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 <span data-ttu-id="661b1-120">Nell'esempio seguente viene usato il metodo <xref:System.Data.DataView.FindRows%2A> per individuare tutti i prodotti di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="661b1-120">The following example uses the <xref:System.Data.DataView.FindRows%2A> method to find all the red colored products.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a><span data-ttu-id="661b1-121">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="661b1-121">ASP.NET</span></span>  
 <span data-ttu-id="661b1-122">In ASP.NET è disponibile un meccanismo di memorizzazione nella cache, che consente di archiviare in memoria oggetti la cui creazione richiede una notevole quantità di risorse del server.</span><span class="sxs-lookup"><span data-stu-id="661b1-122">ASP.NET has a caching mechanism that allows you to store objects that require extensive server resources to create in memory.</span></span> <span data-ttu-id="661b1-123">La memorizzazione di questi tipi di risorse nella cache può migliorare in modo significativo le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="661b1-123">Caching these types of resources can significantly improve the performance of your application.</span></span> <span data-ttu-id="661b1-124">Questo meccanismo viene implementato dalla classe <xref:System.Web.Caching.Cache>, con istanze cache private per ogni applicazione.</span><span class="sxs-lookup"><span data-stu-id="661b1-124">Caching is implemented by the <xref:System.Web.Caching.Cache> class, with cache instances that are private to each application.</span></span> <span data-ttu-id="661b1-125">Poiché la creazione di un nuovo oggetto <xref:System.Data.DataView> può richiedere una notevole quantità di risorse, è opportuno usare la funzionalità di memorizzazione nella cache nelle applicazioni Web in modo da evitare di ricompilare <xref:System.Data.DataView> ogni volta che la pagina Web viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="661b1-125">Because creating a new <xref:System.Data.DataView> object can be resource intensive, you might want to use this caching functionality in Web applications so that the <xref:System.Data.DataView> does not have to be rebuilt every time the Web page is refreshed.</span></span>  
  
 <span data-ttu-id="661b1-126">Nell'esempio seguente l'oggetto <xref:System.Data.DataView> viene memorizzato nella cache per evitare di ordinare nuovamente i dati quando la pagina viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="661b1-126">In the following example, the <xref:System.Data.DataView> is cached so that the data does not have to be re-sorted when the page is refreshed.</span></span>  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.                  
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a><span data-ttu-id="661b1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="661b1-127">See also</span></span>

- [<span data-ttu-id="661b1-128">Data binding e LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="661b1-128">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
